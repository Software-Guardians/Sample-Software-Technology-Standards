# Back-End Yazılım Standartları E-Kitabı
<p>Bu e-kitap, back-end yazılım geliştirmede modern standartları ve en iyi uygulamaları derinlemesine inceleyen kapsamlı bir rehberdir. Amacımız, Dependency Injection'dan Domain-Driven Design'a, mikroservis mimarisinden CI/CD süreçlerine kadar geniş bir yelpazede, sağlam, ölçeklenebilir ve sürdürülebilir back-end sistemleri oluşturmak için gereken temel kavramları ve teknolojileri sunmaktır. Bu rehber, ister kariyerinin başındaki bir geliştirici olun, ister deneyimli bir mühendis, back-end dünyasındaki yetkinliklerinizi bir üst seviyeye taşımanıza yardımcı olacak.</p>

## İçindekiler
1. Dependency Injection & IoC: Bağımlılık enjeksiyonu ve kontrolün tersine çevrilmesi prensipleri.

2. Concurrency & Parallelism: Eş zamanlılık ve paralellik kavramları arasındaki farklar ve kullanım alanları.

3. Threading vs Async Programming: Threading ve asenkron programlama yaklaşımlarının karşılaştırması.

4. Event-Driven Architecture: Olay tabanlı mimarinin temelleri ve avantajları.

5. Observer & Pub/Sub Patterns: Observer ve Yayıncı/Abone (Pub/Sub) tasarım kalıplarının kullanımı.

6. Design Patterns (OOP odaklı): Sık kullanılan nesne yönelimli tasarım kalıpları.

     Singleton, Factory, Strategy, vb.

7. Clean Architecture & SOLID Principles: Temiz mimari ve SOLID prensiplerinin detaylı incelenmesi.

8. Domain-Driven Design (DDD): Etki alanına dayalı tasarımın temel prensipleri ve uygulama yöntemleri.

9. Functional Programming Concepts: Fonksiyonel programlamanın back-end geliştirmeye katkıları.

10. Reactive Programming (RxJS, Reactor, vb.): Reaktif programlama paradigmaları ve popüler kütüphaneler.

11. Microservices & API Design: Mikroservis mimarisi ve etkili API tasarımı.

12. REST vs GraphQL: REST ve GraphQL API'lerinin karşılaştırması ve seçim kriterleri.

13. Message Brokers (Kafka, RabbitMQ): Mesaj aracıları (Message Brokers) ve dağıtık sistemlerdeki rolleri.

14. Caching Strategies (Redis, CDN, vb.): Verimlilik artırıcı önbellekleme stratejileri.

15. Authentication & Authorization Concepts: Kimlik doğrulama ve yetkilendirme süreçlerinin anlaşılması.

16. Containerization & Docker Concepts: Konteynerleştirme ve Docker'ın temel kavramları.

17. CI/CD & DevOps Pipelines: Sürekli Entegrasyon ve Sürekli Dağıtım (CI/CD) süreçleri.

18. Logging & Monitoring: Etkili loglama ve sistem izleme (monitoring) uygulamaları.

19. Testing Types (Unit, Integration, E2E): Birim, entegrasyon ve uçtan uca test türleri.

20. Memory Management & Garbage Collection: Bellek yönetimi ve çöp toplama (Garbage Collection) süreçleri.

## 1.Dependency Injection & IoC 
<p>   Dependency Injection (Bağımlılık Enjeksiyonu), nesnelerin kendi bağımlılıklarını (yani ihtiyaç duydukları diğer nesneleri) kendileri oluşturmak yerine, bunları dış bir kaynaktan aldığı bir tasarım desenidir. Bu yaklaşım, gevşek bağlılığı (loose coupling), daha kolay test edilebilirliği ve daha iyi kod sürdürülebilirliğini teşvik eder. Spring çatısı altında Bağımlılık Enjeksiyonu, genellikle Constructor Injection (Kurucu Metot Enjeksiyonu) veya Setter Injection (Ayarlayıcı Metot Enjeksiyonu) aracılığıyla gerçekleştirilir.</p>

### Need for Dependency Injection
<p>    Bir A sınıfının, işlemlerini gerçekleştirmek için bir B sınıfına ait bir nesneye ihtiyacı olduğunu varsayalım. Bu, A sınıfının B sınıfına bağımlı olduğu anlamına gelir.</p>
         <p>   Böyle bir bağımlılık kabul edilebilir gibi görünse de, gerçek dünya uygulamalarında sıkı bağlılığa, bakımı zorlaştırmaya, test edilebilirliği azaltmaya veya potansiyel sistem arızalarına yol açabilir. Bu nedenle, doğrudan bağımlılıklardan kaçınılmalıdır.</p>
     <p>    Spring IoC (Kontrolün Tersine Çevrilmesi), bu tür bağımlılık sorunlarını Bağımlılık Enjeksiyonu (DI) kullanarak çözer. Bağımlılık Enjeksiyonu, kodu daha kolay test edilebilir ve yeniden kullanılabilir hale getirir.</p>
       <p>  Sınıflar arasındaki gevşek bağlılık, ortak işlevsellik için arayüzler tanımlayarak veya enjektörün (Spring container) uygun implementasyonu sağlamasına izin verilerek elde edilir. Nesneleri örneklendirme görevi, geliştiricinin belirttiği konfigürasyonlara göre container tarafından yapılır.</p>

