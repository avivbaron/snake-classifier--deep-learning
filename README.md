# Venom Snake Classifier

The essence of the project is to serve as a tool for travelers (currently only trained on snakes from India) who travel in the wild of India, in case they have encountered a snake or even been bitten by a snake, photograph the snake and know what kind it is and if it is venomous or not.

How ot works:

The model which is trained for this purpose is based on the 16VGG model without its top and uses the final weights calculated for imagenet.
I chose to use this model because it achieved really good results in the competition and since some of the categories of the competition also include snakes and reptiles which can be deduced from it that some of the textures of the neurons have been trained for similar things and all that remains is to train the final part to identify 13 types of snakes in India.
Currently, I have not yet found the ideal parameters for achieving results with a level of accuracy higher than 70% but I truly believe that this is possible.
The percentage is relatively low because the model has difficulty identifying one specific strain called the banded racer. Compared to the other varieties, the model identifies with a probability of 80% +.
To the end of the model, I added 3 layers of Dense with Sigmoid activation which proved that it achieves better results than ReLU in this case after many attempts. Between each layer, I added Dropout layers to make it as difficult as possible for the system to practice and thus actually produce quality training for the model.
To find the best training method for the model, I first tried to thicken my dataset by augmenting in 2 different configurations (as you can see in the code), and in both, after many attempts that included lots of parameter changes and adding/removing layers from the model, I could not achieve Accuracy greater than 0.65.
But when I tried to process the information (images) manually and use functions that use only the existing images and do not produce new images from the existing content, I reached the highest result in the training phase which was 0.7.
Of course, this is not an accuracy that one can be happy with, but unfortunately, it is the best I have been able to produce.

Sources:


https://www.learnopencv.com/keras-tutorial-fine-tuning-using-pre-trained-models/ - fine tuning guide
https://github.com/arjun921/Indian-Snakes-Dataset - dataset
https://pythonprogramming.net/loading-custom-data-deep-learning-python-tensorflow-keras/ - processing the data
