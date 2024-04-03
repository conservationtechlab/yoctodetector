# yoctodetector

Tools for training custom animal object detectors.

### Instruction on Training Yolo Using Your Own Dataset of Images: 

##### 1. Label data uisng Labelme
1a. Download labelme: "pip install labelme" (https://github.com/labelmeai/labelme)

1b. Label data and save to directory --> {HomeDir/LabelDir}

##### 2. Convert the Labelme output to yolo training input
2a. Download labelme2YOLO: "git clone https://github.com/rooneysh/Labelme2YOLO.git"

2b. "cd Labelme2YOLO"

2c. "python labelme2yolo.py --json_dir {HomeDir/LabelDir} --val_size 0.2"

##### 3. Get the yolo models + packages (inside ultralytics)
3a. Downloaded ultralytics: "pip install ultralytics==8.0.196"

##### 4. Train your model
4a. "yolo task=detect mode=train model=yolov8s.pt data="{HomeDir/LabelDir}/YOLODataset/dataset.yaml" epochs=10 plots=True

*you can view stats about the model at {HomeDir}/runs/detect/train#

*model will be saved at "{HomeDir}/runs/detect/train#/weights/best.pt"


### Instructions to Use the Model You Trained to Predict New Images from Directory
 Please follow the steps in the corresponding jupyter notebook: testOWL_wYOLO.ipynb
 
 *predictions will be saved at {HomeDir}/runs/detect/predict#
 

### Instructions to Use the Basic YOLOv8 Model to Predict New Images from Directory
 Please follow the steps in the corresponding jupyter notebook: owlClassification_YOLOv8
 
 *predictions will be saved at {HomeDir}/runs/detect/predict#
