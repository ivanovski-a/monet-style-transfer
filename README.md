# Photo-to-Monet Image Translation using CycleGAN

![Model training](assets/48%20epoch.png)

This repository implements a CycleGAN for unpaired image-to-image translation between real-world photos and Monet-style paintings. The main objective of the project is to generate images in the artistic style of Claude Monet, using real photos as input — without requiring paired training data. It includes two generator architectures for style translation:

* UNet-based generator - A skip-connection-based encoder–decoder model commonly used in segmentation and image-to-image tasks, Adapted from a [Kaggle notebook](https://www.kaggle.com/code/chongzhenjie/photo-to-monet-cyclegan-pytorch-lightning/notebook) by Chong Zhen Jie

* ResNet-based generator with Color-Texture Disentangled Attention (CTDA) - Our implementation, enhances translation quality by separating color and texture information using attention mechanisms.

The models are trained using PyTorch Lightning with adversarial, cycle-consistency, and identity losses (as in the original CycleGAN), and evaluated using MiFID (Memorization-Informed FID).

## Project Structure
Code was written in python notebook:

* notebooks/  
    * Plots.ipynb  
    * Main.ipynb

## Loading Checkpoints
Our script loads checkpoint from Google Drive.  
For minimal code changes: 
1. create your own folders "ColabCheckpoints/monet_cyclegan"
2. download the checkpoints from [our Google Drive](https://drive.google.com/drive/folders/1wWX0MJEezo3Ze0y4bDcaDklIocIji7jb?usp=sharing)
3. move the files to the directory you created

## Requirments
All installations included in the submission notebook, including dataset downloading.  
Make sure you have a Kaggle.json key needed for the download.

## Reference
* [CycleGAN with Unet based generator](https://www.kaggle.com/code/chongzhenjie/photo-to-monet-cyclegan-pytorch-lightning/notebook) by Chong Zhen Jie
* [CycleGAN paper](https://arxiv.org/abs/1703.10593)
* [Asymmetric CycleGAN for Unpaired Image-to-Image Translation Based on Dual Attention Module](https://ieeexplore.ieee.org/document/9695748) by Yiwei Sheng
