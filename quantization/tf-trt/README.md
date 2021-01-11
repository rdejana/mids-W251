# TensorFlow with TensorRT (TF-TRT)

This is a very simple image classification example based on https://github.com/tensorflow/tensorrt/tree/master/tftrt/examples/image-classification updated to run on the Jetson Xavier NX.   You'll learn how to use TensorFlow 2.x to convert a Keras model to three tf-trt models, a fp32, fp16, and int8.  A simple set of test images will be used to both validate and benchmark both the native model and the three tf-trt ones.


## Docker
This demo is made available as via a Dockerfile.  The image built from this demo leverages Nvidia's TensorFlow 2.x build (see https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html ) and requires an update to Protobuf.  There appears to be an issue with the python implementation protobuf (see https://jkjung-avt.github.io/tf-trt-revisited).  The current workaround is to build and install a C++ based implemenation. The script install_protobuf-3.13.0.sh will download, build, and install protobuf 3.13.0

Assuming you've checked out this repository on your NX, head to the subdirectory `quantization/tf-trt`.  From This directory, run the command `docker build -t tf-trt-demo .`.  This will take a bit of time to build.

Once the image is built, you can run the command `docker run -it --rm --net=host tf-trt-demo`.  Once the container is running, you'll see output similar to:
```
output...
```



