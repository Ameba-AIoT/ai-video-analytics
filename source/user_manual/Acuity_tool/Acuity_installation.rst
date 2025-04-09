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

* Please use the correct acuity wheel version. For example, use **Vivante_acuity_toolkit_whl_6.18.0_python3.8.10** version if you are using Ubuntu 20.04
* Please install the wheel version
* Please follow the step in **Vivante.Programming.ACUITY.Toolkit.User.Guide.pdf: Section 2.2 Installing ACUITY Wheel Version** to install the packages

After installation, please refer to the scripts in acuity_examples_c901149.tgz to execute the flow for Acuity Toolkit

* Please check the usage guidelines in its readme file, and find detail information in Vivante.App.Note.Pegasus.Scripts.pdf
* Users can look at **Vivante.Programming.ACUITY.Toolkit.User.Guide.pdf: Section 3.2 pegasus Workflow** to understand the procedure
* Users can look at **Vivante.Programming.ACUITY.Toolkit.User.Guide.pdf: section 3.4 Command Reference** for detail information about import, quantize, inference, and export for a model
* Users can create their own folder in acuity_examples_c901149 for their customized model (under Models folder)
* Users can also refer to the article NN Deployment and NN quick start (Yolov9_tiny) for examples of acuity model conversion

Install VivanteIDE
------------------

Install VivanteIDE on PC
~~~~~~~~~~~~~~~~~~~~~~~~~

VivanteIDE is the command line tool to export network binary file

Please refer to the **Vivante_IDE_User_Guide.pdf: Section Install and Uninstall VivanteIDE** for more information about installing VivanteIDE

* Please install VivanteIDE for Linux since Vivante_acuity_toolkit_whl_6.18.0_python3.8.10 is install in linux operating system
* license file can be skipped since we only want to export network binary file
* After execution, please check the path to ensure the installation is successfull(/home/$user/Verisilicon/VivanteIDE5.8.1.1 or your designated path)












