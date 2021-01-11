# TensorFlow with TensorRT (TF-TRT)

This is a very simple image classification example based on https://github.com/tensorflow/tensorrt/tree/master/tftrt/examples/image-classification updated to run on the Jetson Xavier NX.   You'll learn how to use TensorFlow 2.x to convert a Keras model to three tf-trt models, a fp32, fp16, and int8.  A simple set of test images will be used to both validate and benchmark both the native model and the three tf-trt ones.


## Docker
TBD

## Running directly
This assumes you are running on Jetpack 4.4.x.  You'll want to make sure TensorFlow 2.x is installed on the NX; see https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html for details.

### Protobuf
There appears to be an issue with the python implementation protobuf (see https://jkjung-avt.github.io/tf-trt-revisited).  The current workaround is to build and install a C++ based implemenation. The script install_protobuf-3.13.0.sh will download, build, and install protobuf 3.13.0.  If a later version is needed, the script can be easily updated.  Run the script with the command:
```
sh install_protobuf-3.13.0.sh
```
The script will take some time to complete.  

Now you'll need to run the following commands
```
sudo cp -R /usr/local/lib/python3.6/dist-packages/protobuf-3.13.0-py3.6-linux-aarch64.egg/google/protobuf /usr/local/lib/python3.6/dist-packages/google/
```
Note, if you get an error regarding google.buff, e.g. `No module named 'google.protobuf` rerun the command above.

Once done, reboot your NX.
