# CCN
  https://ccnets.org/tutorials?category=CelebA
  
## Causal Learning with CCNets

Causal Cooperative Nets(CCNets) is the brand new ML frameworks that are composed of three neural network models; explainer, reasoner and producer.
This ML training is for discovering causal relationships in statistics and explaining black boxes in the ML modeling. Compared to supervised or generative learning, which trains one or two models on the data, this method cooperatively trains three models (explainer, reasoner, producer) simultaneously.
The causal learning with CCNets is different from supervised learning. Normally, supervised learning receives an observation as input and predicts its label that learn association between the observation space and label space. The causal learning takes an observation and its label as input that learn causal relationship between the observation space and label space.

## CCNet models
- **Explainer**: The explainer model learns data explanation for labels. It receives observed data as input and outputs latent vector(causal explantion vector) in the explantory space. Neural networks that are used for Classifier or regressor can be placed as Explainer in CCNets.

- **Reasoner**: Reasoner's role is to infer from data and explaination. Reasoner's output is inferred label. Reasoner's backborn network is basically same architecture with Expainer. The difference from Explainer is it's input is not only data but explaination.

- **Producer**: The producer model learns to generate data with an explanation. It receives a label and a causal explantion vector as input and outputs generated data.

# Setup
```
git clone https://github.com/junho-ccnets/causal-learning

pip3 install -r requirements.txt
```

# Pretrained Models
**Update 27/08/2022:**
- explainer: https://ccnets.org/models?category=CelebA&models=explainer
- reasoner: https://ccnets.org/models?category=CelebA&models=reaonser
- producer: https://ccnets.org/models?category=CelebA&models=producer

## Dataset
If you just want to test training, you should download your dataset
```
dataroot = <data_path>
trainset = dset.CelebA(root=dataroot, split = "train", transform=transforms.Compose([
                            transforms.Resize(n_img_sz),
                            transforms.ToTensor(),
                            transforms.CenterCrop(n_img_sz),
                            transforms.Normalize((0.5, 0.5, 0.5), (0.5, 0.5, 0.5)),
                        ]), download = True)
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
