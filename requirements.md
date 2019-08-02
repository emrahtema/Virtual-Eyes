# Requirements

Firstly install Anaconda from the official site and setup that:

    - https://www.anaconda.com/

Write the commands on the Anaconda Prompt or in a terminal and execute them to install the requirement.

- Google text to speech api:

        pip install --upgrade google-cloud-texttospeech
        
- Google translation api:

        pip install --upgrade google-cloud-translate
        
- Google vision api:

        pip install --upgrade google-cloud-vision
        
- OpenCV:

    Install from: https://opencv.org/releases.html
    
    Setup by following the steps:

    Linux için konsola "sudo apt install python-opencv" komutunu girmek yeterli

    Windows için Son versiyonun "Win Pack" kütüphane dosyası indirilir. İndirilen dosya çalıştırılınca içindekilerin çıkarılmasını istediği yeri sorar. Direkt olarak C: dizinine çıkarma işlemi yapılır. Çıkan dosya "C:\OpenCV" isminde olmalıdır ve içerisinde "C:\OpenCV\build" ve "C:\OpenCV\resources" şeklinde klasörler bulunur (dizin hiyerarşisine dikkat edilmelidir).

    "C:\OpenCV\build\x64\vc14\bin" adresini kopyalıyoruz. Bunu ortam değişkenlerine eklemek gerekecek (vc14 versiyon ile alakalıdır, eğer daha altı, yada vc15 ve üstü kullanılıyorsa ona göre ilgili klasör seçilmeli).

    "Bilgisayarım > Özellikler > Gelişmiş Sistem Ayarları > Gelişmiş" penceresine geliyoruz ve "Ortam Değişkenleri" butonuna basıyoruz. "Sistem Değişkenleri" bölümünde "path" değişkenini seçip "düzenle" butonuna basıyoruz. Açılan pencerede "yeni" butonuna basıp kopyalamış olduğumuz pathı buraya yapıştırıyoruz ve "tamam" butonu ile onaylıyoruz (Windows sürümü farklı ise gidişat farklılık gösterebilir ancak yolu budur).

    Eğer bu yöntem çalışmazsa OpenCV kodlarının bulunduğu dosyanın hemen yanına "C:\OpenCV\build\python" adresinde bulunan "cv2" isimli klasör kopyalanarak yapıştırılır ve OpenCV çalışır.