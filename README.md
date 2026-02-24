# Improving Autonomous Vehicle Object Detection in Extreme Weather

This repository supports the research paper **"Enhancement of Autonomous Vehicles During Extreme Weather"** by Pandian Anand (2025).

📄 Paper: [[Link to PDF here](https://independent-project-mentorship.netlify.app/projects/2fcfe3ae3e0ac0b0bd88127727f8578cb517626d.html)]

This project fine-tunes the **YOLOv8n** object-detection model to help self-driving cars accurately detect vehicles and pedestrians in rain, fog, snow, sandstorms, and other adverse weather conditions.

Click the badge below to **view and run this notebook in Google Colab**:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PandianAnand/Autonomous-Vehicle-Improvement/blob/main/Inspirit_AI_vehicle_Colab.ipynb)
---

## Dataset
- **Source:** DAWN (Detection in Adverse Weather Nature) dataset on Kaggle  
- **Size:** 1,025 real-world road images  
- **Weather Types:** sandstorm, fog, snow, rain, mist, haze  
- **Format:** Images (`.jpg`) with YOLO-style labels (`.txt`)

---

## Methodology
1. **Preprocessing**  
   - Filtered labels for key classes: car, truck, person, bicycle, motorcycle, bus  
   - Split: 80 % training / 20 % testing

2. **Model Training**  
   - Base model: **YOLOv8n (Ultralytics)**  
   - Fine-tuned for 20 epochs

3. **Evaluation**  
   - Metrics tracked: **accuracy** and **average confidence level**

---

## Results
| Model      | Accuracy | Avg. Confidence |
|------------|---------:|----------------:|
| Non-tuned  | 30.77 %  | ~0.5 |
| Fine-tuned | 94.87 %  | ~0.9 |

➡️ **~70 % absolute improvement** in detection accuracy under extreme weather.

---

## Sample Output
<img width="274" height="185" alt="Nontuned" src="https://github.com/user-attachments/assets/4661f4a7-26d5-403d-b952-7a43abe74392" /> <img width="275" height="185" alt="Tuned" src="https://github.com/user-attachments/assets/e904fc74-9c6b-40d6-a66b-2fe75f31184d" />

  
*Left: non-tuned YOLOv8n (single car @0.55 confidence)  
Right: fine-tuned YOLOv8n (multiple vehicles, up to 0.91 confidence).*

---

## Next Steps
- Add traffic-light detection and distance estimation  
- Explore adaptive switching between nominal-weather and extreme-weather models  
- Test more epochs and larger datasets

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


