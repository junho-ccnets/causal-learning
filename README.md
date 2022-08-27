# CCN
  https://ccnets.org/tutorials?category=CelebA
  
## What is this?

CCNs learns a causal explanation that improves generalization of real world data by reducing the bias caused by misleading correlations lacking any causation. CCNs is capable of performing any common task of machine learning such as regression or prediction by using the explainer and reasoner models, more specifically CCNs is a framekow that allows to incorporate any pretrained or previously designed model. The reconstruction of input observations or labels through the explainer and producer guarantees that the framework can efficiently learn a causal vector explanation of the input data while CCNs also offers causal inference and generation.

## CCN models
- Explainer: Explainer's role is to explain data. Output of Explainer is predicted label of input data: Explaination. Explainer's backborn network can be Image Classifier or MLP which is determined by the use of CCN.
- Reasoner: Reasoner's role is to infer from data and explaination. Reasoner's output is inferred label. Reasoner's backborn network is basically same architecture with Expainer. The difference from Explainer is it's input is not only data but explaination.
- Producer: Producer's role is reconstruction or generation from label. It's input can be (label, explaination) or (inferred_label, explaination). Output is generated data which is same type of input data but deformed.

# Setup
```
git clone https://github.com/junho-ccnets/causal-learning

pip3 install -r requirements.txt
```

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
