NN Model Conversion Steps using Acuity Toolkit on Docker
========================================================

.. contents::
  :local:
  :depth: 2

Step 1: Pre-import Preparation
------------------------------

- Make sure that your have installed and setup Docker before continuing to the following steps, kindly refer to the `installation page <https://ameba-doc-ai-video-analytics-doc.readthedocs-hosted.com/en/latest/user_manual/Acuity_tool/Acuity_installation_docker.html>`_ if you have not done so.

- Please verify that the following command is added in 'pegasus_export_ovx.sh' to ensure successful export on Docker.

.. code-block:: bash

    --optimize 'VIP8000NANONI_PID0XAD' \
    --pack-nbg-unify \
    --viv-sdk '/opt/acuity/Vivante_IDE/VivanteIDE5.8.1.1/cmdtools' \

- To import a model into Acuity, please place the model in a folder which is named after it and make sure that it is accessible by the import script.
- If you do not have a customized model ready, you may download the `sample models <https://github.com/Ameba-AIoT/ameba-ai-offline-toolkit/releases/tag/v1.0.0-models>`_ provided on our Repository for testing. **Do note that these models are for testing and development purposes only.**
- In the folder containing model, create a file named ``dataset.txt``, list down the accessible paths to your images there, you may choose to place all images within the same folder.

Step 2: Import Model
--------------------

Import your model using command ``./pegasus_import.sh <model_name>``

Once import is successful, kindly refer to this `modification page <https://ameba-doc-ai-video-analytics-doc.readthedocs-hosted.com/en/latest/user_manual/NN_quantization_discussion/Inputmeta_file_modification.html>`_ to modify the ``inputmeta.yml`` according to the type of imported model.

Step 3: Quantize Model
----------------------

Perform quantization process using command ``./pegasus_quantize.sh <model_name> <quantization_type>``, where quantization_type can be ``uint8`` or ``int16``.

Step 4: Export Model
--------------------

Once quantization process is completed, please export your quantized model using command ``./pegasus_export_ovx.sh <model_name> <quantization_type>``.

If the export is successful, you will be able to find your '.nb' converted model contained in the 'nbg-unify' folder.


