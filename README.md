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
*File > Save a copy in GitHub*. 

If you would like to create pull requests or merge changes from the main branch into your own branch, it may be necessary to install Git on your computer.

## Google Drive access in Colab:

All data files can be found in the following Google Drive: <br />
***Update for shared drive once it has been fully populated with files*** <br />
https://drive.google.com/drive/folders/1aMKv-GfepkHkpRnZRnxxMJhGezVGClnV?usp=sharing

To mount your Google Drive to Colab in order to access the data: <br />
```python
from google.colab import drive
drive.mount('/content/gdrive')
```

To change your working directory to the shared folder containing our data:<br />
```python
%cd /content/gdrive/Shareddrives/Kaggle
```

After the drive is mounted and you have updated your working directory, you can access all of the data in Google Colab.
