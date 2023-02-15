# Object Localisation(From Scratch)
Create and build a model(from scratch) to detect a simple bounding box  i.e build a regression head on Oxford IIT Data set



## Objective of this notebook
- The purpose of this notebook is to build a model to detect a simple bounding box 
- Details of the **problem statement**  , **data set** ,  **summary of the code/solution**  , **sample output/Prediction** from the program and **final result** of the project are listed in the sections to follow.

## Problem Statement 
Build a model to detect a single Bounding Box on a pet image 


## Data Description:
 - Data Set :Oxford IIT Pet Data 
 - Link : https://www.robots.ox.ac.uk/~vgg/data/pets/


## Summary of the Solution/Code:
The code aims at building a simple bounding  box to detect the animal's face 
- We begin by building a utility class to to read the input images ,convert them to a structured format for further processing and model building and pickle the created input data files Code @ **Read_& Structure_Input.ipynb**
- We then do an EDA on the data and  check various statistics on the images such as total no of images , whether classes are balanced and display a few images with their bounding boxes for visulaization . Code @ **EDA.ipynb**
- We will then we will pre-process the input data to make it compatible for model building wherein we first do a Train-Test split and create 2 subsets (70:30 split), convert all images to tensors for both subsets,resize all the images to one pre-defined size, convert bounding boxes accordingly ,visualize data and see that everything looks good. Code @ **Pre-Processing_Data.ipynb**
- Finally we build the model, train the model , log the results and run an inference.We will build a model that is capable of detecting a bounding box on the image -i.e object localisation.We will try 3 different variants of the model. One variant is we will  build a Convolution Neural Network from SCRATCH ,train it & capture results.The second variant is we will  build an image classifier converted into an object detector i.e a pre-trained MobileNet base with a basic top layer re-built, re-trained and log results.The third is we will then try a model with pre-trained MobileNet base and a slightly more sophisticated  top layer re-built, re-trained and log results .We compare and contrast score , pick the best model and run an inference. Code @ **Train_And_Inference.ipynb**



## Sample Ouput/Prediction :
Here is a sample Ouput image from  the program/model 

![image](https://user-images.githubusercontent.com/68383273/218255711-0d275632-a9c4-4ed7-bd8e-a7bc3177f5c5.png)



## Result

- 3 Different models were tried to build the regression head/ bounding box
- A model with pre-trained mobile Net base with a basic top layer reconstructed gave the best results of validation IOU of .96 in 30 epochs
- A model with pre-trained mobile Net base with a more complex top layer reconstructed gave us a result of .8372 in 30 epochs . Further training could possible give us hihger numbers
- A 6 layer deep CNN model built from scratch gave us a result of .5295 in 30 epochs . Further training could possible give us higher numbers.
- The best model is model no 1( model with pre-trained mobile Net base with a basic top layer reconstructed)

## References & Guidance
- PGP GL/UAT study material 
- https://colab.research.google.com/github/zaidalyafeai/Notebooks/blob/master/Localizer.ipynb

