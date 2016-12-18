# Flower-Recognition-
Supervised Machine Learning Model to recognise flowers.
It can be reused to identify other object images by retraining.

### How to use ?
Activate the virtual environment
```bash
source venv/bin/activate
```
Download the trainig dataset (flower images in this case)
```bash
curl -O http://download.tensorflow.org/example_images/flower_photos.tgz
```
Extract the images folder	
```bash
tar xzf flower_photos.tgz
```
Training the dataset using inception v3 neural network
```bash
python retrain.py \
--bottleneck_dir=bottlenecks \
--how_many_training_steps 4000 \
--model_dir=inception \
--output_graph=retrained_graph.pb \
--output_labels=retrained_labels.txt \
--image_dir flower_photos
```
Predicting the flower
*Place the image to be detected in the root project directory(this folder)*
```bash
python label_image.py testimage.jpg 
```
**Note: In this case testimage.jpg is the image to be predicted and it is placed in the root folder directory**
