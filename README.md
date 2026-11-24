# satis-performans-analizi
# Perakende Satış Performans Dashboard'u
Çok mağazalı bir perakende zincirinin **satış, kârlılık, ürün ve bölge performansını** tek yerden izlemeyi sağlayan, 3 sayfalı interaktif Power BI dashboard'u. Proje; veri setinin oluşturulması ve temizlenmesinden veri modelinin kurulmasına, KPI'ların tanımlanmasından dashboard tasarımına kadar uçtan uca bir analitik sürecini kapsar.

> **Not:** Bu projede kullanılan veri seti **sentetiktir**; gerçek bir işletmeye ait değildir. Amaç, gerçek bir iş senaryosunu temsil eden bir ortamda BI becerilerini göstermektir.

---

## 📑 İçindekiler

1. [Proje Amacı](#-proje-amacı)
2. [Dashboard Sayfaları](#-dashboard-sayfaları)
3. [Takip Edilen KPI'lar](#-takip-edilen-kpilar)
4. [Etkileşim Özellikleri](#-etkileşim-özellikleri)
5. [Veri Seti](#-veri-seti)
6. [Veri Modeli](#-veri-modeli)
7. [DAX Ölçüleri](#-dax-ölçüleri)
8. [Öne Çıkan Bulgular](#-öne-çıkan-bulgular)
9. [Kullanılan Araçlar](#-kullanılan-araçlar)
10. [Sınırlılıklar ve Geliştirme Fikirleri](#-sınırlılıklar-ve-geliştirme-fikirleri)

---

## 🎯 Proje Amacı

Bir perakende zincirinin yönetiminin günlük olarak sorduğu sorulara hızlı ve görsel cevap vermek:

- Toplam ciro, kâr ve kâr marjı nasıl seyrediyor?
- Hangi ürün kategorileri ve ürünler cironun ana kaynağı?
- Hangi bölgeler ve mağazalar en iyi performansı gösteriyor?
- Satışlar zaman içinde nasıl değişiyor, hangi aylar öne çıkıyor?
- Mağaza sayısı ile ciro arasındaki ilişki nasıl?

Dashboard; yıl ve bölge filtreleriyle bu soruların cevabını birkaç tıkla, farklı kırılımlarda görmeyi sağlar.

---

## 🖥️ Dashboard Sayfaları

### 1. Ana Sayfa

Genel performansın özetlendiği sayfa.

<img width="1434" height="840" alt="image" src="https://github.com/user-attachments/assets/be41e74c-6506-4ef1-9503-e74101a1c08d" />

| Bileşen | Ne gösterir? |
|---|---|
| KPI kartları | Toplam Ciro, Ortalama Sepet Tutarı, Brüt Kâr Marjı %, Toplam Sipariş, Toplam Kâr |
| Kategorilere Göre Ciro Dağılımı | Halka grafik ile her kategorinin cirodaki payı |
| Aylık Toplam Satış | Aylara göre satış tutarı |
| Bölgelere Göre Ciro Dağılımı | Bölge bazında ciro karşılaştırması |
| En Çok Satan Ürünler | Satış tutarına göre ürün sıralaması |

### 2. Ürün Analizi

Kategori ve ürün düzeyinde detay.

<img width="1432" height="840" alt="image" src="https://github.com/user-attachments/assets/4fc7507d-ec85-4acf-876e-069f82002f20" />

| Bileşen | Ne gösterir? |
|---|---|
| Yıl-Ay ve Kategori Bazlı Satış Tutarı | Kategorilerin zaman içindeki satış seyri (çizgi grafik) |
| Kategoriye Göre Brüt Kâr Toplamı | Her kategorinin toplam brüt kâra katkısı (şelale grafik) |
| Ürün Adına Göre Toplam Satış Tutarı | En yüksek ciro getiren ürünler |
| Kategoriye Göre Satış Miktarı | Kategori bazında satılan adet |
| Kategoriye Göre Satış Tutarları Toplamı | Kategorilerin ciro payı (treemap) |

### 3. Mağaza & Bölge Analizi

Coğrafi ve mağaza bazlı performans.

<img width="1437" height="839" alt="image" src="https://github.com/user-attachments/assets/fe5fb224-5f44-4dd0-b65b-5f0769ec2193" />


| Bileşen | Ne gösterir? |
|---|---|
| KPI kartları | Toplam Mağaza, Mağaza Başına Ortalama Satış, Toplam Ciro, En İyi Mağaza, En İyi Bölge |
| Mağaza Bazında Ciro | Mağazaların ciroya göre sıralaması |
| Aylık Ciro Trendi | Aylara göre ciro değişimi (alan grafik) |
| Bölgelere Göre Mağaza Dağılımı | Hangi bölgede kaç mağaza var |
| Bölge Bazında Ciro | Bölgelerin toplam cirodaki payı |

---

## 📌 Takip Edilen KPI'lar

| KPI | Açıklama |
|---|---|
| **Toplam Ciro** | Seçili filtrelerdeki toplam satış tutarı |
| **Toplam Kâr** | Toplam brüt kâr |
| **Brüt Kâr Marjı %** | Toplam kârın ciroya oranı |
| **Toplam Sipariş** | Gerçekleşen sipariş sayısı |
| **Ortalama Sepet Tutarı** | Sipariş başına ortalama harcama |
| **Toplam Mağaza** | Aktif mağaza sayısı |
| **Mağaza Başına Ortalama Satış** | Ciro / mağaza sayısı |
| **En İyi Mağaza / En İyi Bölge** | Ciroda lider mağaza ve bölge |

---

## 🕹️ Etkileşim Özellikleri

- **Sayfa navigasyonu:** Sol paneldeki butonlarla (Ana Sayfa, Ürün Analizi, Mağaza & Bölge Analizi) sayfalar arası geçiş
- **Dilimleyiciler (slicer):** Yıl (2024, 2025, 2026) ve Satış Bölgeleri filtreleri tüm sayfalara uygulanır
- **Çapraz filtreleme (cross-filter):** Bir grafikte seçilen öğe (ör. bir ay, kategori veya bölge) diğer görselleri günceller
- **Kaydırılabilir listeler:** Çok sayıda ürün ve mağaza içeren grafiklerde kaydırma ile detaya inme
- **Tutarlı tasarım:** Tüm sayfalarda aynı renk paleti ve yerleşim

---

## 🗂️ Veri Seti

Çok mağazalı bir perakende zincirinin satış işlemlerini temsil eden **sentetik** bir veri setidir.

**Kapsam**

- **15 mağaza**, **6 satış bölgesi** (Marmara, İç Anadolu, Karadeniz, Akdeniz, Ege, Güneydoğu Anadolu)
- **5 ürün kategorisi:** Elektronik, Ev & Yaşam, Giyim, Spor, Kozmetik
- Ürün düzeyinde kırılım (ör. Akıllı Telefon, Tablet, Akıllı Saat, Laptop modelleri)
- Dönem: [başlangıç tarihi] – [bitiş tarihi]; yıl filtresi 2024, 2025 ve 2026'yı kapsar

**Başlıca alanlar**

| Alan | Açıklama |
|---|---|
| Tarih (Yıl, Ay Adı, Yıl-Ay) | Sipariş tarihi ve zaman kırılımları |
| StoreName | Mağaza adı |
| Region | Mağazanın bağlı olduğu satış bölgesi |
| Category | Ürün kategorisi |
| ProductName | Ürün / model adı |
| Quantity | Satılan adet |
| SalesAmount | Satış tutarı (₺) |
| GrossProfit | Brüt kâr (₺) |

### Veri Hazırlama (Temizleme) Adımları

Ham veri, Power Query kullanılarak analiz için hazırlandı:

- [Eksik değerlerin tespiti ve doldurulması / çıkarılması]
- [Tekrar eden kayıtların temizlenmesi]
- [Veri tiplerinin düzeltilmesi: tarih, sayısal, metin]
- [Tutarsız isimlerin standartlaştırılması: mağaza, bölge, kategori]
- [Takvim alanlarının (Yıl, Ay, Yıl-Ay) türetilmesi]

---

## 🧩 Veri Modeli

Model, analizlerin hızlı ve doğru çalışması için **fact (olgu) ve dimension (boyut) tabloları** mantığıyla kurulmuştur.

| Tablo | Tür | Açıklama |
|---|---|---|
| [Satışlar] | Fact | Satış işlemleri: adet, tutar, brüt kâr |
| [Ürünler] | Dimension | Ürün adı, kategori |
| [Mağazalar] | Dimension | Mağaza adı, bölge |
| [Takvim] | Dimension | Tarih, yıl, ay, yıl-ay |

**İlişkiler:** [Örn. Ürünler (1) → Satışlar (N), Mağazalar (1) → Satışlar (N), Takvim (1) → Satışlar (N)]

![Veri Modeli](docs/screenshots/04-veri-modeli.png)

---

## 🧮 DAX Ölçüleri

```dax
Toplam Ciro = SUM ( Satışlar[SalesAmount] )

Toplam Kâr = SUM ( Satışlar[GrossProfit] )

Brüt Kâr Marjı % = DIVIDE ( [Toplam Kâr], [Toplam Ciro] )

Toplam Sipariş = COUNTROWS ( Satışlar )

Ortalama Sepet Tutarı = DIVIDE ( [Toplam Ciro], [Toplam Sipariş] )

Toplam Mağaza = DISTINCTCOUNT ( Mağazalar[StoreName] )

Mağaza Başına Ortalama Satış = DIVIDE ( [Toplam Ciro], [Toplam Mağaza] )
```

`DIVIDE` fonksiyonu, sıfıra bölme durumunda hata yerine boş değer döndürdüğü için tercih edilmiştir.

---

## 🔍 Öne Çıkan Bulgular

> Aşağıdaki bulgular 2026 filtresiyle elde edilen görünüme dayanır ve sentetik veriye aittir.

**Bölge performansı**

- Toplam ciro yaklaşık **₺40,8M**; mağaza başına ortalama satış yaklaşık **₺2,72M**.
- **Marmara** (₺11,13M, %27,3) ve **İç Anadolu** (₺9,94M, %24,4) birlikte cironun yaklaşık yarısını oluşturuyor.
- İki bölgenin de **4'er mağazası** var. Yani liderliklerinde mağaza sayısı büyük rol oynuyor.
- Mağaza başına ciroya bakıldığında tablo değişiyor: **Karadeniz** (2 mağaza, ₺5,83M) mağaza başına yaklaşık **₺2,9M** ile öne çıkarken, İç Anadolu yaklaşık **₺2,5M** ile en düşük seviyede. Bu, yeni mağaza yatırımında bölge seçimi için bir ipucu verir.
- **Güneydoğu Anadolu** tek mağazayla (%6,85) en küçük paya sahip.

**Kategori ve ürün performansı**

- **Elektronik**, hem ciroda hem brüt kârda açık ara en büyük kategori.
- **Kozmetik**, satılan adet bakımından lider ama ciroda en küçük paylardan birinde. Düşük birim fiyatlı, yüksek hacimli bir kategori.
- Elektronik, benzer adetlerle çok daha yüksek ciro üretiyor. Yani cironun asıl kaynağı hacimden çok birim fiyat.
- En çok satan ürünler arasında **Akıllı Telefon Model-4**, **Tablet Model-1** ve **Akıllı Saat Model-3** öne çıkıyor; ilk sıralar elektronik ürünlerde toplanıyor.

**Kârlılık**

- Brüt kâr marjı yaklaşık **%30,7**.

---

## 🛠️ Kullanılan Araçlar

| Araç | Kullanım amacı |
|---|---|
| **Power BI Desktop** | Dashboard tasarımı ve etkileşimli raporlama |
| **Power Query** | Veri temizleme ve dönüştürme |
| **DAX** | KPI ve hesaplanan ölçüler |
| **Excel** | Veri seti kaynağı |

---

## ⚠️ Sınırlılıklar ve Geliştirme Fikirleri

**Sınırlılıklar**

- Veri sentetiktir; gerçek müşteri davranışını ve mevsimselliği tam yansıtmayabilir.
- Son dönem ayları [kısmi veri içerebilir]; bu aylardaki düşüşler gerçek bir performans kaybı olarak yorumlanmamalıdır.

**Geliştirme fikirleri**

- Geçen yılın aynı dönemiyle karşılaştırma (YoY) ve büyüme oranı ölçüleri
- Hedef–gerçekleşen karşılaştırması (bütçe/hedef verisi ile)
- Mağaza başına ciro ve m² verimliliği analizi
- Müşteri/sadakat verisi eklenerek segment analizi
- Power BI Service'e yayımlama ve zamanlanmış veri yenileme

---
