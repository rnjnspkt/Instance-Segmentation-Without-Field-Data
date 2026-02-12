🍎 **Instance Segmentation Without Field Data Automatic Annotation for Apple Detection Using LLM-Generated Synthetic Images**

**Overview**
![Fig1](https://github.com/user-attachments/assets/b7f2f905-df50-452a-a6ef-1a74b9b62a9a)

This project presents a novel, fully automated training pipeline for apple instance segmentation in commercial orchards developed without field data collection or manual image annotation during training.

Traditional agricultural computer vision workflows require extensive sensor-based data acquisition and labor-intensive mask labeling. This work eliminates both by leveraging:

**LLM-generated synthetic orchard images**

**Automatic mask annotation via YOLO + SAM**

**Downstream training of YOLO11-seg models**

**Real-field validation using machine-vision sensor images**

The core idea is to use foundation models as annotation engines rather than deployment systems. Synthetic orchard scenes are generated using structured prompts, and apples are automatically localized using a pretrained YOLO detector. These bounding boxes are passed to the Segment Anything Model (SAM) to generate high-quality instance masks. The automatically labeled synthetic dataset is then used to train lightweight YOLO11-seg models suitable for real-time inference.

Importantly, SAM is used only during the annotation stage, not at inference. The trained YOLO11-seg models are independently validated on real orchard images captured using a Microsoft Azure Kinect machine-vision sensor mounted on a robotic platform.

**Key Contributions**
Synthetic Images Publicly available ( Link: https://drive.google.com/drive/folders/1YQmti-aiiaITotCdvD9E_iZsFmV-U6zM ) 

Field-data-free training workflow ( Training code available at : https://github.com/rnjnspkt/Instance-Segmentation-Without-Field-Data/blob/main/Training%20Script.ipynb ) 

Zero manual annotation

Deployment-ready segmentation models

Real-world orchard validation

**Why This Matters**

Agricultural AI systems often face high data collection costs and scalability barriers. This project demonstrates that foundation models can be leveraged to generate training data automatically, enabling accurate and practical instance segmentation in real orchard environments without conventional field imaging pipelines.

This notebook implements a complete automated annotation and training pipeline for apple instance segmentation using YOLO and the Segment Anything Model (SAM). It first installs and configures required libraries, including Ultralytics YOLO and Meta’s Segment Anything, then loads pretrained models to perform zero-shot apple detection and mask generation on LLM-generated synthetic orchard images. The workflow uses YOLO to produce bounding boxes, which are passed to SAM to generate high-quality instance masks that are saved in YOLO segmentation format for downstream training. The dataset is programmatically organized and split into training and validation sets, after which multiple YOLO11-seg configurations (n, s, m, l, x) are trained and evaluated. Finally, the trained models are validated on both synthetic and real machine-vision orchard images, including mask visualization, performance comparison, and computational profiling, enabling assessment of field-level deployment readiness.
Full code available at:  https://github.com/rnjnspkt/Instance-Segmentation-Without-Field-Data/blob/main/Training%20Script.ipynb 
