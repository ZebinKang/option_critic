# The Option-Critic Architecture

Code for [The Option-Critic Architecture](https://arxiv.org/pdf/1609.05140v2.pdf).

## Installation

Here's a list of all dependencies:

- Numpy
- Theano
- Lasagne
- Launcher
- Argparse
- Arcade Learning Environment
- matplotlib
- cv2 (OpenCV)

[Instruction to how to install these dependencies](/dependencies/dependencies_installation.md)

## Atari Download

Download atari from [openai](https://github.com/openai/atari-py/tree/master/atari_py/atari_roms)


## Training

To train, run following command:
```
python train_q.py --rom breakout --num-options 8 --folder-name breakout_tempmodel
```

To view a list of available parameters, run:
```
print train_q.py --help
```

To speed up training, we highly suggest using cudnn(CUDA).

## Testing

To watch model after training, run:
```
python run_best_model.py models/pong_tempmodel/last_model.pkl
```

