# Virtual-Eye
B M E

App ana programda çalışıp resim analizi yapacak olan sınıfı barındıran dosyadır. Bu sınıf kullanılarak gerekli işlemler gerçekleştirilecektir. Sadece kaynak kodu ve çalışma şeklini barındırmaktadır. İmplementasyon için bu dosya değil, sadece içerisindeki kodlar kullanılacaktır.

### Github nasıl kullanılır?

- Github dosyalarının bulunduğu konuma repo denir. Bu projenin reposu budur: github.com/emrahtema/Virtual-Eyes
- Bu repo ile ortak çalışma yapmak istiyorsanız repo üzerindeyken sağ yukarıda bulunan 'Fork' butonuna basmalısınız. Bu işlem bu reponun aynısını kendi Github hesabınıza kopyalayacaktır.
- Bu repo master reposudur. Sizin hesaplarınıza kopyalanan repo ise masterin kopyasıdır. Master'de yapılan değişiklikler sizin repolarınızda görünmez. Sizin yaptığınız değişiklikler de bu repoya işlenmez.
- Repoya katkıda bulunmak istediğiniz zaman, kod güncellemesi, dosya eklemek vb gibi işlemlerde her zaman ilk olarak master reposunu bilgisayarınıza indirin ve o dosyalar üzerinde çalışın.
- Bir dosyada değişiklik yaptığınız zaman bu dosyayı kendi kişisel reponuza yüklemelisiniz. Bu yükleme esnasında bir commit girmeniz istenecektir. Commit başlığına yaptığınız değişikliği özetleyen bir cümle yazmalısınız ve sonrasında reponuzun üzerinde bulunan "Pull requests" butonuna tıklamalısınız. Burada kendi komitiniz görülecektir. Commitinizin göründüğü Pull Request'e tıklayıp master repoya gitmesi için onaylamalısınız. Bu sayede kendi reponuzda yaptığınız dosya değişikliği, master repoya gidecektir. Master reponun sahibi onayladığında değişiklik asıl proje dosyalarına kaydedilecektir. Böylece bu repo üzerinde çalışan kişilerin yaptıkları değişiklikleri tek bir repoda toplayacak ve takım çalışması yapabileceklerdir.
- Kısaca her çalışma yaptığımız zaman master repoyu indirip onun üzerinde çalışıp değişiklikleri kendi reponuza yükleyip master'a bağlanması için istek atıyorsunuz ve mastere bağlandığında artık master repoyu bilgisayarına indirip çalışma yapan herkes sizin kodlarınızı da görebilecek, herkes aynı proje üzerinde kod geliştirmesi yapabilecek.

### Kod Yazarken Dikkat Edilmesi Gerekenler
Kod yazarken Python Pep8 kurallarına uymak zorunludur. Bu sadece Python dilinde değil çoğu programlama dilinde uyulan kurallar bütünüdür, sadece dilden dile, o dile özel yapılarda değişkenlik gösterebilmektedir. Pep8 kurallarına uyulmadan yazılan kodlar master repoya bağlanma konusunda onay almayacaklardır. Pep8 kural hatası olduğu belirlenen kodları içeren komit iptal edilir ve tekrardan yazarı tarafından güncellenip yeni commit oluşturulur. Basit bir kaynakça: http://ahmetcankepenek.blogspot.com/2013/04/pep-8-python-kodu-icin-stil-rehberi.html

### Gerekli Yüklemeler
Bu repo üzerinde düzgün çalışabilmeniz için gerekli olan tüm yüklemeler requirements.md dosyası içerisinde bulunmaktadır. Proje üzerinde çalışmaya başlamadan önce bu yüklemelerin gerçekleşmiş olduğundan emin olmalısınız.

### Güncellenmesi Gereken Şeyler
- Sorun 1: Application.py dosyasında "take_a_photo()" fonksiyonu resim çekmek için kullanılıyor. Resim çekildiği zaman default renk bilgisi siyah beyaz olduğu için resim renklendirme işlemini "cv.merge([r, g, b])" fonksiyonuyla gerçekleştiriyoruz ancak bu fonksiyon resmi ağırlıklı olarak mavi tonda gösteriyor. Bunun düzeltilip resmin orjinal tonlarında olması sağlanmalıdır. OpenCV'de çekilen resmin renklendirilmesiyle ilgili konular araştırılabilir.

- Sorun 2: Application.py dosyasında "take_a_photo()" fonksiyonu resim çekmek için kullanılıyor. Çektiği resmi bir dosya olarak bir dizine kaydediyor ve resim çekilebişmişse True, çekilememişse False değerini döndürüyor. Resmi çektiğinde resmi bir dizine kaydetmek yerine direkt resim objesi olarak döndürecek şekilde güncellenmeli. Yani resim çekilmişse resim objesi, resim çekilememişse None değerini döndürecek şekle getirilmeli. OpenCV'nin kullandığı resim objesinin Google'nin kullandığı "PIL" kütüphanesinin resim objesine dönüştürme işlemleri araştırılabilir.

- Sorun 3: Application.py dosyasında "make_text_analysis()" fonksiyonu resimdeki yazıların çıkarımının yapılabilmesi için kullanılır. Resimden çıkarımı yapılan yazılar bir listeye(list_of_findings) eklenir. Ancak listeye eklenen yazılar sorunludur. Yazılarda gereksiz noktalama işaretleri bulunabilmektedir ve aynı yazılar birden fazla kere tekrar etmektedir. Bu sorunun düzeltilmesi gerekiyor. Yazıların temizlenip, düzeltilip düzgünce seslendirilebilmesi sağlanmalıdır.

- Sorun 4: Application.py dosyasında "display_the_speech()" fonksiyonu seslendirilip .mp3 dosyası olarak kaydedilen bulguların default media oynatıcısında çalınmasını sağlar. Yani bir nevi .mp3 dosyasını bilgisayarda dinlemek gibi düşünülebilir. Bunu daha etkili bir yoldan halletmek gerekiyor. Her ses çalınacağı zaman sistemin default mp3 playerinin çalışması yerine direkt Python ses çalma-yürütme kütüphaneleriyle yapılması daha iyi olacaktır.