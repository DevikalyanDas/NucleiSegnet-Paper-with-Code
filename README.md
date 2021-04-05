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
All the scripts ran using Tensorflow v2.2 in Google Colab Notebook. So, Tensorflow needs to be installed before running the scripts, together with opencv for data-preprocessing..
```pip install requirements.txt```

## Usage
* It is necessary to run the ```pip install spams``` as the stain normalization requires this package.Then you can run the other scripts
* Perform the stain normalization and cropping into patches of 16 (Multi-organ dataset has image size of 1000 x 1000). This will be done by running ``` python color_norm.py```. You can give here the image sizes and path to folders (train,test,valid) and also path where the cropped normalized patches can be saved.
* Then run the ```python main.py``` which will start the training process. It requires path to the saved color normalized patches and various other parametrs. You can change all at the top of the scripts
* For the test, run the ```python test.py``` which will carry out the inference on the test set. But remeber to give the path to your saved weights, model and test image patches.
* All the scripts, are run together in Google colab, to show how to run the scripts.





