Hello, this is a deep learning project that I did during my Erasmus Program with my professor at Politechnika Lubelska. The goal of the project is to classify dog vs cat images with 3 different optimizer and different epoch numbers, evaluate them and choose the effective model.
    
The tools will be used during this project are Anaconda to create environment, jupyter and spyder to code, some libraries such as TensorFlow, Keras, Matplotlib, Seaborn, Pandas, Numpy, Sklearn.


# Characteristics of the data

I have 800 train images (400 for cat-400 for dog), and 600 images for test and validation both (300 for cat-300 for dog). 

**Example Images**
<br>
![](img/cat.9390.jpg)
<br>
![](img/dog.9638.jpg)


# Python Code

First, activating the environment.

```python
-conda activate tf-gpu
```
Then, I set the parameters. I will build a binary classification model and for the loss function, I will use binary_crossentropy. Batch sizes 8 for train and validation. The model which I use is VGG16. So, input shape is (224, 224, 3). I will build a model with 100 epochs first (50 for training and 50 for tuning) and then I will try to find the most effective epoch number for each optimizer.
```python
CLASS_MODE = 'binary'
LOSS_TYPE ='binary_crossentropy'    
CLASSES_NUMBER = 0
IMAGE_SIZE = (224, 224)
INPUT_SHAPE = (224, 224, 3)
TRAIN_BATCH_SIZE = 8
VAL_BATCH_SIZE = 8

TRAINING_EPOCHS = 50
TUNNING_EPOCHS = 50
```

The first model that I will build is using RMSprop optimization algorithm. The metrics will be accuracy for classification model.
```python
model.compile(loss=LOSS_TYPE,
                  optimizer=optimizers.RMSprop(lr=LR),
                  metrics=['acc'])  
```
So, I run the function.

```python
-python modelBuilding.py
```

Sizes for training and validation can be seen from the figures.
<br>
![](img/RMS-50/figure1.PNG)
<br>
![](img/RMS-50/figure2.PNG)

Now, the model has been downloaded from its github page and the model training has been started. These are the last 5 epochs for model training.
<br>
![](img/RMS-50/last%205%20epochs%20of%20training.PNG)
