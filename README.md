# Nature-Images-Classification

## Objective 
To build a model for Intel Image classification challenge dataset.

## About the dataset
- The Intel Image Classification dataset was initially published on https://datahack.analyticsvidhya.com by Intel to host a Image classification Challenge. This dataset can now be downloaded from
  > https://www.kaggle.com/puneet6060/intel-image-classification/version/2.

- The dataset consists of a total 24,335 images of Natural Scenes around the world belonging to 6 categories - 
  1. buildings
  2. forests
  3. glacier
  4. mountain
  5. sea
  6. street

 ![imagedemo](https://user-images.githubusercontent.com/45910651/122985890-564aff00-d3bc-11eb-876f-526fdcad1636.png)

- The dataset is divided into three sets - 
  - Train(`seg_train` folder) - 14,034 images, 
  - Test(`seg_test` folder) - 3,000 images, 
  - Prediction(`seg_pred` folder) - 7,301 images.
- The class distribution of the train and test sets are summarized in the below table. The prediction set is unlabeled.

|           | buildings | forests | glacier | mountain |  sea  | street |
|     -     | --------- | ------- | ------- | -------- |  ---  | ------ |
| **Train** |    2191   |   2271  |   2404  |   2512   | 2274  | 2382   |
| **Test**  |    437    |   474   |   553   |   525    | 510   | 501    |

- Although the images are organized into their respective folders based on their class, some images have scenes which can be classified into more than one class. For example, many images of street class have buildings somewhere in the image.  

## Libraries Used
- TensorFlow
- Matplotlib
- Numpy
- zipfile
- datetime
- os

## Model Used
Created a ResNet based mini model with the architecture as shown below:-
![image](https://user-images.githubusercontent.com/45910651/122986228-cbb6cf80-d3bc-11eb-8bb4-8735b8448cc4.png)

## Model Training
Trained the model with Adam optimizer with an initial learning rate of `1e-3`. Stopped the training when accuracy reached 85% as it is a decent accuracy for this dataset. Special care was taken to prevent overfitting as reflected in below training and validation curves:-

![image](https://user-images.githubusercontent.com/45910651/122989115-1259f900-d3c0-11eb-85dc-a3fd7c04f25c.png)

## Performance of the trained model
The below table shows the loss and accuracy metrics on the train and test sets.
|           | Loss      | Accuracy | 
|     -     | --------- |  ------- |
| **Train** |  0.5067   |  0.8452  |  
| **Test**  |  0.4790   | 0.8533   |

## Visualizing performance on the test set
![image](https://user-images.githubusercontent.com/45910651/122990192-4d106100-d3c1-11eb-8782-a988daa1c898.png)
The *green* label indicates correctly classified and *red* label indicates wrongly classified images. 

## Applying the model on prediction set
![image](https://user-images.githubusercontent.com/45910651/122990521-aa0c1700-d3c1-11eb-9497-2627b8129c37.png)
The model classifies most images in the prediction set correctly if one tries to label the image manually.

## Conclusion
Successfully designed and trained a convolutional network to achieve above 85% test accuracy for the Nature-Scenes-Classification dataset.

## Future Plans
- Make a better classifier for the dataset using more complex architectures.
- Apply Transfer Learning  approach to more accurate classifier for this dataset. 
