# Unet-tensorflow-keras
A concise code for training and evaluating Unet using tensorflow+keras 

A simple practice of mixture usage of tensorflow and keras for the segmentation task. Using keras to build the model is super easy and fully compatible with Tensorflow. See https://blog.keras.io/keras-as-a-simplified-interface-to-tensorflow-tutorial.html for an introduction.

I use the Unet architecture and modify its unsampling part to automatically adjust the feature map width and height when merge (concat) with previous layers. In this way, we do not need to compute the specific input size to fit the model but take an arbitrary size. 

### Usage
- Write a data loader by yourself
- Set necessary hpyerparameters inside the train.py 

  ```python
  python train.py
  ``` 
- Visual train loss, dice score, and output mask per iteration in tensorboard

  ```
  tensorboard --logdir=train_log/
  ``` 
- When checkpoints are saved, you can use eval.py to test an input image with an arbitrary size.
