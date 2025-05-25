# energy-consumption
Bu repo, GlobalAI Hub ve Akbank tarafından düzenlenen Makine Öğrenmesine Giriş Bootcamp kapsamında geliştirilen bir projedir.

# Giriş

Bu proje, bir fabrikanın elektrik tüketim verilerini analiz ederek **enerji kullanımını tahmin etmeyi** amaçlamaktadır. Çalışmada farklı makine öğrenmesi modelleri test edilmiş, en iyi sonuç veren model hiperparametre optimizasyonu ile geliştirilmiştir.

Modelleme süreci şu adımları kapsamaktadır:

- Veri analizi ve ön işleme  
- Değişken seçimi  
- Farklı algoritmalarla model eğitimi  
- En başarılı model için hiperparametre ayarı  
- Son modelin değerlendirilmesi ve görselleştirilmesi

---

# Kullanılan Metrikler

| Metrik  | Açıklama |
|--------|----------|
| **R² Skoru** | Modelin tahmin başarısını ve veri varyansını açıklama oranını gösterir. 1’e ne kadar yakınsa model o kadar başarılıdır. |
| **RMSE** | Hataların karesinin ortalamasının kareköküdür. Daha düşük olması tercih edilir. |
| **MAE** | Ortalama mutlak hata. Gerçek ve tahmin edilen değerler arasındaki farkların ortalamasıdır. |

---

# Model Performansı

**En iyi model:** `RandomForestRegressor`  
**Hiperparametreler (GridSearchCV):**

```python
{'max_depth': 20, 'max_features': 10, 'n_estimators': 200}
```

**Model Başarı Tablosu:**

| Metrik     | Eğitim Seti | Test Seti |
|------------|-------------|-----------|
| R² Skoru   | 0.9999      | 0.9991    |
| RMSE       | 0.39        | 1.03      |
| MAE        | 0.12        | 0.33      |

> Eğitim ve test başarıları birbirine çok yakın olduğu için **overfitting (aşırı öğrenme) problemi yoktur** yorumu yapılabilir.

---

# Veri Analizi ve Görselleştirmeler

## Günlük Enerji Kullanımı

Her bir gün için ortalama tüketimi gösterir. Zamanla artan veya azalan trendler bu grafikle izlenebilir.

![Günlük Enerji Kullanımı](https://github.com/denizyozgatli/energy-consumption/blob/main/assets/daily_energy.png?raw=true)

---

## Günün Saatine Göre Ortalama Elektrik Tüketimi

Enerji tüketiminin saatlik dağılımı, yoğun tüketim zamanlarını tespit etmek için kullanılır.

![Saatlik Tüketim](https://github.com/denizyozgatli/energy-consumption/blob/main/assets/hourly_energy.png?raw=true)

---

## Haftalık Ortalama Enerji Kullanımı ve CO₂ Miktarı

Enerji tüketimi ile karbon salımı arasındaki ilişkiyi gösterir. Çevresel sürdürülebilirlik açısından önemlidir.

![Haftalık Enerji ve CO2](https://github.com/denizyozgatli/energy-consumption/blob/main/assets/weekly_energy_co2.png?raw=true)

---

## Yük Tiplerine Göre Enerji Kullanımı

Tesisin farklı yük koşullarındaki enerji tüketimi analiz edilmiştir.

![Yük Tipi Dağılımı](https://github.com/denizyozgatli/energy-consumption/blob/main/assets/load_type_energy.png?raw=true)

---

## Sonuç ve Gelecek Çalışmalar

RandomForestRegressor modeli, yüksek başarı oranı ve düşük hata değerleri ile elektrik tüketimini tahmin etmede oldukça başarılı olmuştur. Bu model:

- Gerçek tüketimle çok yakın tahminler üretmektedir.
- Gelecekteki enerji planlamalarına yön verebilecek değerli bir öngörü modelidir.

### Eksikler ve Geliştirme Alanları

- Varsa aykırı değerler için daha detaylı ön işleme teknikleri uygulanabilir.
- Feature engineering uygulamaları ile model için daha açıklayıcı ve güçlü özellikler oluşturulabilir.

### Gelecek Planları

- Gerçek zamanlı veri akışı ile sürekli tahmin yapabilen bir sistem kurulabilir.
- Kullanıcı arayüzü olan bir web uygulaması geliştirilebilir. 
- Farklı makine öğrenmesi algoritmaları denenebilir.
- Bu proje, enerji yönetimiyle ilgilenen kurumlara sunularak, veri odaklı karar alma süreçlerini optimize etmelerine katkı sağlayabilir.

---

# Linkler

https://www.kaggle.com/code/dnzyzgtl/steel-industry-energy-consumption
