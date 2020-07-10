# CycleGAN in Horovod and PyTorch

The code is distributed training implementation for CycleGan.

Original paper: [https://arxiv.org/abs/1703.10593](https://arxiv.org/abs/1703.10593)

Official source code: [https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix)

## Getting Started
### Installation

- Clone this repo:
```bash
git clone https://github.com/RyanWangCode/CycleGAN-horovod
cd pytorch-CycleGAN-and-pix2pix
```

- Install [Horovod](https://github.com/horovod/horovod), [PyTorch](http://pytorch.org)  0.4+ and other dependencies (e.g., torchvision).

### CycleGAN train/test
- Download a CycleGAN dataset (e.g. maps):
```bash
bash ./datasets/download_cyclegan_dataset.sh maps
```
- To view training results and loss plots, run `python -m visdom.server` and click the URL http://localhost:8097.
- Train a model:
```bash
#!./scripts/train_cyclegan.sh
python train.py --dataroot ./datasets/maps --name maps_cyclegan --model cycle_gan
```
To see more intermediate results, check out `./checkpoints/maps_cyclegan/web/index.html`.
- Test the model:
```bash
#!./scripts/test_cyclegan.sh
python test.py --dataroot ./datasets/maps --name maps_cyclegan --model cycle_gan
```
- The test results will be saved to a html file here: `./results/maps_cyclegan/latest_test/index.html`.
