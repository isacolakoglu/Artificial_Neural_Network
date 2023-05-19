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

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/165f992f-13b2-4248-920e-d5663e1bd30f)

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/c853876d-8672-4af5-a275-4c4c67d63049)


4. ADIM

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/73ed068f-6603-4b73-a187-16f104e412e3)

Verisetinin yeni hali : 

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/05c62f3a-9296-4b71-9b2d-3c3bb1272813)


5. ADIM

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/b5e404e8-55cb-489e-8c1e-a9eb3a777f9f)


6. ADIM
Kategorik veriler için görselleştirme yapıyorum. Bu grafikleri inceleyerek veriseti hakkında daha doğru yorumlar yapabilecek ve modelimi eğitmek için izleyeceğim yolu daha iyi belirleyeceğim.
 
![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/0a7ef172-0a6c-4e02-b98a-985f8f0f0be3)


7. ADIM
Kategorik verilere encoding uygulayarak verimi sayısal bir hale çevirme yolunda önemli bir adım atıyorum. 

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/a13383aa-674e-464c-9693-9c019c43fa3b)


8. ADIM

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/9bfeb084-924e-4672-a68d-5c8a76c3af61)


9. ADIM
 
![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/150c3bd8-dec5-4627-a7d7-2b9cdffd9b26)

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/9f0a4fdb-689a-4c21-b964-081be85b4b3c)

Veriyi örneklendirdikten sonra 0 ve 1 oranları.

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/ac0bd1b0-4873-4d1e-b4f5-f03613787ed5)

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/b8176bda-9bc4-4338-bc4e-4721355dbd80)

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/df5766bd-1594-4e08-b313-76b97c754ac3)

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/af0a19d6-7744-4f06-b224-77e152a956c2)

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/6c1dca42-bc97-4b61-b450-524eb46b3bc2)

 
10. ADIM

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/b6b4f5b2-dae3-409d-a09c-2ef2f83f4e39)

SelectKBest ve f_classif yardımıyla öğrenmeye sokacağımız verileri belirliyoruz. 


11. ADIM
Train test split ile verileri ayırıyoruz ve öğrenmeye hazır hale getiriyoruz.
 
![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/b69008f1-cd64-4a9e-a7d4-6296514f8571)


12. ADIM

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/c99e596f-e344-4b40-8a03-242b5280a7bd)


13. ADIM

Modeli oluşturup train verileri ile modeli eğittikten sonra model.predict(test) yaparak tahminlemeye başlıyoruz. Tahminleri incelediğimizde ondalık sayılardan oluştuğu görülmekte. Bu tahminleri 0.5’ten büyük olup olmama durumlarına göre 0 ve 1’e yuvarlayıp tahminlemeyi bitiriyorum.


14. ADIM
Confusion Matrix’i heatmap ile bastırarak TP, TN, FP, FN değerlerini inceliyorum. Bu değerleri kullanarak da doğruluk oranımızı yani modelimizin başarı oranını hesaplayacağım.

![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/a52cb083-32f9-42a2-981d-52614d81e1ed)

 
Modelim %95’lik başarı elde etti
 
![image](https://github.com/isacolakoglu/Artificial_Neural_Network/assets/85408010/e1e06cf2-bf7a-412c-9081-493f7ed4b7ad)


