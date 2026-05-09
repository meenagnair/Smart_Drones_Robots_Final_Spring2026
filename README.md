# Smart Drones Final Project For Spring 2026
computer vision system intended for use with aerial drone footage in order detect conditions of crowd crush events in real time

---
## Overview
Crowd crush is the term used to describe when a crowd becomes so dense that fatalities can occur from compressive asphyxia caused by high crowd density.

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
## References

- [VisDrone Dataset](https://github.com/VisDrone/VisDroneDataset)
- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- [CSRNet PyTorch](https://github.com/CommissarMa/CSRNet-pytorch)
- Du et al., VisDrone-DET2019 (arXiv:2001.03360)
