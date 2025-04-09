Acuity Installation
===================

.. contents::
  :local:
  :depth: 2


Install Acuity Toolkit
----------------------

This section will show some suggestion for installing acuity toolkit
Please refer to the user guide document for detail information

By downloading and using the software, you agree to fully comply with the terms and conditions of the :ref:`target-section`

Acuity ToolKit Link: https://github.com/Ameba-AIoT/ai-video-analytics/releases

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

* Please use the correct version. For example, use python3.8.10 version is you are using Ubuntu 20.04
* Please install the wheel version
* Please follow the step in **Installing ACUITY Wheel Version** to install the packages

**After installation, please refer to the scripts in acuity_examples_c901149.tgz to execute the flow for Acuity Toolkit**

* Users can look at section 3.2 pegasus Workflow to understand the procedure
* Users can look at section 3.4 Command Reference for detail information about import, quantize, inference, and export for a model
* Users can create their own folder in acuity_examples_c901149 for their customized model
* Users can also reference to the article NN Deploment and NN Example (Yolov9_tiny) to understand the procedure of acuity toolkit

Install VivanteIDE
------------------

Install VivianteIDE on PC
~~~~~~~~~~~~~~~~~~~~~~~~~

VivanteIDE is the command line tool to export network binary file

Please refer to the section Install and Uninstall VivanteIDE for more information about installation

* Please use **Command Line Installer and Options** to install VivianteIDE
* license file can be skipped 












