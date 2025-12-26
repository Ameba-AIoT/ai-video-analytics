Acuity Toolkit Docker Installation
==================================

.. contents::
  :local:
  :depth: 2


Download Acuity Toolkit Docker
------------------------------

By downloading and using the software, you agree to fully comply with the terms and conditions of the :ref:`target-section-acuity-license`

* Users don't need to download **Verisilicon_SW_VIP_Acuity_6.18.8_whl_20250303.tgz and Verisilicon_Tool_VivanteIDE_v5.8.1_CL664938_Linux_Windows_SDK_p6.4.x_dev_6.4.14.tgz** since these packages is already install in Docker
* Acuity_PATH is also written in docker, written in .bashrc
* We mount acuity_examples_c901149 and Verisilicon_SW_NBInfo_1.2.17_20230412 into docker for flexible operation, so we need to download these software packages


Toolkit Files and Github Access
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- :download:`acuity_examples_c901149.tgz <https://github.com/Ameba-AIoT/ameba-ai-offline-toolkit/releases/download/v1.0.0/acuity_examples_c901149.tgz>`

- :download:`Verisilicon_SW_NBInfo_1.2.17_20230412.tgz <https://github.com/Ameba-AIoT/ameba-ai-offline-toolkit/releases/download/v1.0.0/Verisilicon_SW_NBInfo_1.2.17_20230412.tgz>`

.. note :: 
   ​To access offline AI model conversion tools, please contact AmebaAIoT@realtek.com with the subject line **"Offline AI Model"**. Ensure that you use your **official company, institution, or educational organization email account** for this request. This will help to verify your affiliation and process your inquiry more efficiently.
   
   Once approved, please sign in to your GitHub account to download the files 


We store or docker images on **GitHub Container Registry**, please establish Personal Access Token\

1. GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Generate new token (classic)
3. For permissions: at least select: write:packages, read:packages, delete:packages
4. For Repository access: please select **All repositories**

Docker Entry
------------

Linux
~~~~~
.. code-block:: bash

   cd Linux
   source install.sh (This script will download the docker image from ghcr.io)
   source run.sh (docker entry)


The script will mount acuity_examples and Verisilicon_SW_NBInfo into docker, please placed the folders in the same path with run.sh

.. code-block:: bash

   docker run -it --rm \
      --user $(id -u):$(id -g) \
      -e HOME=/home/user \
      -w /workspace/acuity_examples \
      -v "$(pwd)/acuity_examples_c901149:/workspace/acuity_examples" \
      -v "$(pwd)/Verisilicon_SW_NBInfo_1.2.17_20230412:/workspace/Verisilicon_SW_NBInfo_1.2.17_20230412" \
      ${IMAGE_NAME}:${IMAGE_TAG}

Windows
~~~~~~~

.. code-block:: bash

   cd Windows
   source install.bat (This script will download the docker image from ghcr.io)
   source run.bat (docker entry)

The script will mount acuity_examples and Verisilicon_SW_NBInfo into docker, please placed the folders in the same path with run.bat

.. code-block:: bash

   docker run -it --rm \
      --user $(id -u):$(id -g) \
      -e HOME=/home/user \
      -w /workspace/acuity_examples \
      -v "$(pwd)/acuity_examples_c901149:/workspace/acuity_examples" \
      -v "$(pwd)/Verisilicon_SW_NBInfo_1.2.17_20230412:/workspace/Verisilicon_SW_NBInfo_1.2.17_20230412" \
      ${IMAGE_NAME}:${IMAGE_TAG}











