# Modified Xception model for classification and detection of Breast Cancer 

This github repositories presents a modified Xception architecture for detection and classification of breast Cancer. The Xception architecture has an input shape of 224 x 224 x 3. The mammogram that needs to be classified is of shape more than 4000 X 2000. So instead of reshaping the mammogram as reshaping would seriously compromise with the quality of the input images, we extracted the ROIs containing the mass and used the modified Xception architecture to exctract features. 

The model of our modified Xception arcitecture is shown in figure 1.
![Figure 1](https://github.com/sagardeepdeb/rahman_xception_global/blob/main/model.PNG)

For classification we have used Deep learning based ensemble classifier. Initially the features were extracted using the modified Xception Network as shown in the figure. Later on the extracted features were provided to the stacked ensemble classifier. We have used 5 different ANN classifiers to form the stacked ensemble classifier. The performance of the five individual ANN classifier and the stacked classifier is given in the table below.

No. of ANN classifier | Performance
------------ | -------------
1 | 76.90
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
