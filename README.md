# 🩺 Diabetic Retinopathy & Glaucoma Segmentation  
**Fundus (retina) görüntülerinden optik disk, damar, mikroanevrizma ve eksuda segmentasyonu**  
*Konya Teknik Üniversitesi – Bilgisayar Mühendisliği Bitirme Projesi Final 1 *

---

## 📋 Proje Hakkında
Bu proje, **göz hastalıklarının erken teşhisi** için fundus görüntülerinde çeşitli yapıları otomatik olarak tespit etmeyi amaçlar.  
**Diyabetik Retinopati (DR)** hastalıklarının tanısında kritik olan **optik disk, kan damarları, mikroanevrizmalar ve eksudat** bölgeleri görüntü işleme teknikleri ile segmente edilmiştir.

> **Not:** Kullanılan ham veri seti lisans kısıtlamaları nedeniyle bu repoda yer almamaktadır.  
> Çalışmada **[IDRiD](https://idrid.grand-challenge.org/)** (Indian Diabetic Retinopathy Image Dataset) veri seti kullanılmıştır.

---

## ✨ Özellikler
- **Ön İşleme**  
  - CLAHE (Contrast Limited Adaptive Histogram Equalization) ile kontrast iyileştirme  
  - Median ve Gaussian filtreleme  
  - Renk kanalı ayrıştırma (özellikle kırmızı ve yeşil kanallar)

- **Segmentasyon**  
  - **Optik Disk**: K-means kümeleme + morfolojik işlemler  
  - **Kan Damarları**: Yeşil kanal çıkarımı + morfolojik işlemler + eşikleme  
  - **Mikroanevrizmalar**: CLAHE, gamma düzeltme, Otsu eşikleme, top-hat dönüşümü  
  - **Eksudatlar**: K-means kümeleme ve Canny kenar tespiti kombinasyonu

- **Değerlendirme**  
  - Confusion Matrix, doğruluk/duyarlılık gibi metrikler  
  - Segmentasyon sonrası görsel sonuçların karşılaştırılması

---

## 🖼️ Örnek Sonuçlar

Bu depoda **çıktı klasörü yoktur**. Segmentasyon sonuçlarının tüm örnekleri bitirme raporunda ayrıntılı olarak yer almaktadır.  
Aşağıda, rapordan seçilmiş bazı örnek segmentasyon görüntüleri verilmiştir:

### Optik Disk Segmentasyonu
<img src="https://github.com/user-attachments/assets/838dd68a-2c39-475c-8160-41b8eb94fd67" alt="Optic Disc" width="800"/>

---

### Kan Damarları
<img src="https://github.com/user-attachments/assets/fabcdddb-664c-4cfe-b721-0bac2dad4ccc" alt="Blood Vessels" width="600"/>

---

### Mikroanevrizmalar
<img src="https://github.com/user-attachments/assets/d36711b1-b6fc-4881-931f-be1e3817fcd9" alt="Microaneurysms" width="650"/>

---

### Eksudatlar
<img src="https://github.com/user-attachments/assets/c4589db4-7017-4388-9f0a-256ee6100a02" alt="Exudates" width="650"/>

---

📄 Daha fazla görsel ve detaylı açıklama için rapora göz atın:  
[**Bitirme-1_FinalRapor.pdf**](docs/Bitirme-1_FinalRapor_1docx.pdf
)

---

## 🔬 Metodoloji (Özet)
Projedeki temel adımlar:

- **Optik Disk Segmentasyonu**  
  Kırmızı kanal seçimi, CLAHE, K-means kümeleme ve morfolojik açma–kapama işlemleri
- **Kan Damarlarının Çıkarılması**  
  Yeşil kanal, median/gaussian filtreleme, CLAHE ve ikili eşikleme
- **Mikroanevrizma Tespiti**  
  CLAHE + gamma düzeltme, Otsu eşikleme, top-hat morfolojisi
- **Eksudat Segmentasyonu**  
  K-means kümeleme ve Canny kenar tespiti ile büyük ve küçük eksudaların birleştirilmesi

---

## 🏫 Proje Bilgileri
- **Üniversite**: Konya Teknik Üniversitesi – Bilgisayar Mühendisliği  
- **Ders**: Bilgisayar Mühendisliği Uygulaması – 1 (Bitirme Projesi)  
- **Proje**: Göz Hastalıklarının Görüntü İşleme ile Tespiti (Final 1)

---

## ⚙️ Kurulum
```bash
git clone https://github.com/<kullanici_adi>/diabetic-retinopathy-segmentation.git
cd diabetic-retinopathy-segmentation
pip install -r requirements.txt
