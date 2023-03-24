# DrillSize-Classification
This is sideproject  about drill size classification extract from video
## Introduction
This a personal sideproject to practice a extracted image classifcation from video.
Content included two machine learning method to finish this task. 
### ResNet
ResNet is my potential Network. I choose ResNet because I plan to do more layers than VGG to detect the small feature, and ResNet might help me to do it. However, the training time and computational time limit the model performance. The colab GPU couldn’t run for the full dataset. According to the following accuracy plot, the Network shows potential if we feed more data and training epochs. I tried adjusting the learning rate larger because the model moved around the local minimum when I set the learning as 0.001. After the training and experiment, we should consider YOLO as our task model because the YOLO can detect the object, and it will be easier to do the classification when drills are moving in a complex environment.
#### ResNet Result
![image](https://github.com/j217435/DrillSize-Classification/blob/47581d25c1db8283f84e133bc437b12a83dfebc4/Image/Screen%20Shot%202023-03-24%20at%204.58.01%20PM.png)

### Random Forest
Random Forest is a traditioinal mahcine learning and could be used in a classification task. I do the SOBEL operation first to extract the feature and do the random forest training. The traditional machine learning has better classification result than a deep learning method here because of the limited training time and computational resoursed.

#### Image after SOBEL Operation
![image](https://github.com/j217435/DrillSize-Classification/blob/2d807f0055268e040ad3905a9e1e9465cead26d8/Image/Screen%20Shot%202023-03-24%20at%204.58.14%20PM.png)

#### Random Forest Result

The performance of the RF model has an accuracy of 0.62 on the training dataset and 0.59 on the validation dataset. The precision, recall, and f1-score are listed in the following table. From the table, we can see that class 0 and class 5 have abnormal precision and recall. We need to check back the dataset or try different preprocessing method to improve the model performance. 
![image](https://github.com/j217435/DrillSize-Classification/blob/040d49b442a811180d53ae3584b6a9aa444ad401/Image/Screen%20Shot%202023-03-24%20at%204.58.37%20PM.png)

## Example

I implement a predictoutput.exe for testing cases in the command line. Input the image folder path, and you will output the image class and a table for entire folder. The evaluation method and predict exe are written in code ‘RF_train.py’ and ‘PredictOutput.py.’
![image](https://github.com/j217435/DrillSize-Classification/blob/040d49b442a811180d53ae3584b6a9aa444ad401/Image/Screen%20Shot%202023-03-24%20at%204.46.27%20PM.png)
