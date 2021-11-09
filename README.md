Öğrenciler için  öğrenci numarası ile sisteme giriş yaplılan  , bir ders için  vize, final ,ödev notları ve  yoklama sayısı ile notların ortalaması çıkarıp bunu hem sayısal not olarak hemde harf notu olarak  ad,soyad,not,harf notu , ders geçildimi/geçilmedimi olarak yazan ve bilgisayarda bir txt dosyası oluşturarak içine yazıp kaydeden bir program.

Program çalıştırıldıktan sonra girilen öğrenci numarası sistemde kayıtlı ise girilen numara ile kayıtlı tüm bilgileri ekrana getirir. Eğer numara sistemde kayıtlı değilse yeni bir not hesabı kaydı oluşturulabilir hatta istenilirse kayıtlı olan bir numara hakkında bilgiler silinebilir ve üstüne güncellenebilir. 

```
import os
import time
os.chdir(os.path.expanduser("~"))
klasor='Deneme'
try:
    os.mkdir(klasor)    
except FileExistsError:        
 os.chdir("./Deneme")
 num=int(input("İşlem yapmak için öğrenci numaranızı giriniz\n"))
 num2=str(num)
while True: 
 if os.path.isfile(num2+".txt"):
   with open(num2+".txt","r") as f:
    print(f.readline())
    print(f.readline())
    print(f.readline())
    print(f.readline())
    print(f.readline())   
    time.sleep(1)
    g=input("Kaydınızı güncellemek için 1 yazın , çıkmak için istediğiniz tuşa basınız\n")
    if g == "1":
     f.close()
     os.remove(num2+".txt")
     continue
    else :
     print("Çıkış Yapıldı")
     raise SystemExit
     break
 else: 
   print("Not Kaydınız bulunamadı\n")
   c=input("Yeni Kayıt oluşturmak için 1 yazın , çıkmak için istediğiniz tuşa basınız\n")
   if c == "1":
    True
   else :
    print("Çıkış Yapıldı")
    raise SystemExit
   ad=(input("Adınız "))
   soyad=(input("Soyadınız "))   
   while True:
     v1=float(input("Vize 1 notunuzu giriniz\n"))
     v2=float(input("Vize 2 notunuzu giriniz\n"))
     f=float(input("Final notunuzu giriniz\n"))
     y=float(input("Yoklama Sayınızı giriniz\n"))
     ö=float(input("Ödev notunuzu giriniz\n"))
     ort=(float(v1)+float(v2))/2 
     vort2=float(ort*0.25)+float(y*0.05)+float(ö*0.10)+float(f*0.6)     
     vort=int(vort2)
     vort3=str(vort2)
     if vort<=100 and vort>=0 : 
      True     
     else:     
      print("Notlarınızı yanlış girdiniz kontrol edin.")
      continue
     print("\n")
     print(ad.title(),soyad.title())
     print("Başarı Notunuz",vort)
     with open(num2+".txt","w") as f: 
      f.writelines(["{} Numaralı Öğrenciye ait kayıtlar:\n".format(num)])
      f.writelines([ad.title()," "])
      f.writelines([(soyad.title()),"\n"])
      f.writelines(["Başarı notunuz: {}\n".format(vort3)])
      if vort<=100 and vort>92.5 :      
        print("Harf Notunuz A")
        f.writelines(("Harf Notunuz A\n"))
      elif vort<=92.5 and vort>82.5 :
        print("Harf Notunuz A-")
        f.writelines("Harf Notunuz A-\n")
      elif vort<=82.5 and vort>75 :
        print("Harf Notunuz B+")
        f.writelines("Harf Notunuz B+\n")
      elif vort<=75 and vort>67.5 :
        print("Harf Notunuz B")
        f.writelines("Harf Notunuz B\n")
      elif vort<=67.5 and vort>57.5 :
        print("Harf Notunuz B-")
        f.writelines("Harf Notunuz B-\n")
      elif vort<=57.5 and vort>50 :   
        print("Harf Notunuz C+")
        f.writelines("Harf Notunuz C+\n")
      elif vort==50 :
       print("Harf Notunuz C")
       f.writelines("Harf Notunuz C\n")
      elif vort<50 and vort>42.5 :
       print("Harf Notunuz C-")
       f.writelines("Harf Notunuz C-\n")
      elif vort<=42.5 and vort>32.5 :
       print("Harf Notunuz D+")
       f.writelines("Harf Notunuz D+\n")
      elif vort<=32.5 and vort>25 :
       print("Harf Notunuz D")
       f.writelines("Harf Notunuz D\n")
      elif vort<=25 and vort>17.5 :
       print("Harf Notunuz D-")
       f.writelines("Harf Notunuz D-\n")
      elif vort<=17.5 and vort>=0 :
       print("Harf Notunuz F")
       f.writelines("Harf Notunuz F\n")       
      if vort<=100 and vort>=50 :
        print("Dersi başarıyla geçtiniz")
        f.writelines("Dersi başarıyla geçtiniz")
      elif vort<50 and vort>=17.5 :
        print("Dersi kusurlu geçtiniz")
        f.writelines("Dersi kusurlu geçtiniz")  
      elif vort<17.5 and vort>=0 :
        f.writelines("Dersten kaldınız")
        print("Dersten kaldınız")  
      break
 break
time.sleep(7)      
```     
     
 
 

