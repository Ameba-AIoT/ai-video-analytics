.. _target-section-acuity-install:

Acuity Toolkit Installation
===========================

.. contents::
  :local:
  :depth: 2


Download Acuity Toolkit
-----------------------

By downloading and using the software, you agree to fully comply with the terms and conditions of the :ref:`target-section-acuity-license`

Acuity ToolKit Link: https://github.com/Ameba-AIoT/ai-video-analytics/releases

|

Install Acuity Toolkit
----------------------

This section will show how to install acuity toolkit

Please refer to the user guide document for detail information

* Vivante.Programming.ACUITY.Toolkit.User.Guide.pdf
* Vivante_IDE_User_Guide.pdf
* Vivante.App.Note.Pegasus.Scripts.pdf

|

Install Acuity toolkit on PC
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The Acuity toolkit would be required to generate the NN network binary
file from a pre-trained model. The following documents and tools are
provided by Verisillicon, and please refer its user guild to setup the
PC environment.


Table 1-1 Acuity tool and document


+----------------+----------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------+
| Ver.           | Acuity Tool / Document                             | Description                                                                                                                      |
+================+====================================================+==================================================================================================================================+
|| Acuity 6.18.8 || Verisilicon_SW_VIP_Acuity_6.18.8_whl_20250303.tgz || - Acuity toolkit user guide document                                                                                            |
||               ||                                                   ||                                                                                                                                 |
||               ||                                                   || - Acuity python version toolkit (Please check the installation steps in chapter 2 of Vivante.VIP.ACUITY.Toolkit.User.Guide.pdf) |
+----------------+----------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------+
|                | Verisilicon_SW_NBInfo_1.2.17_20230412.tgz          | - memory evaluation tool (Please check the usage guidelines in its readme file)                                                  |
+----------------+----------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------+
|                | Verisilicon_Tool_VivanteIDE_v5.8.1                 | - command line tool to export network binary file                                                                                |
+----------------+----------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------+
|                | acuity_examples_c901149.tgz                        | - Acuity example and scripts                                                                                                     |
+----------------+----------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------+

Verisilicon_SW_VIP_Acuity_6.18.8_whl_20250303.tgz  

1. Please use the correct acuity wheel version. For example, use **Vivante_acuity_toolkit_whl_6.18.0_python3.8.10** version if you are using Ubuntu 20.04
2. Please install the wheel version
3. Please follow the step in **Vivante.Programming.ACUITY.Toolkit.User.Guide.pdf: Section 2.2 Installing ACUITY Wheel Version** to install the packages
4. After installation, users can use the instruction **pip3 show acuity** to check the version of acuity
5. Please export the acuity path (user can add the instruction to ~/.bashrc file)

.. code-block:: bash

   export ACUITY_PATH=<directory of acuity-toolkit-whl-version>/bin

After installation, please refer to the scripts in acuity_examples_c901149.tgz to execute the flow for Acuity Toolkit

1. Please check the usage guidelines in acuity_examples readme file, and find detail information in Vivante.App.Note.Pegasus.Scripts.pdf

   * Users can look at **Vivante.Programming.ACUITY.Toolkit.User.Guide.pdf: Section 3.2 pegasus Workflow** to understand the procedure
   * Users can look at **Vivante.Programming.ACUITY.Toolkit.User.Guide.pdf: section 3.4 Command Reference** for detail information about import, quantize, inference, and export for a model
2. Users can create their own folder in acuity_examples_c901149 for their customized model (under Models folder)
3. Users can refer to the article NN Deployment or NN Quantization Discussion for acuity model conversion examples

Install VivanteIDE
------------------

Install VivanteIDE on PC
~~~~~~~~~~~~~~~~~~~~~~~~~

VivanteIDE is the command line tool to export network binary file, user don't need to open the IDE interface, we only need to use the cmdtools function of
VivanteIDE for exporting .nb files 

Please refer to the **Vivante_IDE_User_Guide.pdf: Section Install and Uninstall VivanteIDE** for more information about installing VivanteIDE

1. Please install VivanteIDE for Linux OS since Vivante_acuity_toolkit_whl_6.18.0_python3.8.10 is install in linux operating system
2. During installing VivanteIDE, the license file can be skipped since we only want to export network binary file
3. After installing VivanteIDE, please check the path in your OS to ensure the installation is successfull, the packages should be at 
   **/home/$user/Verisilicon/VivanteIDE5.8.1.1 or your designated path**

.. code-block:: bash

   --optimize 'VIP8000NANONI_PID0XAD' \
   --pack-nbg-unify \
   --viv-sdk 'home/Acuity/VivanteIDE5.8.1.1/cmdtools' \

4. User can refer to the article NN Deployment or NN Quantization Discussion for how to export nb file
   
   * optimize: the IP name of Pro2
   * pack-nbg-unify: instructions for exporting nbg files
   * viv-sdk: the path of VivanteIDE cmdtools SDK

.. note :: You only need to read Section Install and Uninstall VivanteIDE for Vivante_IDE_User_Guide.pdf, rest of the feature in user guide won't be used for exporting nb files











