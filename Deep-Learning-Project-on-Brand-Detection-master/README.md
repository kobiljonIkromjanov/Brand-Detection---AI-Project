# Deep-Learning-Project on Brand Detection

Deep Learning Project - Image and Video Training.
Here, you can see the video presentation on this Project also: https://www.youtube.com/watch?v=Ms3hJnLDrF4&feature=youtu.be


We gathered overall 289 train images and 60 test images of different brand. In the following you can see
Name of the brand	Test images	Train Images, respectively.

     Adidas   15	57
     Gucci    15	53
     Nike     11	59
     Puma     10	60
     supreme  9	60

We gathered different amount of pictures to see difference between them.

## Step 1:

Install TensorFlow-GPU 1.5, CUDA v9.0 and cuDNN v7.0, and Anaconda.

PC that we used was strong enough and could support above mentioned programs (8gb RAM, Core(TM) i5-7500 CPU, NVIDIA GeForce GTX-1050 ).

## Step 2:

We created Virual environment and downloaded important files and github project that we used.

https://github.com/EdjeElectronics/TensorFlow-Object-Detection-API-Tutorial-Train-Multiple-Objects-Windows-10

## Then we set up our virtual environment by command lines:

     •	conda create -n tensorflow1 pip python=3.5
     •	activate tensorflow1
     •	pip install --ignore-installed --upgrade tensorflow-gpu
     •	(tensorflow1) C:\> conda install -c anaconda protobuf
     •	(tensorflow1) C:\> pip install pillow
     •	(tensorflow1) C:\> pip install lxml
     •	(tensorflow1) C:\> pip install Cython
     •	(tensorflow1) C:\> pip install jupyter
     •	(tensorflow1) C:\> pip install matplotlib
     •	(tensorflow1) C:\> pip install pandas
     •	(tensorflow1) C:\> pip install opencv-python
     
## Then:

We configured our PYTHONPATH environment variable.  We kept all codes and images in tensorflow1 folder which was located in C: 
setPYTHONPATH=C:\tensorflow1\models;C:\tensorflow1\models\research;C:\tensorflow1\models\research\slim

## Step 3:

We used program called labelimg to create our xml file for each images which were located in train and test folders.

## Step 4:

By the help of xml_to_csv.py (which is located in C:\tensorflow1\models\research\object_detection) script , we created  a train_labels.csv and test_labels.csv file in the \object_detection\images folder

## Then:

We go to generate_tfrecord.py and change our path and class names to one`s which we are using. In my case it is adidas, GUCCI, NIKE, PUMA, supreme. We should be careful in this section because label names should be same as we named in labelImg app, otherwise errors would occur.

![image](https://user-images.githubusercontent.com/52565814/60793021-c77a5300-a1a1-11e9-8345-b260cee15ab0.png)

## Step 5:

We run following command line to start our data training. 
python train.py --logtostderr --train_dir=training/ --pipeline_config_path=training/faster_rcnn_inception_v2_pets.config

## Step 6:

We use our newly trained object detection classidier.

![image](https://user-images.githubusercontent.com/52565814/60793150-0a3c2b00-a1a2-11e9-8b10-847e0b99a467.png)
 
When we run our script we get information about detecting process in Anaconda command prompt.
If you want to run our script please follow instructions and then, do not forget to change PYTHONPATH to \tensorflow1\models\research\slim.
