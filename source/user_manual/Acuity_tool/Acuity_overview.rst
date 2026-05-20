Offline AI Model Conversion Toolkit (Acuity Toolkit) Overview
=============================================================

.. contents::
  :local:
  :depth: 2


Introduction to Offline AI Model Conversion Toolkit
----------------------------------------------------
The offline AI model conversion toolkit allows user to convert their customized model into '.nb' format which can be loaded directly into AmebaPro2 via example codes.

There are 2 ways to install the toolkit, installation of toolkit via docker image is highly recommended.

For installation via **docker image**, kindly follow the instructions provided in `Acuity Toolkit Docker Installation Guide <https://ameba-doc-ai-video-analytics-doc.readthedocs-hosted.com/en/latest/user_manual/Acuity_tool/Acuity_installation_docker.html>`_. You may also refer to this `tutorial video <https://youtu.be/YyorZoIlb_E>`_ for guidance.   

For **manual installation** and user guide, please refer to the `Toolkit Manual Installation and User Guide <https://ameba-doc-ai-video-analytics-doc.readthedocs-hosted.com/en/latest/user_manual/Acuity_tool/Acuity_installation_manual.html#download-acuity-toolkit>`_ to install the toolkit. Kindly follow the steps provided in the guide to ensure successful model conversion.

Eligibility
-----------
.. note :: 
   To access offline AI model conversion tools, please fill up this  `Form <https://forms.cloud.microsoft/r/ME5sTbximx>`__ with your **official company, institution, or educational organization email account**. This will help us to verify your application and process your inquiry more efficiently. 
   
   Once approved, please sign in to your GitHub account to download the files.

Brief Comparison between Offline and Online Conversion Toolkit
--------------------------------------------------------------

User will have access to the following exclusive features available on Offline Toolkit. 
For every new NN model example released in the SDK, the conversion support will also be primarily given to the Offline Toolkit users first.

+------------------------------------------------+---------------------------------------+--------------------------------------+
| Features                                       |  Offline Toolkit                      |    Online Conversion Upload          |
+------------------------------------------------+---------------------------------------+--------------------------------------+
| Support for YOLOv9-tiny                        |  Yes                                  |    No                                |
+------------------------------------------------+---------------------------------------+--------------------------------------+
| Support for MobileNetV2                        |  Yes                                  |    No                                |
+------------------------------------------------+---------------------------------------+--------------------------------------+
| Automation development on Docker/Linux         |  Yes                                  |    NA                                |
+------------------------------------------------+---------------------------------------+--------------------------------------+

Acuity Supported AI Framework
-----------------------------

======================= ======================
**AI Framework**        **Import File Format**
======================= ======================
Caffe                   .caffemodel
TensorFlow              .pb
TensorFlow Lite         .tflite
Darknet                 .cfg
ONNX                    .onnx
PyTorch                 .pt
Keras                   .h5
======================= ======================

.. note :: No quantization is needed on Acuity Networks converted from ONNX, TensorFlow and Tensorflow Lite models that have been quantized. 
    Kindly note that **per-channel** quantized models are **NOT** supported on Pro2 NPU, please ensure that your model is **per-tensor** quantized.

.. tip :: For PyTorch framework, you are highly recommended to export your file in .onnx format first to ensure successful conversion.

Reference: ACUITY Toolkit User Guide

AmebaPro2 SDK AI Model Application Types
----------------------------------------
Currently, the FreeRTOS and Arduino SDK provides several deployed models. They are listed in following table:

==================== =============== ==========================================================================
Category             Model           Repository
==================== =============== ==========================================================================
Object detection     | Yolov3-tiny   https://github.com/AlexeyAB/darknet
                     | Yolov4-tiny
                     | Yolov7-tiny
Object detection     YOLOv7-tiny-pt  https://github.com/WongKinYiu/yolov7	 
Face detection       SCRFD           https://github.com/deepinsight/insightface/tree/master/detection/scrfd
Face Recognition     MobileFaceNet   https://github.com/deepinsight/insightface/tree/master/recognition
Sound classification YAMNet          https://github.com/tensorflow/models/tree/master/research/audioset/yamnet
==================== =============== ==========================================================================

Reference: `NN Model Zoo <https://ameba-doc-rtos-pro2-sdk.readthedocs-hosted.com/en/latest/application_note/14_NN.html#model-zoo>`_


AmebaPro2 SDK NN MMF examples
-----------------------------

Please refer to the `application note <https://ameba-doc-rtos-pro2-sdk.readthedocs-hosted.com/en/latest/application_note/14_NN.html#using-the-nn-mmf-example-with-vipnn-module>`_ for the usage of NN MMF example with VIPNN module.
