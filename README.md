# TraceGuard — PCB Hata Tespiti

Baskılı devre kartlarındaki (PCB) üretim hatalarının YOLOv8 tabanlı bir nesne tespiti modeliyle otomatik olarak tespit edildiği bir Otomatik Optik İnceleme (AOI) sistemi prototipi.

## 📋 Proje Özeti

Elektronik üretim hatlarında kalite kontrol sürecini otomatikleştirmek amacıyla, PCB görüntüleri üzerinde 6 farklı hata tipini tespit edebilen bir yapay zeka modeli geliştirilmiştir.

**Tespit Edilebilen Hata Tipleri:**
- Eksik Delik (Missing Hole)
- Fare Isırığı (Mouse Bite)
- Açık Devre (Open Circuit)
- Kısa Devre (Short)
- Çıkıntı / İğne Ucu (Spur)
- İstenmeyen Bakır Artığı (Spurious Copper)

## 🎯 Model Performansı (Test Verisi Üzerinde)

| Metrik | Değer |
|---|---|
| mAP50 | %86.1 |
| Precision | %88.3 |
| Recall | %81.8 |
| İşlem Hızı (GPU) | ~20 FPS |

## 🛠️ Kullanılan Teknolojiler

- **Model:** YOLOv8n (Ultralytics) — Transfer Learning
- **Veri Seti:** [Kaggle PCB Defects Dataset](https://www.kaggle.com/datasets/akhatova/pcb-defects)
- **Eğitim Ortamı:** Google Colab (Tesla T4 GPU)
- **Demo Arayüzü:** Gradio

## 📁 Dosyalar

- `TraceGuard.ipynb` — Veri analizi, model eğitimi, değerlendirme ve Gradio arayüz kodlarının tamamı
- `best.pt` — Eğitilmiş model ağırlıkları

## 🚀 Kullanım

Notebook'u Google Colab'da açıp GPU ortamıyla çalıştırarak modeli yeniden eğitebilir veya doğrudan `best.pt` dosyasını kullanarak çıkarım (inference) yapabilirsiniz.

```python
from ultralytics import YOLO
model = YOLO("best.pt")
results = model("pcb_görsel.jpg")
```

## 👤 Geliştiren

Emin Ülgüç — Manisa Celal Bayar Üniversitesi, Bilgisayar Mühendisliği
