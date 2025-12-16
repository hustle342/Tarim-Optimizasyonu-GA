# 🤖 BLG-307 Yapay Zeka Sistemleri - Proje 1: Kısıtlı Optimizasyon (Senaryo 4)
---

## 1. Proje ve Öğrenci Bilgileri

| **Öğrenci Adı Soyadı** | Serdar KORKMAZ |
| **Okul Numarası** | 2312729014 |
| **Ders Kodu** | BLG-307 |
| **Kullanılan Yöntem** | Genetik Algoritma |

---

## 2. Optimizasyon Problemi Tanımı

### A. Amaç Fonksiyonu (Maksimizasyon)

Bitki Verimi Puanını  maksimize etmek:

$$y = 10x_1 + 6x_2 - 0.5x_1^2 - 0.2x_2^2

### B. Kısıtlar (Sınırlar)

Algoritmanın bulduğu çözümün geçerli olması için sağlanması gereken iki kısıt:

1.  **Toprak Doygunluğu Sınırı:** x_1 + 0.1x_2 \le 60$
2.  **Minimum Su İhtiyacı:** x_2 \ge 20

---

## 3. Kullanılan Genetik Algoritma Stratejisi

| **Kodlama** | Gerçek Değerli | Sürekli değişkenlerle çalışmak. |
| **Seçim** | Rulet Seçimi | Popülasyondan en uygun bireyleri seçmek. |
| **Çaprazlama** | Aritmetik Çaprazlama | Ebeveynlerin genlerini ağırlıklı ortalama ile birleştirmek. |
| **Mutasyon** | Gauss Mutasyonu | Lokal optimumdan kaçınmak için gürültü eklemek ve sınır kontrolü yapmak. |
| **Kısıt Yönetimi** | **Hard Constraint Handling** | Kısıt ihlalinde, `uygunluk_hesapla` fonksiyonunda çözüme en kötü skor (`-1000.0`) atanmıştır. Bu sayede, Seçim operatörü geçersiz çözümleri otomatik olarak elemiştir. |

### ⚙️ Temel Parametreler
* **Popülasyon Büyüklüğü:** 100
* **Nesil Sayısı:** 150
* **Çaprazlama Oranı (Pc):** 0.8
* **Mutasyon Oranı (Pm):** 0.05

---

## 4. Elde Edilen Optimum Sonuçlar

GA, [150] nesil sonunda kısıtları sağlayan aşağıdaki optimum çözümü bulmuştur:

| Sonuç | Değer | Birim |
| :--- | :--- | :--- |
| **Optimum Gübre ($x_1$)** | [9.9637] | kg/da |
| **Optimum Sulama ($x_2$)** | [20.0321] | L/da |
| **Maksimum Verim Puanı ($y$)** | [89.9350] 

### Kısıtların Kontrolü (Başarı Kanıtı)

Bulunan optimum çözüm, tüm kısıtları sağlamaktadır:

* **Kısıt 1 Kontrolü ($x_1 + 0.1x_2$):** [11.9669] (Hedef $\le 60$) ✅
* **Kısıt 2 Kontrolü ($x_2$):** [20.0321] (Hedef $\ge 20$) ✅

---

## 5. Algoritma İlerleme Grafiği

GA, yaklaşık [120] nesilde çözüme yakınsamış (converged) ve maksimum verim puanını bulmuştur. (Ayrıntılı grafik ve kod akışı, **proje notebook dosyasında (.ipynb)** bulunmaktadır.) 

---
