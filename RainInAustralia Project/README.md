KAYNAK: https://www.kaggle.com/jsphyg/weather-dataset-rattle-package/data


Rain In Australia Deep Learning Project
https://www.kaggle.com/jsphyg/weather-dataset-rattle-package/data
1. ADIM
İlk olarak projede kullanacağım kütüphaneleri import ediyorum. Uyarıları da sessize almak için bir kod yazıyorum.


![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/a7f88379-2ef8-4cc8-8a3a-3c1a9594c3b4)



2. ADIM
Veriseti hakkında : 
Veriseti Avustralya'nın 10 yıllık hava durumunu kullanarak oluşturulmuş bir veriseti. Hedefimiz ise RainTomorrow olan sütunu doğru tahmin edebilmek. Bu da yarın yağmur yağıp yağmayacağını tahmin etmek anlamına geliyor.
“Location” sütunu verinin hangi bölgeye ait olduğu hakkında bilgi veriyor.
“Date” sütunu kaydın alındığı tarihi belirtiyor.
“MinTemp” ve “MaxTemp” ise o gün içerisinde sıcaklığın minimum ve maksimum değerlerini bildiriyor.
Saatlere göre anlık rüzgar, nem ve bulut oranı gibi değişkenler de verisetinde listelenmiş durumda. (WindDir9am, Humidity9am..)





3. ADIM
Boş verileri incelediğim zaman birçok sütunda oldukça fazla boş veri olduğunu gördüm. Bu verileri elimden geldiğince doldurarak işe başlıyorum.
 
 

4. ADIM
 
Verisetinin yeni hali : 
 




5. ADIM
 

6. ADIM
Kategorik veriler için görselleştirme yapıyorum. Bu grafikleri inceleyerek veriseti hakkında daha doğru yorumlar yapabilecek ve modelimi eğitmek için izleyeceğim yolu daha iyi belirleyeceğim.
 





7. ADIM
Kategorik verilere encoding uygulayarak verimi sayısal bir hale çevirme yolunda önemli bir adım atıyorum. 
 

8. ADIM
 


9. ADIM
 
 






Veriyi örneklendirdikten sonra 0 ve 1 oranları.

  
 
 
















10. ADIM
 
SelectKBest ve f_classif yardımıyla öğrenmeye sokacağımız verileri belirliyoruz. 



















11. ADIM
Train test split ile verileri ayırıyoruz ve öğrenmeye hazır hale getiriyoruz.
 
12. ADIM
 

13. ADIM
Modeli oluşturup train verileri ile modeli eğittikten sonra model.predict(test) yaparak tahminlemeye başlıyoruz. Tahminleri incelediğimizde ondalık sayılardan oluştuğu görülmekte. Bu tahminleri 0.5’ten büyük olup olmama durumlarına göre 0 ve 1’e yuvarlayıp tahminlemeyi bitiriyorum.




14. ADIM
Confusion Matrix’i heatmap ile bastırarak TP, TN, FP, FN değerlerini inceliyorum. Bu değerleri kullanarak da doğruluk oranımızı yani modelimizin başarı oranını hesaplayacağım.
 
Modelim %95’lik başarı elde etti
 


