Inputmeta File Modification
===========================

.. contents::
  :local:
  :depth: 3

Crucial step before quantization
--------------------------------
After importing model successfully, the ``<model>_inputmeta.yml`` will be generated. You need to modify it properly according to your model's feature. So you need to understand the features of your custom model, such as the input shape, input format, data normalization etc. Below are the parameters that need to be modified for different models:

YOLOv4-tiny
~~~~~~~~~~~
+----------------------+---------------------+
| Parameter            | Value               |
+======================+=====================+
| reverse_channel      | false               |
+----------------------+---------------------+
| scale                | 0.003921568627451   |
+----------------------+---------------------+
| add_preproc_node     | true                |
+----------------------+---------------------+
| preproc_type         | IMAGE_RGB888_PLANAR |
+----------------------+---------------------+

.. note :: If you retrain your model with a different dataset, please update the mean/scale accordingly as the mean/scale depends on the feature of dataset and data normalization.

YOLOv7-tiny for Pytorch version
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. tip :: Kindly convert your model .pt format to .onnx format before importing.

+----------------------+---------------------+
| Parameter            | Value               |
+======================+=====================+
| reverse_channel      | false               |
+----------------------+---------------------+
| scale                | 0.003921568627451   |
+----------------------+---------------------+
| add_preproc_node     | true                |
+----------------------+---------------------+
| preproc_type         | IMAGE_RGB888_PLANAR |
+----------------------+---------------------+

.. note :: If you retrain your model with a different dataset, please update the mean/scale accordingly as the mean/scale depends on the feature of dataset and data normalization.

MobileFaceNet
~~~~~~~~~~~~~

+----------------------+-------------------------+
| Parameter            | Value                   |
+======================+=========================+
| reverse_channel      | false                   |
+----------------------+-------------------------+
| mean                 | 123.675, 116.28, 103.53 |
+----------------------+-------------------------+
| scale                | 0.003921568627451       |
+----------------------+-------------------------+
| add_preproc_node     | true                    |
+----------------------+-------------------------+
| preproc_type         | IMAGE_RGB888_PLANAR     |
+----------------------+-------------------------+

.. note :: If you retrain your model with a different dataset, please update the mean/scale accordingly as the mean/scale depends on the feature of dataset and data normalization.

SCRFD
~~~~~

+----------------------+-------------------------+
| Parameter            | Value                   |
+======================+=========================+
| reverse_channel      | false                   |
+----------------------+-------------------------+
| mean                 | 127.5, 127.5, 127.5     |
+----------------------+-------------------------+
| scale                | 0.0078125               |
+----------------------+-------------------------+
| add_preproc_node     | true                    |
+----------------------+-------------------------+
| preproc_type         | IMAGE_RGB888_PLANAR     |
+----------------------+-------------------------+

.. note :: If you retrain your model with a different dataset, please update the mean/scale accordingly as the mean/scale depends on the feature of dataset and data normalization.

YAMNet
~~~~~~

This model cannot be quantized due to the use of STFT/FFT operator. You may proceed straight to export step.

CNN Model for Image classification
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. tip :: For Tensorflow keras .h5 models, please do not save optimizer data in .h5 file. Otherwise it will fail when starting to import H5 model. To ignore optimizer data, please add include_optimizer=False in command. For example: model.save('model.h5', include_optimizer=False)

**RGB**

+----------------------+---------------------+
| Parameter            | Value               |
+======================+=====================+
| reverse_channel      | false               |
+----------------------+---------------------+
| scale                | 0.003921568627451   |
+----------------------+---------------------+
| add_preproc_node     | true                |
+----------------------+---------------------+
| preproc_type         | IMAGE_RGB888_PLANAR |
+----------------------+---------------------+

**Gray**

Some models which require gray image dataset, for example, fer2013_cnn, you need to modify yml file differently as the Acuity tool doesn't support bmp files.

+----------------------+---------------------+
| Parameter            | Value               |
+======================+=====================+
| reverse_channel      | false               |
+----------------------+---------------------+
| scale                | 0.003921568627451   |
+----------------------+---------------------+
| add_preproc_node     | true                |
+----------------------+---------------------+
| preproc_type         | TENSOR              |
+----------------------+---------------------+

.. note :: TENSOR means the data will be native tensor data without any header. For gray image dataset, tensor files instead of jpeg or bmp files are used for calibration.