# EC601_Mini_Project_2

This goal of this application is image classification. The application was developed using Python (v3) in Google Colaboratory. The Keras and Tensorflow frameworks were used for development. The application was tested using images of money. The application then classifies the image and predicts whether it is of cash or coins using two different models. The images were tagged using Neurala BrainBuilder and the dataset was exported from there.

**Dataset**
---
The dataset consisted of a total of 212 images and was split up accordingly:
1. Training: 181 Images
2. Validation: 23 Images
3. Test: 23 Images

Note: The orignal dataset contained 106 images, but FlipImages.ipynb was used to flip each image, which double the size of the dataset.

**How to Run Application**
---
1. Download the dataset from this repository
2. Open EC601_Mini_Project_2.ipynb in Google Colaboratory
3. Run EC601_Mini_Project_2.ipynb in Google Colaboratory
4. When you run the application, you will be prompted to upload the dataset (both the images and their labels), therefore you will be prompted 6 times (training, validation and test). Browse to the location of each dataset and upload the correct images and labels.
5. Let the program continue to run, as it runs you will see accuracy calculations after each epoch for each of the two models.

**File Descriptions**
---
1. **OriginalImages/:** This folder contains all of the original images (106 images), before they were flipped. 
2. **dataset/:** This folder contains the dataset that was used to train the models in the application. Inside this folder, there are three other folders: test/, train/, and validation/. Inside each of these folders there are two other folders: images, and labels. These contain the files that are uploaded to Google Colaboratory using the EC601_Mini_Project_2.ipynb file.
3. **FlipImages.ipynb:** This file uploads a set of images, flips them, then saves those flipped images with a new filename.
4. **EC601_Mini_Project_2.ipynb:** This file contains the models that are used for image classification. It first does some preprocessing on the images and extracts the pixel arrays from the images and creates arrays for the labels of each image. A model is then built, compiled, and trained. Then it predicts the classification of the set of test images.
5. **Results_Model1.txt:** This is a text file that contains the output of the training of Model1.
7. **Results_Model2.txt:** This is a text file that contains the output of the training of Model2.

**Results**
---
The first model had a validation accuracy of 0.8696 at the end of the last epoch. I also noticed that the validation loss was larger than the training loss, at the last epoch these were the results: loss: 5.9044e-06 - acc: 1.0000 - val_loss: 0.3973 - val_acc: 0.8696. This may be the result of overfitting. Originally, I was getting a validation accuracy of ~0.70. I ended up adding another convolution layer, and although training time did increase considerably the validation accuracy did increase as well.
The second model also had a validation accuracyy of 0.8696 at the end of the last epoch. The second model had two addtional layers that the first model didn't have: a max pooling layer and a dropout layer. The dropout layer was added because of the overfitting in the first model. It seems that dropout layers should help to prevent overfitting from occurring. And, based on the validation losses and the training losses, it seems that it did help to prevent overfitting. The results at the end of the last epoch for this model were: loss: 6.6081e-04 - acc: 1.0000 - val_loss: 0.3022 - val_acc: 0.8696. So from these results, we can see that the difference between the validation losses and the training losses was smaller than the difference in the first model. This model also took slightly less time to train the the first model. For more information see Results_Model1.txt and Results_Model2.txt.
