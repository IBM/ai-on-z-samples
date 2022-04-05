# Lab exercises: Exporting or converting a model to the ONNX format

## Overview
This project contains simple jupyter notebook lab exercises demonstrating [ONNX](https://github.com/onnx/onnx) model conversion. This includes:
- Exporting a simple model from [Pytorch](https://github.com/pytorch/pytorch) to ONNX format.
- Converting a tensorflow model to ONNX, using [tensorflow-onnx](https://github.com/onnx/tensorflow-onnx).

These examples require you install needed packages. This is not done as part of the notebook; the steps here will guide you through building and running a docker container to complete the lab exercises.

This lab is intended to be run on an x86/x64 environment to demonstrate converting a trained model to ONNX prior to deploying on IBM zSystems and LinuxONE.

## Steps:

1. Clone the lab github repository `git clone https://github.com/IBM/ai-on-z-samples.git`

2. Navigate to the subdirectoy.

3. Run docker build using the provided dockerfile `docker build .`
    - Using a python base image, this will create an environment with both recent Pytorch and TensorFlow releases, model conversion libraries, as well as the lab jupyter notebooks.

4. Create and run a docker container using the image created on the prior step. As part of this step, you should map the jupyter notebook port, 8888, to a port on your local system. An example follows:
    - `docker run -it --rm -p 8571:8888 <image id> `
    - This states the image in interactive mode, tells docker to delete the container upon exit, and publishes container port 8888 to host port 8571.

5. From a web browser, connect to the jupyter URL provided on the prior step. Note, you must change port 8888 to port 8571.

6. Run through the lab exercises:
    - tfonnx_conversion.ipynb
    - torch_export_onnx.ipynb

7. Download the .ONNX models and inspect them using [Netron](https://netron.app/)




There are numerous additional examples and guidance available, not only for Pytorch and TensorFlow, but for other frameworks as well.

This includes:
- Building, exporting or converting a model [here](https://onnx.ai/supported-tools.html)
- tensorflow-onnx [examples](https://github.com/onnx/tensorflow-onnx/tree/master/examples)
- pytorch [guidance and examples](https://pytorch.org/tutorials/advanced/super_resolution_with_onnxruntime.html)


On IBM Z and LinuxONE, you can run these models using [ONNX-MLIR](https://github.com/onnx/onnx-mlir).
For z/OS users, we recommend you try Watson Machine Learning for z/OS Trial edition, available [here](https://www.ibm.com/products/machine-learning-for-zos).

