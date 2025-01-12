# Self-Supervised Learning Examples
## Requriments

To run examples you need catalyst[cv]==21.09 and catalyst[ml]==21.09
```
pip install catalyst[cv]==21.09
pip install catalyst[ml]==21.09
```

## Description

All traing files have common command line parametrs:

    --feature_dim - Feature dim for latent vector
    --temperature - Temperature used in softmax
    --batch_size - Number of images in each mini-batch
    --epochs - Number of sweeps over the dataset to train
    --num_workers - Number of workers to process a dataloader
    --logdir - Logs directory (tensorboard, weights, etc)
    --dataset - Dataset: CIFAR-10, CIFAR-100 or STL10
    --learning_rate - Learning rate for optimizer

### Extra parametrs

Barlow-twins (barlow_twins.py) has an extra parametr ``--offdig_lambda`` - lambda that controls the on- and off-diagonal terms from Barlow twins loss.

## Usage

Implemented algorithms:
- Barlow-Twins: ``barlow_twins.py``
- BYOL: ``byol.py``
- SimClR: ``simCLR.py``
- Supervised contrastive: ``supervised_contrastive.py``

You can run an algorithm with a command:
```
python3 barlow_twins.py --batch_size 32
```
Also, you can use the Docker:
```
docker build . -t train-self-supervised
docker run train-self-supervised python3 simCLR.py --batch_size 32
```



