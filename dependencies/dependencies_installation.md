# Dependencies installation on Unix-based system

## Create and load virtual environment

create virtual environment
```
virtualenv ~/.virtualenv/option-critic --python=python2
```

load virtual environment
```
source ~/.virtualenv/option-critic/bin/activate
```


## [Arcade Learning Environment][https://github.com/mgbellemare/Arcade-Learning-Environment]

###  Installing Dependencies
#### OSX
Use Homebrew to install several libraries required for low level access to media and controls.

1. sdl: designed to provide low level access to audio, keyboard, mouse, joystick, and graphics hardware
2. sdl_image: image file loading library
3. sdl_mixer: sample multi-channel audio mixer library
4. sdl_ttf: allows you to use TrueType fonts in your SDL applications
5. portmidi: real-time MIDI input/output
```
brew install sdl sdl_image sdl_mixer sdl_ttf portmidi
```

#### Ubuntu
reference to [Arcade Learning Environment][https://github.com/mgbellemare/Arcade-Learning-Environment]

####  Installing Arcade Learning Environment

We will work in the user directory.
```
cd ~
```

Clone the source code from Github.
```
git clone https://github.com/mgbellemare/Arcade-Learning-Environment.git
```

Navigate into the newly-created directory.
```
cd ~/Arcade-Learning-Environment
```

Create a directory to house our build, and navigate into it.
```
mkdir build && cd build
```

Use cmake to build our makefile.
```
cmake -DUSE_SDL=ON -DUSE_RLGLUE=OFF -DBUILD_EXAMPLES=ON ..
```

Finally, launch the build.
```
make -j 4
```

#### Installing the Python Interface
Navigate to the repository root.
```
cd ~/Arcade-Learning-Environment
```


Install the Python module, with the provided setup.py.
1. OSX
```
MACOSX_DEPLOYMENT_TARGET=10.9 pip install -e .
```
2. Ubuntu
```
pip install -e .
```

## OpenCV
### Ubuntu
Get [install-opencv.sh](https://github.com/milq/milq/blob/master/scripts/bash/install-opencv.sh)
 or use the install-opencv.sh provided in this directory directory


Install opencv
```
bash install-opencv.sh
```

Link opencv to the environment

```
ln -s /usr/local/lib/python2.7/site-packages/cv2.so ~/.virtualenv/option-critic/lib/python2.7/site-packages/cv2.so
```

### OSX
Install opencv
```
brew install opencv
```


Link opencv to the environment
```
ln -s /usr/local/opt/opencv3/lib/python2.7/site-packages/cv2.so ~/.virtualenv/option-critic/lib/python2.7/site-packages/cv2.so
```




## General Python Packages

#### Install some general python packages with pip.

```
pip install -r requirements.txt
```

#### Config theano
If your Mac has Nvidia GPU and you want to use it. Config as following
and install CUDA.
```
echo -e "\n[global]\nfloatX=float32\ndevice=gpu\n[mode]=FAST_RUN\n\n[nvcc]\nfastmath=True\n\n[cuda]\nroot=/usr/local/cuda" >> ~/.theanorc
```

Otherwise, config theano as following.
```
echo -e "[global]\nfloatX=float32" >> ~/.theanorc
```
