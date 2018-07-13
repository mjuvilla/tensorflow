# TensorFlow Lite

TensorFlow Lite is TensorFlow's lightweight solution for mobile and embedded
devices. It enables low-latency inference of on-device machine learning models
with a small binary size and fast performance supporting hardware acceleration.

See the documentation: https://www.tensorflow.org/mobile/tflite/
Documentation edits can be made here: [tensorflow/docs_src/mobile/tflite](../../docs_src/mobile/tflite)

## Building with cmake

Go to tensorflow/contrib/lite/bin and run:

`cmake -DCMAKE_TOOLCHAIN_FILE=path-to-ndk-bundle/build/cmake/android.toolchain.cmake -DCMAKE_BUILD_TYPE=Release -DANDROID_ABI=ARCHITECTURE -DANDROID_STL=c++_static ..`

ARCHITECTURE can either be armeabi-v7a or x86.

And then run:

`make -j4`