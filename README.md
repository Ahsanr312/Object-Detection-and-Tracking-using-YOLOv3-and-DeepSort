# Object-Detection-and-Tracking-using-YOLOv3-and-DeepSORT
This repository implements object detection and tracking using state-of-the-art algorithms, that are, YOLOv3 and DeepSORT in street view imagery. All the computation required will be performed using Google Colab. Mainly, the process will involve two main steps: 
#### First: Training an Object Detector (YOLOv3) to detect target object
- Follow my YOLOv3 object detection repository to train custom object detector https://github.com/Ahsanr312/Object-Detection-in-Satellite-Imagery-Using-YOLOv3-
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
- 
