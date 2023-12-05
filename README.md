# IMAGE-CAPTION-GENERATOR FOR FLICKR 8K DATASET
Create an image caption generator using pretrained VGG16 model to get features from an image and LSTM layer to generate captions
1. Load the VGG16 model and the Flick dataset.
2. We will remove the last prediction layer and take the remaining layers as we need the image features.
3. Load the captions and create a mapping between captions and image. An image can have multiple captions. Here each image has 5 captions
   
# PREPROCESS CAPTION DATA AND CONVERT INTO SEQUENCE FORMAT
1. Convert all uppercase to loawer case
2. Remove all special characters and numbers and extra spaces.
3. Add startseq and end seq to each caption

# CREATE A DATAGENERATOR OBJECT TO GET DATA IN BATCH
1. Convert each caption into tokens.
2. From the sequences create input and out variables.
3. Input variables will have both the image features and the words in captions.
4. Output variable will the next word in sequence to be redicted
5. for e.g how to sequence generator works
  <start> girl going into wooden building <end>
           x           y
        <start>     girl
   <start> girl    going
   ........
7. Pad the captions to maximum length of the captions.

# MODEL CREATION
![image](https://github.com/aniket-patra-1998/IMAGE-CAPTION-GENERATOR/assets/69764370/55f8eab5-d2da-4f09-b412-7d695257c6ab)
![image](https://github.com/aniket-patra-1998/IMAGE-CAPTION-GENERATOR/assets/69764370/0a2e8d3b-a01f-4616-8c45-f0dfb5daa2fb)

# TRAIN AND TEST THE MODEL
1. Loss function : Categorical CrossEntropy for multiclass classification with softmax as the output layer actiavtion
2. Optimizer = Adam
3. Bleu-Score for checking model performance

# MODEL PERFORMANCE
![image](https://github.com/aniket-patra-1998/IMAGE-CAPTION-GENERATOR/assets/69764370/713c6826-5eb8-43a7-96ef-f628875bc29a)




