# Image-Recognition
Supervised Machine Learning Model to recognise images.
In this example we will use it to detect flowers.
It can be reused to identify other object images by retraining the model.

## How to use this model to detect image of sunflower/daisy/dandelion/rose/tulips?
Activate the virtual environment:
```bash
source venv/bin/activate
```
Predicting the flower category.
*Place the image to be detected in the root project directory(this folder)*:
```bash
python label_image.py testimage.jpg 
```
_Note: In this case **testimage.jpg** is the image to be predicted and it is placed in the root folder directory_

##Reusing the model for some other images!
_You don't need to clone the whole project! Just download the **retrain.py** and **label_image.py** in your project directory_

Go to the project directory.
Create a new virtual environment for your application:
```bash
virtualenv venv
```
Activate the virtual environment:
```bash
source venv/bin/activate
```
Install tensorflow library:
```bash
pip install tensorflow
```
Download the data set for images you want to recognise/classify and place it in the project directory:
*In above case(flower recognition) flower_photos is the data set directory*
_Within the dataset directory keep images of each kind of object in different directries specifying their name _

Train the classifier using inception v3 neural network:
```bash
python retrain.py \
--bottleneck_dir=bottlenecks \
--how_many_training_steps 4000 \
--model_dir=inception \
--output_graph=retrained_graph.pb \
--output_labels=retrained_labels.txt \
--image_dir [image data-set directry name/path]
```
Predicting the image category.
*Place the image to be detected in the root project directory(this folder)*:
```bash
python label_image.py testimage.jpg 
```
_Note: In this case **testimage.jpg** is the image to be predicted and it is placed in the root folder directory_
