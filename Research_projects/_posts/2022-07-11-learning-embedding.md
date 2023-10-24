---
layout: post
title: Learning-Embedding-for-images-using-Deep-leaning
description: >
  Google Universal Image Embedding Kaggle competition
image: /assets/img/learn_emb.png
sitemap: false
---
---
## The problem 

In the competition, we were asked to develop models that can efficiently retrieve images from a large database. For each query image, the model is expected to retrieve the most similar images from an set hidden to us.

In their words
>"In this competition, the developed models are expected to retrieve relevant database images to a given query image (ie, the model should retrieve database images containing the same object as the query). The images in our dataset comprise a variety of object types, such as apparel, artwork, landmarks, furniture, packaged goods, among others."

## Process

* Here are the sources from which the dataset was made:

- https://www.kaggle.com/datasets/naturalseeker/triplet-data https://www.kaggle.com/datasets/abhijeetbhilare/world-cuisines 
- https://www.kaggle.com/datasets/naturalseeker/packed-goods 
- https://www.kaggle.com/datasets/naturalseeker/packed-goods 
- https://www.kaggle.com/datasets/naturalseeker/images-for-google-comp 
- https://www.kaggle.com/datasets/watts2/glove6b50dtxt 
- https://www.kaggle.com/datasets/naturalseeker/door-image 
- https://www.kaggle.com/datasets/jaidevchittoria/babies-products-and-toys 
- https://www.kaggle.com/competitions/google-universal-image-embedding

* Next, I have to select a training method. It's an obvious choice to fine-tune already available models and use triplet loss. I used Swin Transformer and DeiT.

check out the project github [here](https://github.com/shivacharan22/Learning-Embedding-for-images-using-Deep-leaning/tree/main)

Together 100k pair images from 25k initial images.

## Results : 
95 % accuracy on test data(10%) separated from above.

### Test sample:

<img width="517" alt="Screenshot 2023-01-12 at 3 20 01 AM" src="https://user-images.githubusercontent.com/54499416/211925349-3036f946-3ba5-49b3-9172-279046938351.png">

* Image original 
 <img width="274" alt="image" src="https://user-images.githubusercontent.com/54499416/211925837-592b071a-f56e-477e-b95a-e8f7a1bd5417.png">

* Image 1 comparision positive score of **3.39**
<img width="317" alt="image" src="https://user-images.githubusercontent.com/54499416/211926371-7a9e4def-9931-4dab-8454-3812d5b1b7ad.png">
* Image 2 comparision Negitive score of 11.35
<img width="222" alt="image" src="https://user-images.githubusercontent.com/54499416/211926822-76b11449-b691-4f99-9af1-9caf2562e5fa.png">

Model predicts Image 1 is more similar to original than Image 2.
