# HAIR TEXTURE IDENTIFIER 

 My project is designed to identify what hair texture someone has based on a photo of their upper body. This should help people learn how to better maintain their hair's health. 

![image](https://github.com/user-attachments/assets/4374fea5-02b6-4057-b3b7-8ebaa3563d9c)

## The Algorithm

This program uses Resnet-18, which is a network that is pre-trained with the ImageNet 2012 classification dataset. This means that it can already identify various different objects. 
To adapt my project so that it specifically identifies hair types, I retrained the network by applying other datasets that I found on kaggle.com 
with different photos of various hairstyles and textures.
I used data from these two datasets! 
https://www.kaggle.com/datasets/siddhantkulkarni73/hair-segmentation-dataset?select=data 
https://www.kaggle.com/code/kerneler/starter-the-three-hair-types-21796dbe-e

## Running This Project

1. Download the code and any necessary datasets 
2. Train the model by running "python3 train.py --model-dir=models/hair_type data/hair_type" in the docker container
3. Run the onnx export script "python3 onnx_export.py --model-dir=models/hair_type"
4. Exit the docker and assign these variables "NET=models/hair_type" and "DATASET=data/hair_type"
5. Run this command plugging in any needed info to use the model on an image in the test folder
   "imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/*folder name*/*image name* *new name*.jpg"
   
## Required Libraries
1. NumPy
2. PyTorch

[View a video explanation here]([video link](https://drive.google.com/file/d/1E_diFjfmJGqvKa1bvRUa1i2ZHZqfNj_J/view?usp=drive_link))
