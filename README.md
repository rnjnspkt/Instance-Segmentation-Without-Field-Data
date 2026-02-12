**🍎 Instance Segmentation Without Field Data**
Automatic Annotation for Apple Detection Using LLM-Generated Synthetic Images
**Overview**

This project presents a novel, fully automated training pipeline for apple instance segmentation in commercial orchards—developed without field data collection or manual image annotation during training.

Traditional agricultural computer vision workflows require extensive sensor-based data acquisition and labor-intensive mask labeling. This work eliminates both by leveraging:

**LLM-generated synthetic orchard images**

**Automatic mask annotation via YOLO + SAM**

**Downstream training of YOLO11-seg models**

**Real-field validation using machine-vision sensor images**

The core idea is to use foundation models as annotation engines rather than deployment systems. Synthetic orchard scenes are generated using structured prompts, and apples are automatically localized using a pretrained YOLO detector. These bounding boxes are passed to the Segment Anything Model (SAM) to generate high-quality instance masks. The automatically labeled synthetic dataset is then used to train lightweight YOLO11-seg models suitable for real-time inference.

Importantly, SAM is used only during the annotation stage, not at inference. The trained YOLO11-seg models are independently validated on real orchard images captured using a Microsoft Azure Kinect machine-vision sensor mounted on a robotic platform.

**Key Contributions**
Synthetic Images Publicly available ( Link: https://drive.google.com/drive/folders/1YQmti-aiiaITotCdvD9E_iZsFmV-U6zM ) 

Field-data-free training workflow

Zero manual annotation

Deployment-ready segmentation models

Real-world orchard validation

**Why This Matters**

Agricultural AI systems often face high data collection costs and scalability barriers. This project demonstrates that foundation models can be leveraged to generate training data automatically, enabling accurate and practical instance segmentation in real orchard environments without conventional field imaging pipelines.
