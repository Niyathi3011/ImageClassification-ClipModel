# TakeHomeAssignment-InTheLoop.ai
Take-Home Assignment: Few-Shot Learning with Mini Dataset  

1. Exploratory Data Analysis (EDA):
Inspect the dataset.
Visualize sample images from each class.

2. Prepare the data for few-shot learning.
Prepare the data for few-shot learning.
Implement necessary data augmentation techniques to improve the model’s performance.
getTransform function: This function takes a clip_transform (which is likely another transformation function) and returns a composite transformation that includes color jittering, random rotation, and the provided clip_transform. This is useful for augmenting and preprocessing images before they are fed into a model, commonly used in computer vision tasks to improve model robustness.

3. Model and Training :
   i. Method 1 :
   
      image and label are unpacked from the batch. image likely represents the images, and label represents their corresponding ground truth class labels.

      The image tensor is moved to the specified device (e.g., GPU) using image = image.to(device) for efficient processing on the available hardware.
      
      image_features are extracted from the model using model.encode_image(image).float(). This suggests that the model has an image encoder that extracts features from the input image.
      
      Similarity scores between the image features and text features are computed. It appears that the model can associate images with text descriptions. The similarity computation is 
      done using dot products and softmax normalization:
      
      similarity = (100.0 * image_features @ text_features.T).softmax(dim=-1)
      
      This line calculates the similarity scores between image features and text features, scaled by 100.0 and applying softmax along the last dimension (-1).

   ii. Nearest Class Mean (NCM)
      Here's a short description of the provided code:

      Net class: This is a PyTorch neural network module defined with a constructor __init__ and a forward method. It's a simple feedforward network with one linear layer followed by a 
      log-softmax activation. This network takes an input feature vector of size in_feat and produces an output feature vector of size out_feat.
      
      load_imgs function: This function loads images from a folder specified by path_to_folder, applies a series of transformations to each image using the provided transform function, 
      and returns the transformed images as a torch tensor. It uses the Python Imaging Library (PIL) to open and manipulate image files and then stacks them into a tensor.
      
      getTransform function: This function takes a clip_transform (which is likely another transformation function) and returns a composite transformation that includes color 
      jittering, random rotation, and the provided clip_transform. This is useful for augmenting and preprocessing images before they are fed into a model, commonly used in computer 
      vision tasks to improve model robustness.
      
      In summary, this code defines a neural network model (Net class), provides a function to load and preprocess images (load_imgs), and offers a way to create a composite image 
      transformation (getTransform) for data augmentation and preprocessing.

   iii.Training using train and validation datasets:

        It is a neural network model for a certain number of epochs (defined as num_epochs, which is set to 100).
        The code uses a DataLoader to load and batch data from the validation dataset (dataset_val) and sets the batch size to 32.
        Inside the training loop (for each epoch), the following steps occur:
        Training Phase:
        It iterates through the training DataLoader (dataloader) to process batches of image-label pairs.
        Images are transformed (likely using CLIP-specific transformations), moved to the specified device (e.g., GPU), and passed through the CLIP model to obtain image features.
        The neural network (net) is trained to predict class labels based on the image features.
        Loss is computed and backpropagated to update model parameters.
        Training loss for the epoch is accumulated.
        Validation Phase:
        It iterates through the validation DataLoader (dataloader_val) to evaluate the model's performance on the validation dataset.
        Similar to the training phase, images are transformed, and image features are extracted.
        Model predictions are compared to ground truth labels to compute validation loss and accuracy.
        Validation loss and accuracy for the epoch are printed.
        Overall, this code trains and evaluates a neural network model using the CLIP model's image features on a dataset for a specified number of epochs, tracking training and 
        validation loss, as well as validation accuracy.


      


