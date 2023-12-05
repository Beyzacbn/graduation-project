# graduation-project
NOT

graduation-project repository içerisindeki MVVMDemoProject dizini -> Android tarafı kodları, ogrenciyasami-api dizini -> Laravel API tarafı kodları temsil eder.

# Proje Tanımı
Projemiz iki ana başlık çerçevesinde geliştirilmiştir.

Birinci bölümde Çanakkale Onsekiz Mart Üniversitesi’nde düzenlenen topluluk etkinlikleri üzerine,
İkinci bölümde ise öğrencilerin hızlı ulaşabilmesi için ev,eşya ilanlarının bir araya getirilmesi üzerine yoğunlaşılmıştır.

Topluluk Etkinlikleri Kısmı:
Öğrenciler, düzenlenen tüm etkinlikleri listeleyip etkinlik hakkındaki bilgilere kolaylıkla ulaşabilecek, gerektiğinde bilgilerde güncelleme yapabilecektir. Aynı zamanda kendi kriterleri doğrultusunda etkinlikleri filtreleyebilecekler. Topluluk etkinliklerine ek olarak öğrencilerin ders ilanı oluşturabileceği bir yapı sunulması da hedeflenmiştir.

Öğrenci Yaşamı Kısmı:
Öğrenciler Çanakkale’deki kiralık evleri ve diğer öğrenciler tarafından satılmak istenen eşyaları görüntüleyebilecekleri gerekli durumlarda ilan güncelleme, kaldırma yapabilecekleri bir yapı sunulması hedeflenmiştir. Aynı zamanda uygulamayı kullanacak öğrenciler ev arkadaşı da arayabilirler. Öğrenciler yine istekleri doğrultusunda gerekli filtreleme işlemleri yapabilirler.

# Sistemin Hedefleri
1-Öğrencilerin düzenlenen topluluk etkinliklerinden haberdar olmasını sağlamak.

2-Etkinliklerdeki etkinliğe katılıp katılmama durumuna göre kontenjan kontrolünü sağlamak.

3-Öğrencilerin katılacağı etkinlikleri takvim üzerinden takibini ve bildirim almasını sağlamak.

4-Öğrencilerin kolay ve hızlı şekilde ev ve eşya bulmasına imkan sunmak.

5-Öğrencilerin kendi aralarında iletişim kurmalarına fırsat tanımak.

6-Kurulan iletişimler sonucunda en ekonomik şartlarda eşya satın almak ve ev kiralayabilmek.

7-Birebir kurulan iletişimler sayesinde istenilen kriterlere uygun ev arkadaşı bulmak.

# UI Tasarımları
Uygulama geliştirmeye başlamadan önce kullanacağımız bileşenleri kolaylıkla belirleyebilmek ve uygulama gereksinimlerini anlayabilmek için taslak niteliğinde UI tasarımlarını oluşturduk.
Adobe XD üzerinden arayüzleri hazırladıktan sonra Prototype yardımıyla senaryo işleyişini takip ettik.

