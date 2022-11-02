# β-VAE to train from frozen or untrained weights

This is a fork of the implementation by [Konny1](https://github.com/1Konny)

### Dependencies
```
python 3.6.4
pytorch 0.3.1.post2
visdom
```
<br>

### Datasets
[same with here]
<br>

### Usage
initialize visdom
```
python -m visdom.server
```
you can reproduce results below by
```
sh run_celeba_H_beta10_z10.sh
sh run_celeba_H_beta10_z32.sh
sh run_3dchairs_H_beta4_z10.sh
sh run_3dchairs_H_beta4_z16.sh
sh run_dsprites_B_gamma100_z10.sh
```
or you can run your own experiments by setting parameters manually.<br>
for objective and model arguments, you have two options H and B indicating methods proposed in Higgins et al. and Burgess et al., respectively.<br>
arguments ```--C_max``` and ```--C_stop_iter``` should be set when ```--objective B```. for further details, please refer to Burgess et al.
```
e.g.
python main.py --dataset 3DChairs --beta 4 --lr 1e-4 --z_dim 10 --objective H --model H --max_iter 1e6 ...
python main.py --dataset dsprites --gamma 1000 --C_max 25 --C_stop_iter 1e5 --lr 5e-4 --z_dim 10 --objective B --model B --max_iter 1e6 ...
```
check training process on the visdom server
```
localhost:8097
```
<br>

### Reference
1. [β-VAE: Learning Basic Visual Concepts with a Constrained Variational Framework, Higgins et al., ICLR, 2017]
2. [Understanding disentangling in β-VAE, Burgess et al., arxiv:1804.03599, 2018]
3. Repo from [Konny1](https://github.com/1Konny)
