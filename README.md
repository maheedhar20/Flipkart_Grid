# Flipkart Grid Robotics Challenge
## 1. Freshness Detection
This model predicts Freshness Index based on the image uploaded. The training process involves the use of a preprocessed dataset and a custom Convolutional Neural Network (CNN) architecture based on the MobileNetV2 model.
We use this model as the base and freeze its layers to prevent them from being modified during our training process. On top of the MobileNetV2 model, we add additional layers to fine-tune the model for our specific freshness classification task.
We achieved an accuracy of 97.87% on training dataset and 96.85% on validation dataset.

### Model Architecture:
![image](https://github.com/user-attachments/assets/8de71ce7-f07b-4a19-8f8b-7372b8e29800)

### Few Outputs:
![image](https://github.com/user-attachments/assets/1f9641c3-bc1a-49cd-9402-af8d3b667339)
![image](https://github.com/user-attachments/assets/8b76716e-7a07-4d7d-b13a-9f6e2b035d05)
![image](https://github.com/user-attachments/assets/d2c47c16-fa6f-465b-a547-bffea9d77d70)

## 2. Expiry Date Extraction
We started with an image compression with the help of Principal Component Analysis.
As a first step, we have performed image classification of the grocery images in our dataset. For training, we have used Transfer Learning where the weights of the classification neural network are obtained from ResNet50 model trained on the ImageNet dataset. This to determine whether the product expires or not.
Once we have the image classified, the next step would be to detect the probable bounding box of expiry date for a packed product and then extract the data from the bounding box. We used VGG16 Architecture for Bounding box Regression.
We have the coordinates of bounding boxes. We then crop the image to get the Region of Interest and converted the image to grayscale, then resized our image and applied morphological transforms to enhance the contrast of the pixels of the image. We then used EasyOCR to get the text from the image.

![image](https://github.com/user-attachments/assets/38725021-a52d-4544-a1eb-be8049282251)

## 3. Brand Recognition and Product Details Extraction
For recognising the brand of the product and extraction of other details like Price, Product name, manufacturer, we used Tesseract OCR to extract text from images and then used NLP techniques to further extarct specific product information from 
the OCR extracted text.

![image](https://github.com/user-attachments/assets/a583a6ff-50de-47a0-ba74-653fcbd26165)

## 4. Counting number of Objects from images
For count detection, we have used Image Segmentation methods. We applied various Contrast adjusting techniques, Segmenting techniques like dilatation and erosion. 
After applying all the preprocessing and segmentation techniques, we counted number of connected components to detect the number of objects.

![image](https://github.com/user-attachments/assets/b2768a79-9d2e-40f5-aaf3-fd01de41f903)

![image](https://github.com/user-attachments/assets/01b2b505-23bf-4239-ae7f-5fb09fd6a474)







