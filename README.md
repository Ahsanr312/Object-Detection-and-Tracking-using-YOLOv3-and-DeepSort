# Object-Detection-and-Tracking-using-YOLOv3-and-DeepSORT
This repository implements object detection and tracking using state-of-the-art algorithms, that are, YOLOv3 and DeepSORT in street view imagery. All the computation required will be performed using Google Colab. Mainly, the process will involve two main steps:

### Original Repository: 

### Yolov3 Paper: https://arxiv.org/abs/1804.02767

### DeepSORT Paper: https://arxiv.org/abs/1703.07402

### About Darknet framework: http://pjreddie.com/darknet/

#### First: Train an Object Detector (YOLOv3) to detect target object
- Follow my YOLOv3 object detection repository to train custom object detector https://github.com/Ahsanr312/Object-Detection-in-Satellite-Imagery-Using-YOLOv3-
- In this repository our target of interest would be detection and tracking of cars in tough weather conditions using a sub-dataset from AAU RainSnow Traffic Surveillance Dataset available at https://www.kaggle.com/aalborguniversity/aau-rainsnow.
- Training dataset: Contains 1200 images (80% dataset)
- Validation dataset: Contains 300 images (20% dataset)
- Test Videos: The system is tested on 10 videos with results available at  

#### Second: Apply Tracker (DeepSORT) to trained YOLOv3 weights to perform tracking
- Set up google drive:
  - Log in to your google account and go to google drive.
  - Create a folder, by naming it "Object Tracking" and upload this repository to newly created Object Tracking folder.
- Set up google colab:
  - In the Object Tracking folder in google drive, right click on "Object_Tracking.ipynb" file and select open with -> Google Colaboratory. The file will open in the colab.
  - Next, we need to choose GPU for our training. To do so, click on "Edit" and select "Notebook settings" and then choose "GPU" under Hardware accelerator option. 
  - Press "save" and you are good to go.
  - This notebook is created for testing object tracking in colab.
  - Step 1: Place trained YOLOv3 weights in the weights folder at your google drive 
  - Step 2: Run first cell in the Object_Tracking.ipynb notebook to check which GPU is assigned to you. 
  - Step 3: Run second cell to install all the requirements needed for this repository.
  - Step 4: Run third cell to setup NVIDIA driver for GPU
  - Step 5: Run fourth cell that basically converts YOLOv3 weights (darknet) to tensorflow format.
  - Step 6: Run fifth cell that detects and tracks target objects using converted YOLOv3 weights and DeepSORT.

#### Important measures before Going onto Second Step
- Make sure you place exact same .names file in your data/labels/ folder for which you trained YOLOv3.
- Place test video files in data/video/
- Make sure you replace exact same classes in coco_classes.txt at model_data/ folder for which YOLOv3 is trained. 
- Make sure you replace and use same anchor values in yolo_anchors.txt on which YOLOv3 is trained. 
- Make sure you replace/edit yolo_anchors array in models.py file at yolov3_tf2/ folder with same anchor values used for training YOLOv3. Moreover, the array is divided by the network resolution value that maybe 416, 608, or any value used while training YOLOv3.

#### FUTURE WORK
- The Flow can be te-implemented by using other detection algorithms such as YOLOv4, YOLOv5, EfficientDet
- Use other state-of-the-art object tracking algorithms. 
