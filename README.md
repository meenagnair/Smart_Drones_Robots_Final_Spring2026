# Smart Drones Final Project For Spring 2026
computer vision system intended for use with aerial drone footage in order detect conditions of crowd crush events in real time

---
## Overview
Crowd crush is the term used to describe when a crowd becomes so dense that fatalities can occur from compressive asphyxia caused by high crowd density. This project is intended for use of a drone to autonomously patrol a designated area and monitor crowds for associated risk conditions. Due to the diffuiculty of simulating the associated conditions with this project, the files here remain an AI pipeline, and will be updated in the future.

---
## Risk Thresholds

| Level    | Density     | Meaning                          |
|----------|-------------|----------------------------------|
| SAFE     | < 2 /m²     | Free movement                    |
| CAUTION  | 2–4 /m²     | Monitored                        |
| WARNING  | 4–5 /m²     | Intervention advised             |
| DANGER   | 5–7 /m²     | High crush risk                  |
| CRITICAL | > 7 /m²     | Immediate intervention required  |
---
## Dataset & Model

- **Dataset:** VisDrone2019-DET — 261,908 annotated aerial frames 
  across 288 video clips, captured across 14 cities
- **Model:** YOLOv8m fine-tuned on VisDrone pedestrian + people classes
- **Accuracy:** mAP@0.5 = 45.35% on VisDrone val set
- **Baseline comparison:** Standard COCO-trained YOLOv8 scores ~0% 
  on aerial crowd imagery
---
## How to Run

1. Open `crowd_crush_video_final.ipynb` in Google Colab
2. Set runtime to **L4 GPU** (Runtime → Change runtime type)
3. Run all cells in order
4. Training takes around 1 hour on first run but weights will be saved to Drive
   so you only train once
6. Set your video file path in Step 10 and run the pipeline
---
## Pipeline Stages

| Stage | Description | Status |
|-------|-------------|--------|
| 1 | Data collection & preparation | ✅ Complete |
| 2 | YOLOv8m fine-tuning on VisDrone | ✅ Complete |
| 3 | Density estimation & optical flow | ✅ Complete |
| 4 | Risk classification & alerts | ✅ Complete |
| 5 | Dashboard visualisation | ✅ Complete |
| 6 | Video frame pipeline | ⚠️ In Progress |
| 7 | ROS2 drone integration | 🔲 Planned |
| 8 | CSRNet density estimation | 🔲 Planned |

---
## References

- [VisDrone Dataset](https://github.com/VisDrone/VisDroneDataset)
- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- [CSRNet PyTorch](https://github.com/CommissarMa/CSRNet-pytorch)
- Du et al., VisDrone-DET2019 (arXiv:2001.03360)
