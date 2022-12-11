# One-Neural-Network-for-Multiple-Purposes
This repository contains code for a neural network model that is trained once and is used for 4 different tasks successfully. 
Here we train a single model, which is used for captioning images, inferring images from a caption, finding similar words from a given word and finding similar images from given image.


Here we use pretrained InceptionV3 model to generate 2048-dimensional representation of a image, a fully connected neural networks is used to produce 300-dimensional embeddings from image embeddings (from inception V3), another fully connected neural network is used to produce 300 dimensional embeddings from word vectors, a recurrent neural network layer followed by a fully connected neural network to predict the next word. **(Look at the poster for model architecture - [Poster](https://github.com/Sahaj09/One-Neural-Network-for-Multiple-Tasks/blob/master/Project%20Poster.pdf))**. 

### Task 1 (generate captions from image) - 
We learn to generate the image captions using the above model and the image captioning dataset 

### Task 2 and 3 (find similar images given an image, find similar captions given a caption) -
Then we use embeddings from the two fully connected neural networks (that generate 300 dimensional embeddings from InceptionV3 output embeddings and word vectors) to find similar images for given image, and  similar captions for a given caption using cosine similarity.

### Task 4 (find images for a caption) -
For "inferring image given a caption" we fix the model weights and instead of image embeddings, we input a randomly generated embedding, now keeping the model weights fixed we only update the input embedding. After training for a few number of iterations we use cosing similarity to find the most similar image to the resulting embedding, hence, completing the task of inferring image from caption.

### Other details

The dataset used by us is Flickr8K Dataset.

The programs for the project is dependent on multiple pickled files that will be created as you keep on following the instructions below.

1. run the Inception_2048vector_generation.ipynb to generate 2048 vectors for further tasks.

2. run the read_for_data.py while placing it within the Flickr8k_text folder. (this file is used to load all the captions along with image names)

3. run the test_images_pickle file while placing it within the Flickr8k_text folder. 

4. run the preprocessing_ordering_data_for_model.ipynb file to order the data accordingly for the training phase.

5. run the Image_Caption_Generation_Training.ipynb file which will provide predicted captions for the image and train the model.

6. Make sure you save your model using checkpoints accordingly. As you will require a saved model for the other tasks in the project.

7. Now run the Tasks_using_built_network.ipynb file for results for similar image finding task, similar words finding task and
   inferring images from sentence of words task.   

8. t_SNE_viz .ipynb file was used for creating tsne plots for image and word embeddings.


Dataset has been provided in this zipped folder.

This folder also includes the Project Report and the Project Poster. 

For more information reach out at sahmaini@iu.edu. Have a good day! and stay blessed!
