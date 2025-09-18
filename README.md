# 🩺 Diabetic Retinopathy & Glaucoma Segmentation  
**Fundus (retina) görüntülerinden optik disk, damar, mikroanevrizma ve eksuda segmentasyonu**  
*Konya Teknik Üniversitesi – Bilgisayar Mühendisliği Bitirme Projesi*

---

## 📋 Proje Hakkında
Bu proje, **göz hastalıklarının erken teşhisi** için fundus görüntülerinde çeşitli yapıları otomatik olarak tespit etmeyi amaçlar.  
 **Diyabetik Retinopati (DR)** hastalıklarının tanısında kritik olan **optik disk, kan damarları, mikroanevrizmalar ve eksudat** bölgeleri görüntü işleme teknikleri ile segmente edilmiştir.

> **Not:** Kullanılan ham veri seti lisans kısıtlamaları nedeniyle bu repoda yer almamaktadır.  
> Çalışmada **[IDRiD](https://idrid.grand-challenge.org/)** (Indian Diabetic Retinopathy Image Dataset) veri seti kullanılmıştır.

---

## ✨ Özellikler
- **Ön İşleme**:  
  - CLAHE (Contrast Limited Adaptive Histogram Equalization) ile kontrast iyileştirme  
  - Median ve Gaussian filtreleme  
  - Renk kanalı ayrıştırma (özellikle kırmızı ve yeşil kanallar)

- **Segmentasyon**:  
  - **Optik Disk**: K-means kümeleme + morfolojik işlemler  
  - **Kan Damarları**: Yeşil kanal çıkarımı + morfolojik işlemler + eşikleme  
  - **Mikroanevrizmalar**: CLAHE, gamma düzeltme, Otsu eşikleme, top-hat dönüşümü  
  - **Eksudatlar**: K-means kümeleme ve Canny kenar tespiti kombinasyonu

- **Değerlendirme**:  
  - Confusion Matrix, doğruluk/duyarlılık gibi metrikler
  - Segmentasyon sonrası görsel sonuçların karşılaştırılması

---

## 🗂️ Proje Yapısı (Önerilen)
diabetic-retinopathy-segmentation/
│
├─ src/
│ ├─ # Optik disk, damar, mikroanevrizma, eksuda kodları
├─ samples/ # Veri setinden izinli örnek fundus görselleri
├─ outputs/ # Segmentasyon maskeleri ve sonuç görselleri
├─ docs/ # Bitirme raporu ve diyagramlar
│
├─ requirements.txt
├─ README.md
└─ .gitignore

---

## 🚀 Kurulum
```bash
git clone https://github.com/<kullanici_adi>/diabetic-retinopathy-segmentation.git
cd diabetic-retinopathy-segmentation
pip install -r requirements.txt
Gereken Kütüphaneler
Python 3.10+
opencv-python
numpy
scikit-image
scikit-learn
matplotlib

🖼️ Örnek Sonuçlar
Girdi Fundus Görseli	Optik Disk Maskesi	Kan Damarları	Mikroanevrizmalar

(Bu görseller, IDRiD veri setinden alınan küçük örneklerden türetilmiş maskeleri göstermektedir.)

🔬 Metodoloji (Özet)
Projedeki temel adımlar:

Optik Disk Segmentasyonu

Kırmızı kanal seçimi, CLAHE, K-means kümeleme ve morfolojik açma-kapama işlemleri

Kan Damarlarının Çıkarılması

Yeşil kanal, median/gaussian filtreleme, CLAHE ve ikili eşikleme

Mikroanevrizma Tespiti

CLAHE + gamma düzeltme, Otsu eşikleme, top-hat morfolojisi

Eksudat Segmentasyonu

K-means kümeleme ve Canny kenar tespiti ile büyük ve küçük eksudaların birleştirilmesi



📚 Kaynakça
Bu proje aşağıdaki çalışmalardan ilham almıştır (raporda ayrıntılı liste):

Melo et al., Computers in Biology and Medicine, 2020

Tanyıldızı & Okur, Fırat Üniversitesi Müh. Bilimleri Dergisi, 2016

Maison et al., Journal of Physics: Conference Series, 2019

Spencer et al., Computers and Biomedical Research, 1996

Sreng et al., IEEE Conference on Biomedical Engineering, 2017

ve diğerleri… (detaylar için docs/Bitirme-1_FinalRapor.pdf dosyasına bakınız)

🏫 Proje Bilgileri
Üniversite: Konya Teknik Üniversitesi – Bilgisayar Mühendisliği
Bitirme projesi -Final1 projesi 

📜 Lisans
Bu proje MIT Lisansı ile sunulmuştur. Ayrıntılar için LICENSE dosyasına bakınız.
