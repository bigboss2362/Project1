# Project1
linkedin'de paylaştığım projemin tüm kodları içeren dosyaları da ekledim.

# Laborant Vardiya ve Cihaz Atama Sistemi

Bu proje, bir hastanedeki laborant ekibinin vardiya ve çalışacağı cihaz/makine/bölüm atamalarını **otomatik ve adil bir şekilde planlayan Python + SQL tabanlı bir sistemdir**. Haftalık planlama, veri analizi ve görselleştirme özelliklerini içerir.

---

## 📌 Proje Amacı

Gerçek hayatta karşılaşılan bir probleme dayanıyor:  
- Laborantların vardiyaları ve hangi cihazlarda çalışacakları sistemli bir şekilde belirlenemiyor.  
- Manuel planlama hatalara ve adaletsiz dağılımlara yol açabiliyor.  

Bu proje, hem **Python ile algoritma geliştirme**, hem de **SQL ve görselleştirme ile analitik sonuçlar elde etme** pratiği sağlamaktadır.

---

## 🛠 Kullanılan Teknolojiler

- **Python 3**: Ana programlama dili  
- **Pandas**: Veri işleme ve DataFrame yönetimi  
- **NumPy**: Sayısal hesaplamalar ve veri indeksleme  
- **DuckDB**: Python içinde SQL sorguları çalıştırmak için  
- **Matplotlib & Seaborn**: Çıktıları görselleştirmek için  
- **Random**: Rastgele seçimler yapmak için  

---

## ⚙️ Program Mantığı ve Adım Adım İşleyiş

1. **Veri Girişi**
   - Kullanıcıya basit sorular sorularak manuel input alınabilir veya  
   - Excel dosyasından çalışan ve cihaz verileri okunabilir (`deneme123.csv` örnek).

2. **Laborant Sınıfı**
   - `laborant` class’ı ile her çalışanın bilgileri tutulur: isim, cihaz bilgileri, tecrübe yılı.  
   - Birden fazla cihaz kullanabiliyorsa bunlar liste halinde saklanır.

3. **Vardiya Ataması**
   - Laborantlar **gece ve gündüz** vardiyalarına kısmen rastgele olarak atanır.  
   - Aynı kişinin **üst üste iki gün aynı cihazda çalışması engellenir**.  
   - Cihaz kapasitesi mantığı uygulanır: aynı cihazda maksimum kişi sayısı belirlenir (örn. 6 kişi).  
   - Kapasite aşıldığında uyarı verilir ve algoritma alternatif cihazları kontrol eder.

4. **Haftalık Planlama**
   - Tüm atamalar **haftalık döngü** ile gerçekleştirilir.  
   - Günlük cihaz kapasitesi ve önceki günün cihaz seçimi dikkate alınır.  
   - Sonuçlar `pandas DataFrame` formatında kaydedilir ve Excel’e aktarılır.

5. **SQL ile Analiz**
   - **DuckDB** kullanılarak DataFrame üzerinden SQL sorguları çalıştırılır:  
     - Cihaz bazlı toplam kullanım  
     - Vardiya bazlı kullanım  
     - Planlama dağılımlarının kontrolü

6. **Görselleştirme**
   - **Bar Chart**: Cihazların toplam kullanım sayıları  
   - **Pie Chart**: Cihaz kullanımının yüzdesel dağılımı  
   - **Heatmap**: Vardiya bazlı cihaz kullanım yoğunluğu  

---

## 💡 Mantık Katmanları ve Kurallar

- Çalışanlar yalnızca **bildikleri cihazlarla** görevlendirilir.  
- Aynı cihazda arka arkaya çalışmama kuralı uygulanır.  
- Cihaz kapasitesi kontrol edilir; maksimum kapasite dolduğunda algoritma uyarı verir ve alternatif cihazları değerlendirir.  
- Haftalık planlama boyunca her gün cihaz seçimleri, önceki günün cihaz kullanım bilgisi ile karşılaştırılır.  
- Rastgele seçimler ile hem adil hem de değişken vardiya atamaları sağlanır.
