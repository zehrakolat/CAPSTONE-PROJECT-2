# The RSA Cryptosystem – Security Analysis

Bu proje, **RSA şifreleme sisteminin güvenliğini**, özellikle **tam sayı çarpanlarına ayırma algoritmaları** ve **anahtar seçimindeki zayıflıklar** üzerinden incelemektedir.  
Çalışma, teorik analizlerin yanı sıra **SageMath** kullanılarak geliştirilen **pratik kod uygulamalarını** da içermektedir.

---

## 📋 Proje Özeti

Proje, modern kriptografinin temelini oluşturan **RSA kriptosisteminin güvenliğini tehdit eden iki ana saldırı yöntemine** odaklanmaktadır:

- **Pollard’ın \( p-1 \) Algoritması**  
  \( p-1 \) değerinin *smooth* (düzgün) olması durumunu istismar eder.

- **Wiener’ın Saldırısı**  
  Küçük özel üs (\( d \)) seçiminden kaynaklanan yapısal zayıflıkları hedefler.

---

## 🛠 İncelenen Algoritmalar ve Kod Uygulamaları

### 1. RSA Temelleri

- **Anahtar Üretimi (Key Generation)**  
  Rastgele büyük asal sayılar \( p \) ve \( q \) seçilerek  
  \( N \), \( \varphi(N) \), \( e \) ve \( d \) değerleri hesaplanır.

- **Şifreleme ve Şifre Çözme**
  - Şifreleme:  
    \[
    y = x^e \bmod N
    \]
  - Şifre Çözme:  
    \[
    z = y^d \bmod N
    \]

---

### 2. Çarpanlara Ayırma Yöntemleri

- **Pollard Rho Algoritması**  
  Küçük çarpanları bulmak için kullanılan iteratif ve olasılıksal bir yöntemdir.

- **Dixon’s Algorithm**  
  Kareler ve *factor base* kullanarak çarpanlara ayırma yaklaşımı sunar.

- **Pollard \( p-1 \) Algoritması**  
  Eğer \( p-1 \) değeri belirli bir \( B \) sınırına göre *B-smooth* ise,  
  \( N \) başarılı şekilde çarpanlarına ayrılabilir.

---

### 3. Wiener’ın Saldırısı

- **Teorik Temel**  
  Eğer
  \[
  d \le \frac{N^{1/4}}{\sqrt{12}}
  \]
  koşulu sağlanıyorsa, gizli anahtar sürekli kesirler yardımıyla elde edilebilir.

- **Kullanılan Matematiksel Araçlar**
  - Sürekli Kesirler (Continued Fractions)
  - Genişletilmiş Öklid Algoritması

---

## 💻 Örnek Çalışma Sonuçları

Projede gerçekleştirilen bazı test sonuçları aşağıda verilmiştir:

- **RSA**
  - \( n = 16 \) bit, mesaj = 14  
  - Public Key: \( (187, 79) \)  
  - Private Key: \( (187, 79) \)

- **Pollard Rho**
  - \( N = 1517 \)  
  - Bulunan bölen: **37**

- **Dixon’s Algorithm**
  - \( N = 1545879895645 \)  
  - Bulunan faktör: **5**

- **Wiener’ın Saldırısı**
  - \( e = 53387 \), \( N = 82123 \)  
  - Bulunan geçerli özel anahtar:  
    \[
    d = 3
    \]

---

## 📑 Akademik Bilgiler

- **Yazar:** Zehra Kolat  
- **Danışman:** Doğa Can Sertbaş  
- **Kurum:** İstinye Üniversitesi, Matematik Bölümü  
- **Tarih:** Ocak 2025

---

## 🔧 Kullanılan Araçlar

- **SageMath**
- Python
- Number Theory ve Kriptografi algoritmaları

---
