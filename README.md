# Modified Xception model for classification and detection of Breast Cancer 

This github repositories presents a modified Xception architecture for detection and classification of breast Cancer. The Xception architecture has an input shape of 224 x 224 x 3. The mammogram that needs to be classified is of shape more than 4000 X 2000. So instead of reshaping the mammogram as reshaping would seriously compromise with the quality of the input images, we extracted the ROIs containing the mass and used the modified Xception architecture to exctract features. Example of a ROI extracted is shown below,


<img src="https://github.com/sagardeepdeb/rahman_xception_global/blob/main/enhanced_dataset/benign/Mass-Test_P_00099_LEFT_MLO_ROI_Mass_B_1.png%20.png" alt="(b)" width="200" height="200"> <img src="https://github.com/sagardeepdeb/rahman_xception_global/blob/main/enhanced_dataset/benign/Mass-Test_P_00278_RIGHT_MLO_ROI_Mass_B_1.png%20.png" alt="alt text" width="200" height="200"> <br/> Some examples of Benign ROIs (After Pre-processing)


<img src="https://github.com/sagardeepdeb/rahman_xception_global/blob/main/enhanced_dataset/malignant/Mass-Test_P_00324_RIGHT_MLO_ROI_Arch_M_1.png%20.png" alt="(a)" width="200" height="200"> <img src="https://github.com/sagardeepdeb/rahman_xception_global/blob/main/enhanced_dataset/malignant/Mass-Test_P_00514_LEFT_MLO_ROI_Mass_M_1.png%20.png" alt="alt text" width="200" height="200"> <br/> Some examples of Malignant ROIs(After Pre-processing)

We have tried to design a classification framework by a modified Xception architecture. Xception network is choosen as the backbone network for deep feature extraction. This architecture is composed of three different components; the inception module, depthwise separable convolution layers and residual blocks. Later on the extracted features from the modified Xception network is provided to a stacked ensemble bases ANN classifier. To achieve this, first, we omit the top layer of the Xception network to transfer pre-trained knowledge from ImageNet dataset and then concatenate features extracted from intermediate CNN layers. This is the main difference between our method and the original Xception architecture. Also, in the Xception architecture, the standard convolutional layers are replaced with depthwise separable convolution layers that help to reduce the computational complexity, which is useful when implementing real-time applications. In addition to the modified Xception deep extractor for this task, we employed the min-pooling [16] image pre-processing technique to aid in the features extraction and further improve the classification performance
The model of our modified Xception arcitecture is shown in figure below.
![Figure 5](https://github.com/sagardeepdeb/rahman_xception_global/blob/main/model.PNG)

For classification we have used Deep learning based ensemble classifier. Initially the features were extracted using the modified Xception Network as shown in the figure. Later on the extracted features were provided to the stacked ensemble classifier. We have used 5 different ANN classifiers to form the stacked ensemble classifier. The performance of the five individual ANN classifier and the stacked classifier is given in the table below.

Sl no. of the classifier | Performance
------------ | -------------
<p align="center">
    // 1
</p> | 76.90
2 | 80.5
3 | 80.9
4 | 74.2
5 | 80.0
__Stacked Ensemble Classifier__ | __84.30__

As shown in the table above, the strategy employed by us provided better results.


# References 

The codes are heavily inspired from the following repositories.


1 ) https://github.com/sara-kassani/APTOS-2019/blob/master/APTOS_MultiClass_Ben_noAug_Xception_modified_ML_without_LGBM.ipynb <br/>
2 ) https://machinelearningmastery.com/stacking-ensemble-for-deep-learning-neural-networks/
