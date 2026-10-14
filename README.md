# Improving Autonomous Vehicle Object Detection in Extreme Weather

This repository supports the research paper **"Enhancement of Autonomous Vehicles During Extreme Weather"** by Pandian Anand (2025).

📄 Paper: [[Link to PDF here](https://independent-project-mentorship.netlify.app/projects/2fcfe3ae3e0ac0b0bd88127727f8578cb517626d.html)]

This project fine-tunes the **YOLOv8n** object-detection model to help self-driving cars accurately detect vehicles and pedestrians in rain, fog, snow, sandstorms, and other adverse weather conditions.

Click the badge below to **view and run this notebook in Google Colab**:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PandianAnand/Autonomous-Vehicle-Improvement/blob/main/Inspirit_AI_vehicle.ipynb)
---

## Dataset
- **Source:** DAWN (Detection in Adverse Weather Nature) dataset on Kaggle  
- **Size:** 1,025 real-world road images  
- **Weather Types:** sandstorm, fog, snow, rain, mist, haze  
- **Format:** Images (`.jpg`) with YOLO-style labels (`.txt`)

---

## Methodology

### 1. Data Preprocessing
- Used the DAWN (Detection in Adverse Weather Nature) dataset containing 1,025 real-world road images.
- Filtered YOLO annotations for six object classes: car, truck, person, bicycle, motorcycle, and bus.
- Organized images and corresponding labels into training (80%) and validation (20%) datasets using stratified splitting.

### 2. Model Training
- Initialized a pretrained YOLOv8n object-detection model using Ultralytics.
- Fine-tuned the model for 20 epochs using an NVIDIA Tesla T4 GPU.
- Trained the model to recognize vehicles and pedestrians under fog, rain, snow, sandstorms, mist, and haze.

### 3. Model Evaluation
- Evaluated the fine-tuned model on 205 validation images containing 1,575 annotated object instances.
- Measured precision, recall, mAP@50, and mAP@50–95 using Ultralytics validation metrics.
- Conducted a separate manual comparison of the original and fine-tuned YOLOv8n models by counting detected objects in selected adverse-weather images.
- Examined prediction confidence levels and model limitations under adverse and nominal weather conditions.

## Results

### Standard Object Detection Metrics

The fine-tuned YOLOv8n model achieved the following results on the 205-image validation set containing 1,575 annotated object instances:

| Metric | Result |
|---|---:|
| Precision | 71.4% |
| Recall | 51.9% |
| mAP@50 | 60.4% |
| mAP@50–95 | 33.7% |

The model achieved its highest class-specific mAP@50 on cars (85.9%).

### Manual Object Detection Comparison

A separate manual comparison was conducted using selected adverse-weather images to examine the detection capabilities of the original and fine-tuned YOv8n models.

| Model | Manual Detection Rate | Approx. Avg. Confidence |
|---|---:|---:|
| Original YOLOv8n | 30.77% | 0.5 |
| Fine-tuned YOLOv8n | 94.87% | 0.9 |

The fine-tuned model showed a **64.10 percentage-point increase in the reported manual detection rate**.

**Important:** These manual detection rates represent the proportion of visible objects counted as detected in selected images. They are not equivalent to standard detection accuracy or mAP, and the comparison has not been independently reproduced through a complete validation benchmark.

### Key Findings

- Fine-tuning improved object detection in the selected adverse-weather examples.
- The model achieved 60.4% mAP@50 on the validation dataset.
- Some detection limitations remained, particularly for small or distant objects and classes with fewer training examples.
- The fine-tuned six-class model did not support traffic-light detection, highlighting a limitation for broader autonomous-driving applications.

## Sample Output
<img width="274" height="185" alt="Nontuned" src="https://github.com/user-attachments/assets/4661f4a7-26d5-403d-b952-7a43abe74392" /> <img width="275" height="185" alt="Tuned" src="https://github.com/user-attachments/assets/e904fc74-9c6b-40d6-a66b-2fe75f31184d" />

  
*Left: non-tuned YOLOv8n (single car @0.55 confidence)  
Right: fine-tuned YOLOv8n (multiple vehicles, up to 0.91 confidence).*

---

## Next Steps

- Evaluate the original and fine-tuned YOLOv8n models on the same held-out test dataset to quantify changes in mAP, precision, and recall.
- Expand the model to detect traffic lights and estimate object distances.
- Investigate adaptive switching between nominal-weather and adverse-weather perception models.
- Experiment with additional training epochs, larger datasets, and data augmentation to improve detection robustness.
- Evaluate model generalization across individual weather conditions, including fog, rain, snow, and sandstorms.

---

## Tech Stack
Python · Ultralytics YOLOv8 · OpenCV · Pandas · Jupyter Notebooks

---

## Citation
If you reference this work, please cite:  
`Anand, P. (2025). Improving Autonomous Vehicle Object Detection in Extreme Weather with YOLOv8n.`

---

## Citation

If you reference this work, please cite:

Anand, P. (2025). *Enhancement of Autonomous Vehicles During Extreme Weather*. Inspirit AI Research Program.  
Supporting implementation: *Improving Autonomous Vehicle Object Detection in Extreme Weather*, GitHub Repository.


