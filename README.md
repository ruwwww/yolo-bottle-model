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

Model YOLO11s 3 kelas untuk demo kasir kulkas kejujuran.

| kelas | mAP50 (val) |
|-------|-------------|
| bottle | 0.896 |
| ballpoint_box | 0.404 |
| computer_mouse | 0.958 |
| **all** | **0.748** |

- Input 640x640, arsitektur `yolo11s` (9.4M parameter)
- Dataset: https://huggingface.co/datasets/ruwwww/yolo-bottle-multiclass
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

Catatan: `ballpoint_box` masih lemah (recall 0.28) karena banyak frame
dilabeli negatif; gunakan `conf` lebih rendah atau label ulang dengan prompt
`pen box`.
