---
library_name: ultralytics
pipeline_tag: object-detection
tags:
  - yolo
  - yolo11
  - object-detection
  - kasir-kulkas
license: other
---

# yolo-bottle-multiclass-yolo11s

Model YOLO11s 5 kelas untuk demo kasir kulkas kejujuran ES HMSI.

| kelas | Precision | Recall | mAP50 (val) | mAP50-95 |
|-------|-----------|--------|-------------|----------|
| bottle | 1.000 | 1.000 | 0.995 | 0.968 |
| teh_pucuk | 1.000 | 1.000 | 0.995 | 0.940 |
| golda | 1.000 | 1.000 | 0.995 | 0.948 |
| computer_mouse | 0.933 | 1.000 | 0.967 | 0.921 |
| ballpoint_box | 0.978 | 0.200 | 0.195 | 0.174 |
| **all** | **0.982** | **0.840** | **0.829** | **0.790** |

- Input 640x640, arsitektur `yolo11s` (9.4M parameter, 21.4 GFLOPs)
- Evaluasi pada 186 gambar validasi
- Dataset: https://github.com/ruwwww/yolo-bottle-dataset
- Kode: https://github.com/ruwwww/yolo-bottle

## Pakai

```python
from ultralytics import YOLO

model = YOLO("multiclass_best.pt")
results = model.predict("foto.jpg", conf=0.35, imgsz=640)
print(results[0].names)
```

```bash
yolo detect predict model=multiclass_best.pt source=0 conf=0.35
```
