# Modified Xception model for classification and detection of Breast Cancer 

This github repositories presents a modified Xception architecture for detection and classification of breast Cancer. The Xception architecture has an input shape of 224 x 224 x 3. The mammogram that needs to be classified is of shape more than 4000 X 2000. So instead of reshaping the mammogram as reshaping would seriously compromise with the quality of the input images, we extracted the ROIs containing the mass and used the modified Xception architecture to exctract features. 

The model of our modified Xception arcitecture is shown in figure 1.
![Figure 1](https://github.com/sagardeepdeb/rahman_xception_global/blob/main/model.PNG)
