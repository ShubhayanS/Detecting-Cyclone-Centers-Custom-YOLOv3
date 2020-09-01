# Detecting-Cyclone-Centers-Custom-YOLOv3

This is a part of research work under National Aerospace Labs, Bangalore and CSIR under the chief scientist of Electromagnetics and Aerospace.
Fork and Star this repository and feel free to contribute to it.

## How to run? :runner:

    • Clone the repository and go to the folder with terminal. 
    • Install OpenCV by typing " pip install -r requirements.txt " in Terminal. 
    • Download last weight from [Google Drive Link](https://drive.google.com/drive/folders/1YaiyzmHb3_gJu2T_W2XRA2gmZhtR3Mxz?usp=sharing) and save it in yolo_custom_detection (P.S - Github has size limit of 100MB to upload files)
    • Run the ML model to detect hurricane center by typing python_object_detection.py
    • You can retrain for different dataset just you have to prepare datapoints for Yolov3 by installing LabelImg and running the Train_YoloV3.ipynb and also storing the dataset in your drive.

## Background

Artificial Intelligence refers to the intelligence of machines. This is in contrast to the natural intelligence of humans and animals. With Artificial Intelligence, machines perform functions such as learning, planning, reasoning and problem-solving. Most noteworthy, Artificial Intelligence is the simulation of human intelligence by machines. It is probably the fastest-growing development in the World of technology and innovation. Furthermore, many experts believe AI could solve major challenges and crisis situations.

Atmospheric science is the study of the Earth's atmosphere and its various inner-working physical processes. Meteorology includes atmospheric chemistry and atmospheric physics with a major focus on weather forecasting. Nowadays, the development of Information Technologies has led to a new era in computation, affecting almost all fields in Science and Engineering. Specifically, Machine Learning techniques have proven to be excellent tools to cope with difficult problems that arise in a huge variety of applications in Atmospheric Science and Climate Physics. These are usually data-driven problems concerning optimization, classification, or prediction, among others. In many cases, these problems are in close connection with alternative applications such as renewable energy resource evaluation, etc.

Similar to these situations, during severe cyclones and weather conditions, it might be difficult to identify regions where tropical cyclones and hurricanes exist. In such scenarios, the goal of building this AI based model is so it can be used to identify and detect cyclones from the satellite images in real time and help determine parameters such as location of cyclone in the images along with the center of cyclone where low pressure is indicated. This can help the weather scientists greatly and help notice points of depression.
                       
## Objectives:
 Storms and anticyclones are detected as extrema in the mean sea level pressure (slp) field. These extrema are detected following a modified form of the YOLO algorithm which stands for You Only Look Once  and implemented in the current AI based software.

    • Analyzing Images of Satellite 
    • Preparing Dataset of Satellite Images of Hurricane 
    • Training the ML model over labeled data sets of Hurricanes
    • Running a ML model to detect hurricanes in the Images
    • Finding the center of Cyclone from the detected Images                                       

## Methodology:

Initial Step is to collect satellite image dataset so as to train our AI based model. The dataset the model was trained upon  had been collected from MOSDAC, ISRO. It contains 14 satellite based images of hurricanes and cyclones of the globe.
Various other existing datasets are available in which the model can be fine tuned by training it with more open sources datasets available in Kaggle. Next Task lies in labelling the images where the cyclones are located in the images and storing the information in Blob - Text format. This is done using LabelImg Software which is open-sourced.

The first step is to run the training script which will load in the fields, detect extrema (minima for cyclones, maxima for anticyclones). Extrema must lie within a set of pixels no fewer than bounding boxes. The cyclone/anticyclone position is then recorded as the centre of mass of this neighbourhood of points. The detected positions are trained by the model with the information generated by LabelImg. The training generally took around 6hours on a Nvidia Tesla P Series GPU and an output file of stored weights if generated by the script.
The next step is to run the yolov3.py script which will load in the detected positions and stitch together appropriate bounding boxes from the weights generated over these satellites. Specifically, each layer contains one convolutional layer and one pooling layer. First convolutional layer has 32 features with 5 x 5 kernels and the second convolutional layer has 64 features with 7 x 7 kernels. We use max-pooling with a size of 2 x 2. We apply dropout~ to exclude 20% of neurons in order to reduce overfitting. The YOLO architecture works in the methodology of preprocessing, training, storing the learned parameters in weights and testing .The script runs over trained model with the images and helps in determining the cyclone in the images along with the images.

         
## Main Findings: 
Analysing Satellite Images after Training the model using getting bounding boxes of hurricane and from those boxes finding the centre of the boxes to get Center of Images. First, convolutional neural networks are trained to detect extreme climate events, and learn a distinctive feature of the event from massive-scaled cropped climate reanalysis data. Our architecture is 2-layered CNNs of YOLO.

Specifically, each layer contains one convolutional layer and one pooling layer. First convolutional layer has 32 features with 5 x 5 kernels and the second convolutional layer has 64 features with 7 x 7 kernels. We use max-pooling with a size of 2 x 2. We apply dropout~ to exclude 20% of neurons in order to reduce overfitting. Lastly, one dense layer with ReLU activation and one fully connected layer is followed. We use softmax The output has one class representing probability of existing events in input and a softmax activation has been used. The YOLO v3 model showed an accuracy of 85% when it had been trained on an image dataset of 14 satellite images.
                                                                                   
       
## Conclusion: 
TROPICAL cyclones (TCs) are intense warm-corded cyclonic vortices, developed from low-pressure systems over the tropical oceans and driven by complex air-sea interaction. Recent trend analysis based on both archive data and future projections consistently suggest an increase of the mean intensity of global TCs over coming decades, although there could be a decrease in TC frequency. Deep learning and advances in the field of computer vision provide a novel and powerful set of tools to tackle this demanding task
Output of the AI model is the exact location of the longitude and latitude of the hurricane center in a 2d-input image. Satellite images can be imputed to get cyclone centers points that are the regions of lowest pressure. We present preliminary results on tracking and semantic segmentation with climate data. CNNs and LSTMs in the form of YOLOv3 and Darknet are able to track storms as long as they are trained one at a time. In the future, we aim to apply CNNs and LSTMs to simultaneous storm tracking. Providing more physical variables and dataset for models to train on may improve model performance and allow for detection of other extreme weather events.

## Future perspectives:
The study lacks training in a wide variety of datasets. The work can be added for visualization and we can also predict the cyclone direction and also increasing accuracy by training over wide variety of cyclone data.

## Contributor:

* [Shubhayan S](https://www.google.com)
