# Data Seaborn Regression Analysis
### Delivery Performance vs Customer Review Score

Bu proje, Olist e-ticaret verileri kullanılarak teslimat performansının müşteri memnuniyeti (`review_score`) üzerindeki etkisini analiz etmeyi amaçlamaktadır.  
Analiz kapsamında korelasyon incelemesi ve Seaborn tabanlı doğrusal regresyon görselleştirmeleri kullanılmıştır.

---

## Proje Amacı

Bu çalışmanın temel hedefleri şunlardır:

- Teslimat süresi (`wait_time`) ile müşteri değerlendirme puanı arasındaki ilişkiyi incelemek  
- Beklenen teslim tarihine göre gecikmenin (`delay_vs_expected`) müşteri memnuniyetini nasıl etkilediğini analiz etmek  
- Farklı örneklem büyüklükleri ve güven aralıklarının regresyon sonuçları üzerindeki etkisini gözlemlemek  
- Korelasyonun istatistiksel anlamlılığını görsel olarak değerlendirmek  

---

## Kullanılan Veri Seti

- Kaynak: Olist E-Commerce Dataset
- Veri yapısı: Sipariş bazlı teslimat ve değerlendirme bilgileri
- Hedef değişken:  
  - `review_score` (1–5 arası müşteri değerlendirme puanı)

### Analizde Kullanılan Temel Değişkenler

- `wait_time` : Siparişten teslimata kadar geçen süre (gün)
- `expected_wait_time` : Tahmini teslim süresi
- `delay_vs_expected` : Beklenen teslim tarihine göre gecikme (gün)
- `price` : Ürün fiyatı
- `freight_value` : Kargo bedeli
- `number_of_items` : Siparişteki ürün sayısı
- `number_of_sellers` : Siparişte yer alan satıcı sayısı

---

## Metodoloji

Analiz aşağıdaki adımlarla gerçekleştirilmiştir:

1. Sayısal değişkenler için korelasyon matrisi oluşturulması  
2. `review_score` ile en ilişkili değişkenlerin belirlenmesi  
3. Seaborn `regplot` kullanılarak doğrusal regresyon görselleştirmeleri  
4. Farklı örneklem büyüklükleri (`n = 300`, `3000`, `10000`) ile regresyon stabilitesinin incelenmesi  
5. Güven aralığı seviyelerinin (`ci=99`, `ci=95`, `ci=68`, `ci=None`) karşılaştırılması  

---

## Temel Bulgular

- Teslimat süresi uzadıkça müşteri memnuniyeti düşmektedir.
- Beklenen teslim tarihinin aşılması, toplam teslimat süresinden daha güçlü bir negatif etkiye sahiptir.
- Regresyon eğimleri tüm örneklem boyutlarında tutarlı şekilde negatiftir.
- Örneklem büyüklüğü arttıkça güven aralığı daralmakta ve model kararlılığı artmaktadır.
- Elde edilen ilişkiler istatistiksel olarak anlamlıdır.

---

## Önemli Not

Bu çalışma **korelasyonel bir analizdir**.  
Elde edilen sonuçlar **nedensellik kanıtı** olarak yorumlanmamalıdır.

Teslimat süresi ile müşteri memnuniyeti arasındaki ilişki şu faktörlerden etkileniyor olabilir:

- Ürün kategorisi
- Satıcı lokasyonu
- Lojistik altyapı
- Fiyat ve müşteri beklentisi

Daha güçlü çıkarımlar için çok değişkenli modeller gereklidir.

---

## Kullanılan Teknolojiler

- Python
- Pandas
- Seaborn
- Matplotlib
- Jupyter Notebook

---

## Proje Yapısı