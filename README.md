# Pneumonia-Classification-in-Chest-X-Ray-Images
Classification of Pneumonia vs Normal in the Chest X-Ray Images (Pneumonia) dataset from Kaggle

# **Dataset**
The Chest X-Ray Images (Pneumonia) dataset from Kaggle is a collection of 5,863 chest X-ray images in JPEG format organized into three folders (train, test, val) and two categories (Pneumonia/Normal).
The X-rays were selected from pediatric patients aged one to five years old who received chest X-rays as part of their routine clinical care at the Guangzhou Women and Children's Medical Center in Guangzhou. The images were screened for quality control, and diagnoses were graded by two expert physicians and checked by a third expert to account for any grading errors.
The dataset is designed to be used for developing AI systems to assist in the diagnosis of pneumonia, with the aim of improving patient outcomes.
The X-ray images show clear lungs without abnormal opacification for the Normal category, while the Pneumonia category displays either a focal lobar consolidation for bacterial pneumonia or a diffuse 'interstitial' pattern in both lungs for viral pneumonia.
# References:
1. https://www.cell.com/cell/fulltext/S0092-8674(18)30154-5
2. https://complexity.cecs.ucf.edu/chest-x-ray-images-pneumonia/
3. https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

# **Model Architecture:**
The model I have chosen to implement is ZubinRNet() model inspired by the ResNet model  which was proposed in Deep Residual Learning for Image Recognition by Kaiming He, Xiangyu Zhang, Shaoqing Ren and Jian Sun. [1]
The ResNet model is a good deep learning model for the classification of Pneumonia vs Normal in the Chest X-Ray Images dataset due to its ability to train very deep neural networks with minimal degradation of performance. The ResNet architecture was specifically designed to address the problem of vanishing gradients that can occur in very deep neural networks. The architecture introduces a "skip connection" that allows gradients to be propagated more easily through the network, thus enabling the training of deeper networks.[2,3] ResNet has shown exceptional performance in various image classification tasks, including the ImageNet Large Scale Visual Recognition Challenge (ILSVRC), where it achieved top-5 error rates as low as 3.57%.[4]

# Implementation:
1. The BasicBlock class represents the fundamental building block of the ResNet architecture. It defines a single residual block containing two convolutional layers with Batch Normalization and ReLU activation functions, followed by a residual (skip) connection. The residual connection enables the network to learn the residual function, which is the difference between the input and the output of the block. This design helps to tackle the vanishing gradient problem and allows for more efficient training of deeper networks.
2. The ZubinRNet() combines multiple BasicBlock instances to form the complete network. This class defines the initial convolutional layer, the residual blocks organized in layers, and the final fully connected layer for classification. It also takes care of the forward pass through the entire network, ensuring that the residual connections are properly added to the outputs of their respective blocks.

# References:
1. https://huggingface.co/docs/transformers/model_doc/resnet
2. https://www.mygreatlearning.com/blog/resnet/#:~:text=Using%20ResNet%20has%20significantly%20enhanced,as%20compared%20to%20plain%2D34.
3. https://iq.opengenus.org/residual-neural-networks/
4. https://towardsdatascience.com/review-resnet-winner-of-ilsvrc-2015-image-classification-localization-detection-e39402bfa5d8
