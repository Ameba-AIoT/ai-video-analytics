NN Example (Yolov7_tiny)
========================

.. contents::
  :local:
  :depth: 3

Using customized NN model
-------------------------

This section will demonstrate the process of deploying yolov7-tiny pytorch.

Setup Acuity toolkit on PC
~~~~~~~~~~~~~~~~~~~~~~~~~~

The Acuity toolkit would be required to generate the NN network binary
file from a pre-trained model. The following documents and tools are
provided by Verisillicon, and please refer its user guide to setup the
PC environment.

Please refer to :ref:`target-section-acuity-install` about how to install Verisilicon's Acuity Toolkit

|

Step for customized model conversion 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

User can refer the following acuity toolkit instructions to generate
their own model binary. Necessary scripts are in
"acuity-examples/Script". Take yolov7 as example, user can train or download
*yolov7-tiny.pt*, from
https://github.com/WongKinYiu/yolov7\ .

If user wants to use your self-trained yolov7-tiny model on amebapro2 sdk, these are the following steps

1. Train your customized yolov7-tiny model
   
   * Remember to modify the nc class num in training/yolov7-tiny.yaml to your custom classes num
2. Reparam the trained yolov7-tiny.pt
   
   * Please refer to https://github.com/Ameba-AIoT/ameba-arduino-pro2/tree/dev/Arduino_package/hardware/libraries/NeuralNetwork/src/Yolov7_reparam_scripts for reparam scripts
   * Remeber to modify the nc class num in yolov7-tiny-deploy.yaml to your custom classes num

3. Convert pytorch to onnx
4. Acuity quantize

.. note :: Please use reparam tiny model for deploying


(1) Convert PyTorch to onnx. 

    It is recommend to convert .pt file to onnx file for better performance and compatibility for quantization.
    Please refer to the code export.py in https://github.com/WongKinYiu/yolov7 for exporting onnx file

    **Please modify models/yolo.py in yolov7 repo to the following code**

    In **class Detect**, please modify the forward function, the reason is the official yolov7 will rearrange the tensor from 
    [bs, 255, H, W] to [bs, 3, H, W, 85] when the model is forwarded, but the format supported by pro2 sdk post-processing 
    is [bs, 255, H, W] (to be consistent with yolov3, v4), therefore, we need to change the code in models/yolo.py for amebapro2 support

Please change the function in **class Detect**

.. code-block:: python

    def forward(self, x):
        # x = x.copy()  # for profiling
        z = []  # inference output
        self.training |= self.export
        for i in range(self.nl):
            x[i] = self.m[i](x[i])  # conv
            y = x[i].sigmoid()
            z.append(y)
        out = z
        return out

Next, export .pt to onnx

.. code-block:: bash

    $ python export.py --weights weights/yolov7-tiny.pt --simplify --img-size H W



(2) import the model:

.. code-block:: bash

    $ ./pegasus_import.sh yolov7-tiny

.. note :: Due to yolov7 anchor-based model structure, we don't need to seperate the outputs when importing yolov7-tiny
    
.. code-block:: bash

    cmd="$PEGASUS import onnx\
        --model         ${NAME}.onnx \
        --output-model  ${NAME}.json \
        --output-data   ${NAME}.data \
        $(cat inputs_outputs.txt)"


(3) modify the "scale" and "reverse channel" in yolov7-tiny_inputmeta.yml 
    
    scale: 0.00392157 (1/255), reverse_channel: false
    
    * Since during the training process of yolov7, the input image has been mapped from 0~255 to 0~1


(4) quantize the model:

.. code-block:: bash

    $ ./pegasus_quantize.sh yolov7-tiny uint8

(5) add the following to the command in pegasus_export_ovx.sh

**Acuity 6.18.8**:

.. code-block:: bash

   --optimize 'VIP8000NANONI_PID0XAD' \
   --pack-nbg-unify \
   --viv-sdk 'home/Acuity/VivanteIDE5.8.1.1/cmdtools' \

(6) export the NBG file:

.. code-block:: bash

    $ ./pegasus_export_ovx.sh yolov7-tiny uint8


Then, a network_binary.nb (yolov7-tiny.nb) will be generated. The generated nb file will locate in **wksp/yolov7-tiny_uint8_nbg_unify**

.. note :: After the model conversion is completed. The model can be successfully deployed on amebapro2

|















