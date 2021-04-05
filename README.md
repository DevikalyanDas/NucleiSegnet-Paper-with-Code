# NucleiSegnet-Paper-with-Code
This repository contains the Tensorflow code for the paper:
[NucleiSegNet: Robust deep learning architecture for the nuclei segmentation of liver cancer histopathology images](https://www.sciencedirect.com/science/article/abs/pii/S0010482520304066)

If you find this code helpful, please cite our work:
```
@article{LAL2021104075,
title = {NucleiSegNet: Robust deep learning architecture for the nuclei segmentation of liver cancer histopathology images},
journal = {Computers in Biology and Medicine},
volume = {128},
pages = {104075},
year = {2021},
issn = {0010-4825},
doi = {https://doi.org/10.1016/j.compbiomed.2020.104075},
url = {https://www.sciencedirect.com/science/article/pii/S0010482520304066},
author = {Shyam Lal and Devikalyan Das and Kumar Alabhya and Anirudh Kanfade and Aman Kumar and Jyoti Kini},
keywords = {Deep neural network, Histopathology image, Nuclei segmentation, Nuclei detection},
}
```
## Goal
To perform nuclei segmentation of the Liver cancer Histopathology Images using deep learning architecture.

## Requirements
All the scripts ran using Tensorflow v2.2 in Google Colab Notebook. So all the required dependencies can be installed using
```pip install -r requirements.txt```

## Usage
* It is necessary to run the ```pip install spams``` as the stain normalization requires this package.Then you can run the other scripts
* Perform the stain normalization and cropping into patches of 16 (Multi-organ dataset has image size of 1000 x 1000). This will be done by running ``` python color_norm.py```. You can give here the image sizes and path to folders (train,test,valid) and also path where the cropped normalized patches can be saved.
* Then run the ```python main.py``` which will start the training process. It requires path to the saved color normalized patches and various other parametrs. You can change all at the top of the scripts
* For the test, run the ```python test.py``` which will carry out the inference on the test set. But remeber to give the path to your saved weights, model and test image patches.
* All the scripts, are run together in Google colab, to show how to run the scripts.

## Code Structure
```
code-template/
│
├── color_norm.py       - script to start training
├── inference.py        - inference using a trained model
├── trainer.py          - the main trained
├── config.json         - holds configuration for training
│
├── base/               - abstract base classes
│   ├── base_data_loader.py
│   ├── base_model.py
│   ├── base_dataset.py  - All the data augmentations are implemented here
│   └── base_trainer.py
│
├── dataloader/ - loading the data for different segmentation datasets
│
├── models/ - contains semantic segmentation models
│
├── saved/
│   ├── runs/ - trained models are saved here
│   └── log/ - default logdir for tensorboard and logging output
│  
└── utils/ - small utility functions
    ├── losses.py - losses used in training the model
    ├── metrics.py - evaluation metrics used
    └── lr_scheduler - learning rate schedulers 
```

## Folder Structure
The code is built using this folder template
```
Folder Template/
│
└── TrainData/     - Training data folder containing the stain normalized patches for training
    ├── Bin        - Binary Labels
    ├── tis        - Training images
└── ValidData/     
    ├── Bin  
    ├── tis 
└── TestData/      
    ├── Bin  
    ├── tis 
├── checkpoint     - For saving the weight
├── history        - For saving the loss and metrice score
├── results        - For saving the segmented mask
```

## Segmented Masks

| ID's    | Ground Truth  |    NucleiSegnet | 
| ----------- | ----------- | ----------- |
|    |    |    |





