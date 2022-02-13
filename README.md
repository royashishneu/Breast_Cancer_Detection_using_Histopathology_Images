# <p align="center">Breast Cancer Detection using Histopathology Images</p>
<p align="center"> 
<a href="https://www.linkedin.com/in/roy-ashish">
<img alt="linkedin" src="https://img.shields.io/badge/-Ashish Roy-blue?style=flat&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/roy-ashish"></a>
<img src="https://img.shields.io/badge/Version-1.0.2-blue" />
<img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" target="_blank" />
<img src="https://img.shields.io/badge/Python-100%25-yellow?style=flat&logo=python&logoColor=yellow" />
</p>

## Motivation

Invasive ductal carcinoma (IDC) is - with ~ 80 % of cases - one of the most common types of breast cancer. It's malicious and able to form metastases which makes it especially dangerous. Often a biopsy is done to remove small tissue samples. Then a pathologist has to decide whether a patient has IDC, another type of breast cancer or is healthy. In addition sick cells need to be located to find out how advanced the disease is and which grade should be assigned. This has to be done manually and is a time consuming process. Furthermore the decision depends on the expertise of the pathologist and his or her equipment. Therefor deep learning could be of great help to automatically detect and locate tumor tissue cells and to speed up the process. In order to exploit the full potential one could build a pipeline using massive amounts of tissue image data of various hospitals that were evaluated by different experts. This way one would be able to overcome the dependence on the pathologist which would be especially useful in regions where no experts are available.

## Our Goal

Our goal here is to develop a Deep Learning Model which can determine if the lump is cancerous or not without having to perform a biopsy or replying on the doctor's expertise.

## Background Info - What is Invasive Ductal Carcinoma? <img align='right' src="https://github.com/royashishneu/Breast_Cancer_Detection_using_Histopathology_Images/blob/main/504px-Lobules_and_ducts_of_the_breast.jpg" width="190">

This illustration created <a href = "https://commons.wikimedia.org/wiki/File:Lobules_and_ducts_of_the_breast.jpg">Mikael Häggström</a> shows the anatomy of a healthy breast. One can see the lobules, the glands that can produce milk which flews through the milk ducts. Ductal carcinoma starts to develop in the ducts whereas lobular carcinoma has its origin in the lobules. Invasive carcinoma is able to leave its initial tissue compartment and can form metastases.

Link to <a href="https://colab.research.google.com/drive/1MIfyYIkWc6w6J3zQ2lobkzAT5jZ-E22O?usp=sharing">Google Colab Notebook</a>

## Installation

Use the package manager pip or homebrew to install any necessary packages for your environment if you are running on local machine.

```bash
pip install glob
```
OR
```bash
brew install glob
```
## Packages Used

```python
import warnings
warnings.filterwarnings("ignore", category=DeprecationWarning)
warnings.filterwarnings("ignore", category=UserWarning)
warnings.filterwarnings("ignore", category=FutureWarning)

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
%matplotlib inline
import seaborn as sns
sns.set()
import random
from PIL import Image
from glob import glob
from skimage.io import imread
import os
from google.colab import files

from tqdm import tqdm_notebook as tqdm

import keras_preprocessing.image as im
from keras.models import Sequential
from keras.wrappers.scikit_learn import KerasClassifier
from keras.layers import Dense, Dropout, Activation, Flatten, BatchNormalization, Conv2D, MaxPool2D, MaxPooling2D

from tensorflow.keras import Sequential
from tensorflow.keras.optimizers import SGD, RMSprop, Adam, Adagrad, Adadelta
from tensorflow.keras.callbacks import EarlyStopping

from sklearn.model_selection import train_test_split
from sklearn.model_selection import GridSearchCV
from sklearn.metrics import confusion_matrix, accuracy_score, roc_curve, auc
from sklearn.preprocessing import StandardScaler
```

## Sample Data
### Healthy Tissues
![image](https://user-images.githubusercontent.com/78773964/153774564-3cce1a38-0d1b-4503-bfea-bbe56bbc01b1.png)

### Cancerous Tissues
![Screen Shot 2022-02-13 at 3 50 40 PM](https://user-images.githubusercontent.com/78773964/153774525-c94d8154-8458-4730-adf2-398f6ecdf362.png)

## Model Evaluation

We used AUC/ROC curve to evaluate the performance

![Screen Shot 2022-02-13 at 3 54 38 PM](https://user-images.githubusercontent.com/78773964/153774670-d00889fe-1dfe-4287-8960-dfbd4cbd9129.png)

## How to Use

```python
# Upload kaggle.json File with Credentials to upload the dataset to your google colab
upload = files.upload()
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
