# BLG-307 Yapay Zeka Sistemleri – 1. Proje Ödevi  
## Genetik Algoritma ile Sunucu Performans Optimizasyonu  
**Öğrenci:** Rabia Çolak  
**Numara:** 2212721008  
**Senaryo:** 8 – Web Sunucusu Ayarları Optimizasyonu  

---

## 📌 Proje Açıklaması
Bu projede Genetik Algoritma (GA) kullanılarak bir web sunucusunun donanım ayarlarının  
(CPU çekirdek sayısı ve RAM miktarı) **maksimum performansı** verecek şekilde optimize edilmesi amaçlanmıştır.

Amaç fonksiyonu tamamen ödev için üretilmiş olup şu şekildedir:

\[
y = 5x_1 + 7x_2 - 0.1x_1^2 - 0.2x_2^2
\]

Bu fonksiyon **maksimize edilecektir**.

---

## 📌 Değişkenler (Decision Variables)
| Değişken | Açıklama | Aralık |
|---------|----------|--------|
| x₁ | CPU çekirdek sayısı | 2 – 12 |
| x₂ | RAM miktarı (GB) | 4 – 64 |

---

## 📌 Kısıtlar
- x₁ ≥ 4  
- x₁ * x₂ ≤ 512  
- x₁ ∈ [2,12]  
- x₂ ∈ [4,64]

---

## 📌 Genetik Algoritma Yapısı
Proje boyunca kullanılan GA bileşenleri:

### ✔ Birey Temsili  
Her birey: `[x₁, x₂]` şeklinde tutulmuştur.

### ✔ Başlangıç Popülasyonu  
Popülasyon büyüklüğü: **30**

### ✔ Seçim Mekanizması  
**Roulette Wheel Selection** yöntemi kullanılmıştır.  
Bu yöntemde bireylerin seçilme olasılığı fitness değerleri ile orantılıdır.


### ✔ Çaprazlama (Crossover)  
**Tek noktalı çaprazlama** yöntemi kullanılmıştır.  
İlk gen bir ebeveynden, ikinci gen diğer ebeveynden alınmıştır.


### ✔ Mutasyon  
- x₁ genine ±1 değişim  
- x₂ genine ±4 değişim  
- Mutasyon olasılığı: **0.2**

### ✔ Kısıt Onarım Fonksiyonu  
Oluşan bireylerin kısıtları ihlal etmesi durumunda birey onarılmıştır.

### ✔ Nesil Sayısı  
Toplam: **100 nesil**

---

## 📌 Sonuçlar

Genetik algoritma sonucunda elde edilen en iyi çözüm:

- **CPU (x₁): 12 çekirdek**  
- **RAM (x₂): 18 GB**  
- **Maksimum performans skoru: 106.80**

---

## 📈 Fitness Grafiği

Algoritma boyunca nesillere göre en iyi fitness değeri:

> İlk 10–15 nesilde hızlı yükseliş,  
> 20. nesilden sonra plato,  
> Yani algoritma optimum çözümü bulup kararlı hale gelmiştir.

(Not: Grafiğin oluşturulması için notebook dosyasına bakınız.)

---

## 📁 Dosya Yapısı

```text
├── README.md
├── blg307_genetik_optimizasyon.ipynb


## ⚙️ Kurulum ve Çalıştırma Yönergeleri

Bu proje Python dili kullanılarak geliştirilmiştir ve
Google Colab ortamında çalıştırılabilir.

### 🔹 Gereksinimler
- Python 3.x
- NumPy
- Matplotlib

Gerekli kütüphaneler Colab ortamında varsayılan olarak yüklüdür.
Yerel ortamda çalıştırmak isteyen kullanıcılar için
aşağıdaki komut ile eksik kütüphaneler kurulabilir:

```bash
pip install numpy matplotlib



