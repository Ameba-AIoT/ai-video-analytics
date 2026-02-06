.. _target-section-nn-quantization-discussion:

Realtek AmebaPro2 NN Quantization Discussion
============================================

By quantizing the model, it can decrease the size of model and speed up the inference. But it will decrease the accuracy about 1~3% as well.

Before starting quantization, please prepare a dataset for calibration by choosing images from your dataset randomly and copy them to a folder. Then create a text file, called ``dataset.txt`` to list down the path of the images. Kindly place the ``dataset.txt`` in the same directory as the model.

.. toctree::
   :maxdepth: 3

   Inputmeta_file_modification

Examples

.. toctree::
   :maxdepth: 3

   NN_yolov7_example
   NN_yolov9_example
