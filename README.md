# RSNA-MICCAI Brain Tumor Radiogenomic Classification

Welcome to our Visagio repository for the RSNA-MICCAI Brain Tumor Radiogenomic Classification Kaggle competition! The purpose of this competition is to provide techniques to detect the presence of a specific genetic sequence in brain tumours which has been shown to be a favourable prognostic factor and a strong predictor of responsiveness to chemotherapy. Currently, the genetic analysis of cancer requires surgery to extract a tissue sample. 

## Requirements:
* Web browser
* Github account
* Visagio Google account for accessing Google Drive and Colab

***Before getting started with anything and making any changes, please create your own branch of this repo in Github***.

## Setup Github access through Google Colab
1. Navigate to http://colab.research.google.com/github.
2. Click the "Include Private Repos" checkbox.
3. In the popup window, sign-in to your GitHub account and authorize Colab to read the private files.
4. Select the 'Kaggle-RSNA-MICCAI' repository and your personal branch that you previously created.

When you want to commit and push your changes to your branch: <br />
*File > Save a copy in GitHub*

If you would like to create pull requests or merge changes from the main branch into your own branch, it may be necessary to install Git on your computer.

## Google Drive access in Colab:

All data files can be found in the following Google Drive: <br />
***Update for shared drive once it has been fully populated with files*** <br />
https://drive.google.com/drive/folders/1aMKv-GfepkHkpRnZRnxxMJhGezVGClnV?usp=sharing

Opening a file from GitHub in Google Colab should always be done using the following link: <br /> 
http://colab.research.google.com/github

To mount your Google Drive to Colab in order to access the data: <br />
```python
from google.colab import drive
drive.mount('/content/gdrive')
```

To change your working directory to the shared folder containing our data:<br />
```
%cd /content/gdrive/Shareddrives/Kaggle
```

After the drive is mounted and you have updated your working directory, you can access all of the data in Google Colab.


## Benefits of using Google Colab

Google Colab provides free access to very powerful GPUs which are necessary to perform deep learning on image datasets. It also provides extremely fast access to our data stored in Google Drive. The GPUs available in Colab often include Nvidia K80s, T4s, P4s and P100s.

To access a GPU runtime in Google Colab:<br />
*Runtime > Change runtime type > Hardware accelerator: GPU*

Keep in mind that this uses Google's resources that are freely available to anyone using Colab. Please only use a hardware accelerator if you are running a deep learning model. If you are using a GPU runtime when it is not necessary, you will likely be removed from your current session and your runtime will be restarted with no hardware accelerator. If this happens multiple times, it is possible that your rights to use a GPU for free are revoked by Google.

If you do not need to do anything computationally intensive or have your own powerful computer, feel free to use your own development environment to access the notebook files. To access the data using your own IDE, you will need to download the dataset to your own storage.<br />


## Overview of data

In Kaggle, we are provided with data which includes four types of whole brain MRI scans (FLAIR, T1w, T1Gd, T2w) for each subject as well as the MGMT promoter methylation status associated with each subject. Methylated cases are marked as '1' and unmethylated as '0' in the data. The task is to predict a probability for the target MGMT value of each subject based on the MRI scans we are provided. Submissions are evaluated on the area under the ROC curve between the predicted probability and the observed target.

The image data in Kaggle has been provided in a common medical imaging format, *DICOM*. The shared Google Drive contains images that have been converted to PNG files in order to save space. This data was taken from Kaggle user Jonathan Besomi's contribution (https://www.kaggle.com/c/rsna-miccai-brain-tumor-radiogenomic-classification/discussion/253000). By using this data, we significantly reduce computational intensivity and storage requirements while only sacrificing minimal amounts of information from our data. The PNG dataset will allow us to train complex deep learning models using the GPUs available on Colab without too many issues. These trained models can then be implemented in Kaggle when required - we just need to slightly alter the way the data is read in to our model to account for the difference in format.

**If you would like to look further in to the data and how we use Google Colab, please have a look at the 'Setup-and-EDA.ipynb' file!**

![image](https://user-images.githubusercontent.com/80082879/126605042-e771a6c2-65ca-420c-b0bb-6a05b14a8a2b.png)

