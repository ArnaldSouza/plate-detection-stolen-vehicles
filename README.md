# Vehicle License Plate Detection for Stolen Car Identification

Computer Engineering Final Project — Facens, 2025

Hybrid computer vision pipeline combining **YOLO + Faster R-CNN + OCR** to automatically detect and read license plates from surveillance camera footage, with application in stolen vehicle identification.

> Full-stack implementation: [PlateDetectionForStolenVehicles](https://github.com/ArnaldSouza/PlateDetectionForStolenVehicles)

---

## Results

| Model | Precision | Recall | mAP@0.5 |
|---|---|---|---|
| YOLOv11-nano | 94.4% | 95.6% | 99.2% |
| Faster R-CNN (ResNet50-FPN) | 82.0% | 99.9% | 90.1% |
| EasyOCR (plate accuracy) | — | — | 86.0% |

- Inference speed: ~41 fps on GPU (NVIDIA Tesla T4)
- Global pipeline accuracy: 86%
- Training time: ~3h 40min on Google Colab GPU

---

## Pipeline

```
Input image
    └── YOLOv11-nano          → fast plate detection
        └── Faster R-CNN      → refinement on low-confidence detections
            └── OpenCV        → preprocessing (grayscale, blur, threshold)
                └── EasyOCR   → character extraction
```

---

## Stack

- Python · PyTorch · Torchvision
- YOLOv11 (Ultralytics) · Faster R-CNN (ResNet50-FPN)
- OpenCV · EasyOCR
- Google Colab (GPU: Tesla T4)
- Dataset: UFPR-ALPR (4,500 labeled images)

---

## Dataset

[UFPR-ALPR](https://web.inf.ufpr.br/vri/databases/ufpr-alpr/) — 4,500 images from 150 vehicles, captured with 3 different devices under real conditions (both vehicle and camera in motion).

Split: 40% train / 20% validation / 40% test

---

## Authors

## Authors
- Arnald Souza · [LinkedIn](https://www.linkedin.com/in/arnaldsouza/) · [GitHub](https://github.com/ArnaldSouza)
- Bruno Gabriel de Oliveira Targa · [LinkedIn](https://www.linkedin.com/in/brunotarga/)
- Victor Soares Nunes Pires de Oliveira · [LinkedIn](https://www.linkedin.com/in/victorpioli/)

Advisor: Prof. Allan Marconato Marum — Centro Universitário Facens
