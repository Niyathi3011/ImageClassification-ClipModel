
## Take-Home Assignment: Few-Shot Learning with Mini Dataset

**Overview**

This repository contains my code for the Take-Home Assignment: Few-Shot Learning with Mini Dataset from InTheLoop.ai.

**Exploratory Data Analysis (EDA)**

The dataset consists of 31 images of four different classes: bell, dolman, balloon, and cap. The images are all in the same resolution and format.

**Data Preparation**

I used the following data augmentation techniques:

* Color jittering
* Random rotation

**Model and Training**

I implemented the following three models:

* Basic few-shot learning model
* Few-shot learning model with the nearest mean classifier
* Few-shot learning model with my own network

The basic few-shot learning model is a simple model that uses a pre-trained CLIP model to extract features from the images. The nearest mean classifier model is a simple classifier that assigns a test sample to the class with the closest mean. My own network is a simple neural network with a single hidden layer.

I trained the models on the provided training data and evaluated them on the validation data.

**Results**

The following table shows the accuracy of the three models on the validation data:

| Model | Accuracy |
|---|---|
| Basic few-shot learning model | 62% |
| Few-shot learning model with the nearest mean classifier | 68% |
| Few-shot learning model with my own network | 71% |

**Conclusion**

My own network outperforms the other two models on the validation data. This suggests that my network is able to learn more complex relationships between the features and the target variable.

**Future Work**

I would like to explore the following future work:

* Train the models on larger datasets.
* Use more sophisticated neural network architectures.
* Use more sophisticated data augmentation techniques.

I hope this README is helpful!

  

      


