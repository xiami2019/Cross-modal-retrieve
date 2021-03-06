# Cross-modal-retrieve
By Xiami2019

## Requirements
Python 3.6  
PyTorch 1.1.0  
pytorch-transformers  

## Dataset  
Images and text are from `iaprtc-12` https://www.imageclef.org/photodata  
Labels are from `saiaprtc-12` https://www.imageclef.org/SIAPRdata  
And make a mixture dataset for cross-modal retrieve by simply concatenate the labels, images, text.  
In this dataset, we have 20000 images and their corresponding description both in English and German.  
There are also multi labels for each image-text pair.
Follow the setting in reference paper, I choose 10000 images as train set.  
When testing, I choose 2000 images as query set and the last 18000 images as database.

## Model
The network consists of image model and text model. I use pretrained **Resnet18** as the image model and pretrained **BERT-base** as the text model.

## Objective
Final objective consists of four triplet losses：  
<a href="https://www.codecogs.com/eqnedit.php?latex=F=L_{I\rightarrow&space;T}&plus;L_{T\rightarrow&space;I}&plus;L_{T\rightarrow&space;T}&plus;L_{I\rightarrow&space;I}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?F=L_{I\rightarrow&space;T}&plus;L_{T\rightarrow&space;I}&plus;L_{T\rightarrow&space;T}&plus;L_{I\rightarrow&space;I}" title="F=L_{I\rightarrow T}+L_{T\rightarrow I}+L_{T\rightarrow T}+L_{I\rightarrow I}" /></a>

## Result   
Due to time and device limited, extensive experient has not been executed.  
After about 30 epochs    
**Text→Images**  

language | 16bits | 32bits | 48bits | 64bits  
|:---: |:---: |:---: | :---: |:---: |  
`English` | **To be added** | **0.5005** | **To be added** | **To be added**  
`German` | **To be added** | **0.4947** | **To be added** | **To be added**  

**Images→Text**  

language | 16bits | 32bits | 48bits | 64bits  
|:---: |:---: |:---: | :---: |:---: |  
`English` | **To be added** | **0.4955** | **To be added** | **To be added**  
`German` | **To be added** | **0.4940** | **To be added** | **To be added**  

## Reference  
[1] Xi Zhang, Hanjiang Lai, Jiashi Feng [*Attention-aware Deep Adversarial Hashing for Cross-Modal Retrieval*](http://openaccess.thecvf.com/content_ECCV_2018/papers/Xi_Zhang_Attention-aware_Deep_Adversarial_ECCV_2018_paper.pdf)
