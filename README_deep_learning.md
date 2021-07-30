## Deep Learning in Medical Imaging

Please feel free to have a look at some of the below links for a brief overview of some of the currently used deep learning models used in the field of medical imaging.

### Overview of commonly used CNN architectures in medical imaging.
https://www.imaios.com/en/Company/blog/Classification-of-medical-images-the-most-efficient-CNN-architectures <br />
The ResNet, DenseNet, EfficientNet, Inception and Xception architectures are well-known and widely used CNNs. You can easily access pre-trained models of these online and implement them quickly.

For example, if you wanted to download pre-trained models for EfficientNetV2, you can do that here:<br />
https://github.com/google/automl/tree/master/efficientnetv2


### Research papers using CNNs for medical imaging purposes:
#### For brain MRI segmentation:
Kamnitsas et al., Efficient multi-scale 3D CNN with fully connected CRF for accurate brain lesion segmentation, 2017<br />
https://www.sciencedirect.com/science/article/pii/S1361841516301839 <br />
Uses a 3D CNN for brain segmentation. This might be useful for this Kaggle competition. Segmentation of the tumour prior to classification may improve performance greatly.

#### For classification:
S. Deepak, P.M. Ameer, Brain tumor classification using deep CNN features via transfer learning, 2019 <br />
https://www.sciencedirect.com/science/article/abs/pii/S0010482519302148 <br />
Uses a pre-trained GoogLeNet (Inception v1) to extract features from brain MRI images.

### Transformers

The use of transformers in medical imaging is relatively new and quite exciting. See the below link for a brief overview <br />
https://techblog.ezra.com/transformers-in-medical-computer-vision-643b0af8fc41

This recently published paper written by Dai, Y and Gao, Y demonstrates the use of a hybrid transformer-CNN model with promising results.
It was demonstrated that combining ResNet CNN architectures with DeiT transformers produced more accurate models than using solely ResNet or ConvNet. <br />
https://arxiv.org/pdf/2103.05940.pdf

DeiT: Data-efficient Image Transformers <br />
https://github.com/facebookresearch/deit <br />
This is Facebook's public repository for the DeiT and CaiT models. Here you can find pre-trained transformers that can be implemented for image classification purposes. 
