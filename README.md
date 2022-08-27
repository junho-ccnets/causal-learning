# Causal-learning
  https://ccnets.org/tutorials?category=CelebA
  
# Setup
```
git clone https://github.com/junho-ccnets/causal-learning

pip3 install -r requirements.txt
```
  
# Parameter Reference
- `dataroot`: Root directory for dataset
- `workers`: Number of workers for dataloader
- `batch_size`: Batch size during training
- `n_img_ch`: image channels
- `n_img_sz`: image width & heights
- `dim_explanation`: number of dimensions of causal explanation vector in explantory space
- `dim_label`: A dimension of labels
- `lr`: Learning rate for Celeb A images
- `num_epochs`: Number of training epochs
- `step_size`: Learning rate for optimizers
- `beta1`: coefficients used for computing running averages of gradient
- `gamma`: scheduler decay rate
- `manualSeed`: Set random seed for reproducibility

# Copyright
ⓒ 2022 CCNets, Inc All Rights reserved.
