## Cross-Domain Car Detection Using Unsupervised Image-to-Image Translation: From Day to Night

[Vinicius F. Arruda](https://viniciusarruda.github.io/), [Thiago M. Paixão](https://sites.google.com/view/thiagopx), [Rodrigo F. Berriel](http://rodrigoberriel.com), [Alberto F. De Souza](https://inf.ufes.br/~alberto), [Claudine Badue](https://www.inf.ufes.br/~claudine/), [Nicu Sebe](http://disi.unitn.it/~sebe/) and [Thiago Oliveira-Santos](https://www.inf.ufes.br/~todsantos/home)

Published in [IJCNN](https://www.ijcnn.org/) 2019 Conference: [10.1109/IJCNN.2019.8852008](https://doi.org/10.1109/IJCNN.2019.8852008)

The preprint version can be accessed [here](https://arxiv.org/abs/1907.08719).



![Method Overview](https://github.com/viniciusarruda/cross-domain-car-detection/blob/master/images/methodoverview.png)

#### Abstract

Deep learning techniques have enabled the emergence of state-of-the-art models to address object detection tasks. However, these techniques are data-driven, delegating the accuracy to the training dataset which must resemble the images in the target task. The acquisition of a dataset involves annotating images, an arduous and expensive process, generally requiring time and manual effort. Thus, a challenging scenario arises when the target domain of application has no annotated dataset available, making tasks in such situation to lean on a training dataset of a different domain.
Sharing this issue, object detection is a vital task for autonomous vehicles where the large amount of driving scenarios yields several domains of application requiring annotated data for the training process.
In this work, a method for training a car detection system with annotated data from a source domain (day images) without requiring the image annotations of the target domain (night images) is presented. 
For that, a model based on Generative Adversarial Networks (GANs) is explored to enable the generation of an artificial dataset with its respective annotations. The artificial dataset (fake dataset) is created translating images from day-time domain to night-time domain. The fake dataset, which comprises annotated images of only the target domain (night images), is then used to train the car detector model. Experimental results showed that the proposed method achieved significant and consistent improvements, including the increasing by more than 10% of the detection performance when compared to the training with only the available annotated data (i.e., day images).

---

### Source-code

#### CycleGAN

The source code used for the CycleGAN model was made publicly available by [Van Huy](https://github.com/vanhuyz/CycleGAN-TensorFlow).

#### Faster R-CNN

The source code used for the Faster R-CNN model was made publicly available by [Xinlei Chen](https://github.com/endernewton/tf-faster-rcnn).

For training the Faster R-CNN, a pre-trained resnet-101 model was used to initializate the process an can be downloaded [here](http://download.tensorflow.org/models/resnet_v1_101_2016_08_28.tar.gz).

---

### Trained Models

#### CycleGAN

The trained model used in this paper is available [here](https://drive.google.com/drive/folders/17CJ5-cOK2CteZTPtRaT7rfW8oSt38CCe?usp=sharing).

#### Faster R-CNN

The trained models used in this paper are available [here](https://drive.google.com/drive/folders/1XRtExg-QGVA-DFJ1EKf8L0GLCxe5wIqH?usp=sharing).

---

### Dataset

#### Berkeley Deep Drive Dataset

##### Dataset Acquisition

Download the Berkeley Deep Drive dataset [here](https://bdd-data.berkeley.edu/).
It is only necessary to download the Images and Labels files.

##### Dataset Filtering

After downloading the BDD dataset, the Images and Labels will be placed into the zipped files `bdd100k_images.zip` and `bdd100k_labels.zip` respectively. In the same directory, place the provided source code `filter_dataset.py` from this repository with the folder `lists`.

On the terminal, run: `python filter_dataset.py`.
It will take a few minutes, and at the end, the folder `images` and `labels` will contain the images and bounding boxes of the images respectively. 

#### Generated (Fake) Dataset

Available [here](https://drive.google.com/drive/folders/1ZoXfgpTT1N5eOsI4-Tcv0id3mqij5gsP?usp=sharing).

---

### Videos

Videos demonstrating the inference performed by the trained Faster R-CNN model which yielded the best results with our proposed system.

 Testing on Day+Night Dataset | Testing on Night Dataset 
:-------------------------:|:-------------------------:
[![Video1](https://github.com/viniciusarruda/cross-domain-car-detection/blob/master/images/day_plus_night_video_overview.png)](https://youtu.be/qENxVuUXa0s) Inferences performed on day+night dataset |  [![Video2](https://github.com/viniciusarruda/cross-domain-car-detection/blob/master/images/night_video_overview.png)](https://youtu.be/MqZ2I-h_FOA) Inferences performed on night dataset 

---
<!--
#### Copyright
&copy; 2019 IEEE. Personal use of this material is permitted.  Permission from IEEE must be obtained for all other uses, in any current or future media, including reprinting/republishing this material for advertising or promotional purposes, creating new collective works, for resale or redistribution to servers or lists, or reuse of any copyrighted component of this work in other works.
---
-->

### BibTeX

    @inproceedings{arruda2019ijcnn,
      author={Vinicius F. Arruda, Thiago M. Paixão, Rodrigo F. Berriel, Alberto F. De Souza, Claudine Badue, Nicu Sebe and Thiago Oliveira-Santos},
      booktitle={2019 International Joint Conference on Neural Networks (IJCNN)},
      title={Cross-Domain Car Detection Using Unsupervised Image-to-Image Translation: From Day to Night},
      year={2019},
      doi={10.1109/IJCNN.2019.8852008},
      ISSN={2161-4407},
      month={July}
    }