![image](https://github.com/Beyzacbn/graduation-project/assets/33182994/6af1b8cd-7d9b-4491-9caf-04ffd91a206d)
![image](https://github.com/Beyzacbn/graduation-project/assets/33182994/32c9d7b3-e070-415d-92ea-e834706bcaa5)
![image](https://github.com/Beyzacbn/graduation-project/assets/33182994/96def6d3-5dbc-4864-a8dd-05366cfd00a8)

# Kullanılan Teknolojiler
 Mobil Uygulama Platformu
 
   Hedef kullanıcı kitlesini ve uygulama kapsamını göz önünde bulundurduğumuzda mobil cihazlar üzerinden daha kolay ve verimli şekilde gereksinimlerimizin karşılanabileceğini düşündük. Bu yüzden uygulama ortamının mobil tarafta olmasının daha kullanışlı olacağına karar verdik. Geliştirme için Android Studio ortamını belirledik. Daha az kod satırıyla daha güvenli kod yazmaya olanak sağladığı için ve diğer avantajları da dikkate alındığında Kotlin programlama diliyle de uygulamamızı kodlamaya karar verdik.

  Veritabanı Tasarımı
  
   Uygulama gereksinimlerini incelediğimizde veritabanında oluşturacağımız birçok tablonun birbiriyle ilişkili olması gerektiğini fark ettik. Bundan dolayı SQLite, MySQL, Microsoft SQL Server, Postgre SQL gibi ilişkisel veritabanları üzerine yoğunlaştık. Bu araştırmalar sonucunda MySQL veritabanına karar verdik.
Veritabanı tasarımımızı öncelikle MySQL Workbench üzerinde yaparak tablolar arasındaki ilişkileri daha net kavradık. Tüm modüllerin ER şemalarını hazırladıktan sonra PhpStorm üzerinden migration işlemleriyle veritabanımızı geliştirme ortamımıza aktarmış olduk.
 
![image](https://github.com/Beyzacbn/graduation-project/assets/33182994/ad1f5be6-ccc6-4a07-aa78-079f24eb4285)

  Rest API

  Uygulamamızda verilerin uzak sunucuda tutulması ve internet üzerinden ulaşılması gereksinimi vardı. 
  Ayrıca veritabanı işlemlerinin tek merkezde yapılıp platform ve dil bağımsızlığının sağlanması gerekliydi.
  
  Restful standartı, daha eski olan Soap servislerine bir çözüm olarak geliştirildiğinden bizim de tercihimiz bu yönde oldu. 
  
  Hem hızlı uygulama geliştirmeyi mümkün kılan bir kod altyapısını kullanıcılarına sunarak, daha sade bir ortamda kullanıcılara kolaylık sağladığı için hem de MVC yapısında API uygulama geliştirmeye imkan sunduğu için Laravel framework’üne karar verdik. 
  IDE olarak PHP Storm kullanmayı tercih ettik.
  
  Veri tabanıyla etkili şekilde çalışmak için laravelin sunduğu elequent orm yapısını kullandık.

  Postman ile isteklerimizi test ettik. Kodlarımızı daha temiz ve değişime açık şekilde yazmak için projemizi bir mimari üzerine inşa ettik. Ayrıca çeşitli tasarım desenlerinden yararlandık, Repository Pattern bunlardan biriydi.

  ![image](https://github.com/Beyzacbn/graduation-project/assets/33182994/a48d247b-b0aa-4178-9412-f797c3b2cf20)

# Mobil Uygulama Geliştirme

  Retrofit
 
Veri çekme ve network işlemleri için API’lara kolaylıkla erişebilme, test edilebilir ve kolay kullanım özelliklerinden dolayı açık kaynak kodlu REST istemcisi olan Retrofit'e karar verdik.

  MVVM
  
Kullanıcı arabirimiyle ilişkili verileri yaşam döngüsü bilinçli şekilde tutmayı ve yönetmeyi sağladığı bu sayede de yapılandırma değişikliklerini koruduğu için MVVM mimarisini kullanmaya karar verdik. Use Case'ler ile veri akışı mantığını uygulayarak bu akışın view modellerde yeniden kullanılabilir olmasını sağladık.

![image](https://github.com/Beyzacbn/graduation-project/assets/33182994/30818cf2-adff-4acd-a5b5-d1a1d123d648)

  RxJava
  
Arayüz işlemleri ile istek sonuçlarının birbirini bloklamaması ,ana ve arka plan iş parçacığını birbirinden ayrılabilmesi için eş zamansız çağrılar yapmamız gerekliydi. Bundan dolayı isteklerimizi işleyebilmek için aşağıdaki avantajları da göz önünde bulundurarak RxJava kullanmaya karar verdik.

* Operatörler ve veri akış manipülasyonlarının kolaylıkla yapılabilmesi

* Observable veri tipleri sayesinde istek yapısına uygun veriler işlenebilmesi

* Zincir yapısı sayesinde iç içe ağ aramasından kurtarması

* Kodun çalıştırılacağı zamanlayıcıyı değiştirme olanağı sağlaması

* Hata işlemeyi kolaylaştırması

Data Binding

Arayüzümüz kullanıcı odaklı olduğu için daha hızlı ve düzenli kod yazmamızı sağlayacak Data Binding kütüphanesini kullanarak veri modelini XML dosyasına bağladık.

![image](https://github.com/Beyzacbn/graduation-project/assets/33182994/408e5113-244c-4e8a-a22e-168332e3dd60)

Navigation

Uygulamamızın baştan sona bir bütün halinde gezinme akışını sağlamak için Jetpack mimari bileşenlerde bulunan Navigation componenti kullanmaya karar verdik. Bu sayede fragmentler arası geçişi kolaylıkla ele alıp geri akışları etkili şekilde tamamladık.

![image](https://github.com/Beyzacbn/graduation-project/assets/33182994/69cb4a05-4a15-4f86-87e2-745968b16fa0)







 


