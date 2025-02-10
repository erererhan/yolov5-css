
This project contains the source code of our paper ["Real-Time Pavement Crack Detection for Cutting Machines: Enhancing YOLOv5 with Lightweight Modules and Attention Mechanisms"](https://).
This project is based on YOLOv5 (https://github.com/ultralytics/yolov5) to achieve real-time pavement crack detection, aiming to provide more accurate crack recognition function for cutting machines. By introducing lightweight modules and attention mechanisms, the performance and real-time performance of the model in the task of pavement crack detection are improved.
We also propose a new crack datasets, namely [Slit Crack-Data dataset], to facilitate related research in the community.

# Documnetation

## Install
Python version: Python 3.8 or higher.
Libraries:
torch: Used for training and inference of deep learning models. Install it via pip install torch torchvision.
thop (optional): Used for computing FLOPs. Install it via pip install thop.

##dataset
Download datasets from (https://pan.baidu.com/s/1ej42BO6hZ1UDC5KFzrUCjA (d7wg))

## Training 

If you want to conduct your own training, please follow the steps below:

Data Preparation

Data Collection: Collect image data containing road surface cracks, ensuring the diversity of the images, including different lighting conditions, crack types, and backgrounds.
Data Annotation: Use an annotation tool (such as LabelImg) to annotate the collected images, marking the positions and categories of the cracks. The annotation format must meet the requirements of YOLOv5.
Dataset Splitting: Divide the annotated dataset into a training set, a validation set, and a test set. The common ratios are 7:2:1 or 8:1:1. Organize the divided dataset according to the following directory structure:

datasets/
    ├── your_dataset_name/
        ├── images/
            ├── train/
            ├── val/
            ├── test/
        ├── labels/
            ├── train/
            ├── val/
            ├── test/
Configuration File Modification
Data Configuration File: Create a new .yaml file (such as your_dataset.yaml) in the data directory with the following content:

train: datasets/your_dataset_name/images/train/
val: datasets/your_dataset_name/images/val/
test: datasets/your_dataset_name/images/test/

nc: 1  # Number of classes, assuming there is only one class of cracks here
names: ['crack']  # Class names
Model Configuration File: Select a suitable model configuration file.

Start Training

Run train.py
--img: The size of the input image.
--batch: Batch size, adjust it according to the VRAM of your GPU.
--epochs: The number of training epochs.
--data: The path of the data configuration file.
--cfg: The path of the model configuration file.
--weights: The path of the pre-trained weight file.
```
python train.py
```

# Citation

If you use our code or dataset in your research, please cite our article:["Real-Time Pavement Crack Detection for Cutting Machines: Enhancing YOLOv5 with Lightweight Modules and Attention Mechanisms"](https://).
