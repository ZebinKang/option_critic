# GPU Speedup

## Ubuntu

### Install CUDA

```
sudo apt-get -y install cuda-8-0
```

Monitor memory usage

```
watch -n 0.5 nvidia-smi
```

### Install cuDNN

Get cuDNN Linux Library v5.1 for CUDA8 from [Nvidia](https://developer.nvidia.com/rdp/cudnn-archive)

Install cuDNN

```
sudo cp cuda/include/cudnn.h /usr/local/cuda/include
sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn.h
sudo chmod a+r /usr/local/cuda/lib64/libcudnn*
```

Configure theano to use cuDNN

```
echo -e "\n[dnn]\nenabled=True\ninclude_path=/usr/local/cuda/include\nlibrary_path=/usr/local/cuda/lib64" >> ~/.theanorc
```

## OSX
Because most of MacBooks don't have Nvidia GPU, so it isn't supported to
use GPU speedup on OSX.

