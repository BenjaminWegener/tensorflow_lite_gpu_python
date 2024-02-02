a jupyter notebook to compile a tflite gpu delegate for debian aarch64 (raspberry / chromebook etc) and run a comlete end-to-end training example

on a clean debian system use:
```
sudo apt update && sudo apt install jupyter python3-pip unzip opencl-headers ocl-icd-opencl-dev libegl-dev mesa-common-dev libegl1-mesa-dev libgles2-mesa-dev libegl-dev wget -y
wget -O bazel https://github.com/bazelbuild/bazel/releases/download/7.0.2/bazel-7.0.2-linux-arm64 
chmod +x bazel; ./bazel; sudo cp bazel /usr/bin
wget https://codeload.github.com/tensorflow/tensorflow/zip/refs/heads/master
unzip master; cd tensorflow-master; ./configure
bazel build -s -c opt --config=elinux_aarch64 --copt="-DMESA_EGL_NO_X11_HEADERS" --copt="-DEGL_NO_X11"  tensorflow/lite/delegates/gpu:libtensorflowlite_gpu_delegate.so
pip3 install tensorflow --break-system-packages
wget https://raw.githubusercontent.com/BenjaminWegener/tensorflow_lite_gpu_python/2024_tflite_gpu_python_wheel/tflite_complete_on_device_training_python_gpu.ipynb
jupyter notebook --ip='*' --NotebookApp.token='' --NotebookApp.password=''
```

run the .ipynb in the opening browser

---
based on https://colab.research.google.com/github/tensorflow/tensorflow/blob/master/tensorflow/lite/g3doc/examples/on_device_training/overview.ipynb

## License

[Apache License 2.0](LICENSE)
