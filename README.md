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
🖼️ Örnek Sonuçlar

Bu depoda çıktı klasörü yoktur. Segmentasyon sonuçlarının tüm örnekleri bitirme raporunda ayrıntılı olarak yer almaktadır:

Segmentasyon Adımı	Rapor Görseli (PDF)
Optik Disk Segmentasyonu	Şekil 6
Kan Damarları	Şekil 7
Mikroanevrizmalar	Şekil 8
Eksudatlar	Şekil 9

👉 Bu görsellere erişmek için: docs/Bitirme-1_FinalRapor.pdf

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
