a jupyter notebook to compile a tflite gpu delegate for debian aarch64 (raspberry / chromebook etc) and run a comlete end-to-end example training

based on https://colab.research.google.com/github/tensorflow/tensorflow/blob/master/tensorflow/lite/g3doc/examples/on_device_training/overview.ipynb

on a clean debian system use:
```
sudo apt update && sudo apt install jupyter python3-pip unzip wget
pip3 install tensorflow --break-system-packages
wget https://raw.githubusercontent.com/BenjaminWegener/tensorflow_lite_gpu_python/2024_tflite_gpu_python_wheel/tflite_complete_on_device_training_python_gpu.ipynb
jupyter notebook --ip='*' --NotebookApp.token='' --NotebookApp.password=''
```

run the .ipynb in the opening browser

## License

[Apache License 2.0](LICENSE)
