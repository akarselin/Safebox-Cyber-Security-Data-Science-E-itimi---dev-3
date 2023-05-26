# Safebox-Cyber-Security-Data-Science-E-itimi---dev-3
Safebox Cyber Security Data Science Eğitimi - Ödev 3
Analitik SQL Nedir?
Analitik SQL, veritabani yönetim sistemlerinde kullanilan bir tür SQL sorgulama yöntemidir. Analitik SQL sorgulari, veri analizi ve raporlama gibi islemleri gerçeklestirmek için kullanilir. Bu sorgular, veri setlerindeki iliskileri, desenleri ve trendleri analiz etmeyi saglar.

Analitik SQL sorgulari genellikle GROUP BY, HAVING, COUNT, SUM, AVG, MIN, MAX, ORDER BY gibi islevleri kullanir. Bu sorgular, verileri gruplara ayirma, toplama, sayma, ortalama alma, minimum ve maksimum degerleri bulma gibi islemleri gerçeklestirir. Ayrica, analitik fonksiyonlar ve pencere fonksiyonlari gibi özel SQL fonksiyonlarini da içerebilir.

Genel Analitik SQL sorgusu: 
SELECT 
    category,
    COUNT(*) AS count,
    AVG(price) AS average_price
FROM 
    products
GROUP BY 
    category
ORDER BY 
    count DESC;

Bu sorgu, bir ürün tablosundaki ürünleri kategoriye göre gruplar ve her kategori için ürün sayisini (count) ve ortalama fiyati (average_price) hesaplar. Sonuçlari ürün sayisina göre büyükten küçüge siralar.

Bu analitik SQL sorgusu, ürünlerin kategorilere göre dagilimini ve her bir kategorinin ortalama fiyatini bulmak için kullanilabilir. Böylece isletme sahipleri veya analistler, ürün portföyü hakkinda bilgi edinerek, talebi yüksek olan kategorileri ve fiyat düzenlemeleri yapabilecekleri potansiyel firsatlari belirleyebilirler.

SQL Ve Analitik SQL Arasindaki Fark Nedir?
SQL, veritabani yönetim sistemlerinde kullanilan genel bir sorgulama dili olup, veritabanlari üzerinde veri ekleme, güncelleme, silme ve sorgulama gibi temel islemleri gerçeklestirir. Analitik SQL ise, SQL dilinin analitik islemler için kullanilan bir alt kümesidir. Analitik SQL sorgulari, veriler üzerinde daha karmasik analiz islemlerini gerçeklestirir, veri iliskilerini, desenlerini ve trendlerini analiz eder ve genellikle büyük veri kümeleriyle çalisirken performans optimizasyonu saglar. Analitik SQL, gruplama, toplama, ortalama alma, minimum ve maksimum degerleri bulma gibi islevlerin yani sira analitik fonksiyonlar ve pencere fonksiyonlarini da kullanir. Bu sayede daha derinlemesine analizler yapilabilir ve anlamli içgörüler elde edilebilir.

SORGU ÖRNEKLERI:

1.  SELECT 
       	category,
       	COUNT(*) AS count,
      	 AVG(price) AS average_price
      FROM 
      	 products
      GROUP BY 
      	 category;
Bu sorgu, bir ürün tablosundaki ürünleri kategoriye göre gruplayarak, her kategori için ürün sayisini (count) ve ortalama fiyati (average_price) hesaplar.

2. Egitimde bize verilen dvdrental datasetinde SELECT *, ROW_NUMBER() OVER(PARTITION BY category_id, ORDER BY film_id) FROM film_category; fonksiyonu analitik bir fonksiyondur ve category_id leri pencereleyerek o penceredeki film_id leri siralar.

3. DVDRENTAL.tar dosyasinda içerisinde bulunan Film Tablosu bulunan "length" grup hakkinda çalisma yaptim . 

Agg fonksiyonlarin içinde bulunan 'avg' fonksiyonu kullandim. Filmlerin ortalama uzunluklari buldum. Ve grubun ismini degistirdim.


select avg (length) as uzunluk  from film ;

4. dvdrental.tar dosyasinin içindeki örneklerde bulunan "payment" tablosu üzerinden ROUND fonksiyonu kullanim örneginde bulundum.

select payment_id, ROUND(amount,0) as FIYAT_YUVARLAMA
from payment;
Bu sayede amount yani fiyat kolonunun içindeki ondalikli sayilari virgülden sonrasini almadan yuvarlayabiliyoruz. Örnegin 0,99 olan herhangi bir ürünün fiyati yuvarladigimizda 1 olarak gözükür. Bu bize islem kolayligi saglar.
