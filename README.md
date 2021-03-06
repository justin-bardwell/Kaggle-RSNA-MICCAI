# RSNA-MICCAI Brain Tumor Radiogenomic Classification

Welcome to our repository for the RSNA-MICCAI Brain Tumor Radiogenomic Classification Kaggle competition! The purpose of this competition is to provide techniques to detect the presence of a specific genetic sequence in brain tumours which has been shown to be a favourable prognostic factor and a strong predictor of responsiveness to chemotherapy. Currently, the genetic analysis of cancer requires surgery to extract a tissue sample. 

## Based on our first meeting, we will likely be using Kaggle initially and then moving to an external cloud provider for this. Due to this, we probably won't need to use this system of GitHub and Colab. We figured it would be worth sharing anyway so people can have a look at some of the data and play around with it in Python if they wish.

## Requirements:
* Web browser
* Github account (you might be able to skip this step now that we've made the repository public)
* Visagio Google account for accessing Google Drive and Colab

## Setup Github access through Google Colab (can also probably skip this now that the repo is public)
1. Navigate to http://colab.research.google.com/github.
2. Click the "Include Private Repos" checkbox.
3. In the popup window, sign-in to your GitHub account and authorize Colab to read the private files.
4. Select the 'Kaggle-RSNA-MICCAI' repository and your personal branch that you previously created.

When you want to commit and push your changes to your branch: <br />
*File > Save a copy in GitHub*

If you would like to create pull requests or merge commits from the main branch into your own branch, it may be necessary to install Git on your computer.

## Google Drive access in Colab:

All data files can be found in the following Google Drive: <br />
***Update for shared drive once it has been fully populated with files*** <br />
https://drive.google.com/drive/folders/1aMKv-GfepkHkpRnZRnxxMJhGezVGClnV?usp=sharing

Opening a file from GitHub in Google Colab should be done by clicking on the button at the top of each .ipynb file <br />
<a href="https://colab.research.google.com/github/justin-bardwell/Kaggle-RSNA-MICCAI/blob/main/Setup_and_EDA.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a> <br /> 
or by using the following link and choosing the file you would like to open <br /> 
http://colab.research.google.com/github

To mount your Google Drive to Colab in order to access the data: <br />
```python
from google.colab import drive
drive.mount('/content/gdrive')
```

You will then need to authorise access to your Google Drive.
![image](https://user-images.githubusercontent.com/80082879/129331539-d32b108c-0bf0-4afc-b34c-6cfec01101c1.png)

And then go to the link provided in the output of the above code block and copy the authorisation code.
![image](https://user-images.githubusercontent.com/80082879/129331692-1372fec3-1b2b-4932-8af4-9b646320f556.png)

You should now be able to see the files in the shared drive in the Files sidebar. <br />
![image](https://user-images.githubusercontent.com/80082879/129332029-f913e66a-a6b9-4643-83e5-4c09c3e59d48.png)


To change your working directory to the shared folder containing our data: <br />
```
%cd /content/gdrive/Shareddrives/Kaggle
```

After the drive is mounted and you have updated your working directory, you can access all of the data in Google Colab.


## Benefits of using Google Colab

Google Colab provides free access to GPUs which are necessary to perform deep learning on image datasets. It also provides extremely fast access to our data stored in Google Drive. The GPUs available in Colab often include Nvidia K80s, T4s, P4s and P100s.

To access a GPU runtime in Google Colab:<br />
*Runtime > Change runtime type > Hardware accelerator: GPU*

Keep in mind that this uses Google's resources that are freely available to anyone using Colab. Please only use a hardware accelerator if you are running a deep learning model. If you are using a GPU runtime when it is not necessary, you will likely be removed from your current session and your runtime will be restarted with no hardware accelerator.


## Overview of data

In Kaggle, we are provided with data which includes four types of whole brain MRI scans (FLAIR, T1w, T1Gd, T2w) for each subject as well as the MGMT promoter methylation status associated with each subject. Methylated cases are marked as '1' and unmethylated as '0' in the data. The task is to predict a probability for the target MGMT value of each subject based on the MRI scans we are provided. Submissions are evaluated on the area under the ROC curve between the predicted probability and the observed target.

The image data in Kaggle has been provided in a common medical imaging format, *DICOM*. The shared Google Drive contains images that have been converted to PNG files in order to save space. This data was taken from Kaggle user Jonathan Besomi's contribution (https://www.kaggle.com/c/rsna-miccai-brain-tumor-radiogenomic-classification/discussion/253000). By using this data, we significantly reduce computational intensivity and storage requirements while only sacrificing minimal amounts of information from our data. The PNG dataset will allow us to train complex deep learning models using the GPUs available on Colab without too many issues. These trained models can then be implemented in Kaggle when required - we just need to slightly alter the way the data is read in to our model to account for the difference in format.

**If you would like to look further in to the data and how we use Google Colab, please have a look at the 'Setup-and-EDA.ipynb' file!**

<br />
<a href="https://colab.research.google.com/github/justin-bardwell/Kaggle-RSNA-MICCAI/blob/main/Setup_and_EDA.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a> <br /> 

![image](https://user-images.githubusercontent.com/80082879/126605042-e771a6c2-65ca-420c-b0bb-6a05b14a8a2b.png)

