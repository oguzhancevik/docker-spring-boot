### Docker Nedir?
İşletim sistemindeki kaynakları verimli bir şekilde paylaştırarak container oluşturmaya imkan veren bir programdır.

### Container Nedir?
<p>
Bilgisayarlarda yer alan işlemci ve ram işletim sistemi tarafından her zaman tam olarak kullanılmaz.
Kaynaklar tam olarak kullanılmadığından bilgisayar kaynaklarını bölünerek farklı programlar tarafından verimli bir şekilde kullanılması sağlanır.
Bu amaçla VMWare, Virtualbox gibi çeşitli sanallaştırma yazılımları kullanılmaktadır.
Sanallaştırma yazılımları kaynakların paylaşımını yaparken yeniden bir işletim sistemi kurulumuna ihtiyaç duymaktadır.
Yeniden bir işletim sistemi kurulumu beraberinde uygulamaların ihtiyaç duymadığı kaynakların gereksiz yere kullanılması neden olur.
Örneğin; Kullanıcı bilgilerini saklamak için kullanılan bir uygulama ekran kaynaklarını kullanmayabilir.
Ancak işletim sistemi programları ekran kartına ihtiyaç duyduğundan uygulama için gerekli olmayan ekran kartı kaynakları da kullanılmış olur.
Sanallaştırma sonucu ortaya çıkan işletim sisteminin çalışması için yeniden başlatılması ve yüklenme işleminin gerçekleşmesi gerekir.
Konteyner yapısında ise uygulamanın ihtiyaç duyduğu kaynaklar yazılımsal olarak paylaşılarak sanallaştırma sonucu ortaya çıkan gereksiz kaynak kullanımının önüne geçilmiş olur.
Konteyner yapısında mevcut işletim sistemi kaynakları bölündüğünden uygulamaların hızlıca çalışması sağlanır.
Ayrıca konteyner yapısında yer alan imaj ile uygulama için gerekli olan çalışma ortamı hazırlanarak uygulamanın taşınabilir olması sağlanır.
</p>

### Bu uygulamayı dockerize etmek için aşağıdaki komutlar çalıştırılmalıdır
- ```docker build -f Dockerfile -t docker-spring-boot .```
- ```docker run -p 8085:8085 docker-spring-boot```

### Bazı Docker komutları
- ```docker version``` 
Docker versiyonunu öğrenmek için version komutu kullanılır.

- ```docker info``` 
Sistemde yer alan imaj, konteyner, çalışan konteyner sayısı ile detaylı bilgi için info komutu kullanılır.

- ```docker run hello-world``` 
İmaj çalıştırmak için run komutu kullanılır.

- ```docker search hello-world``` 
İmaj aramak için search komutu kullanılır.

- ```docker pull hello-world``` 
İmaj indirmek için pull komutu kullanılır.

- ```docker images``` 
İmajları listelemek için images komutu kullanılır.

- ```docker rmi hello-world``` 
İmaj silmek için rmi komutu kullanılır.

- ```docker history hello-world``` 
İmaj geçmişi için history komutu kullanılır.

- ```docker ps``` 
Çalışan konteynerlerı listelemek için ps komutu kullanılır.

- ```docker ps -a``` 
Tüm konteynerlerı listelemek için ps komutu kullanılır.

- ```docker stop konteyner-id``` 
Çalışan konteynerı durdurmak için stop komutu kullanılır.

- ```docker kill konteyner-id``` 
Çalışan konteynerı zorla durdurmak için kill komutu kullanılır.

- ```docker start konteyner-id``` 
Durdurulan konteynerı çalıştırmak için start komutu kullanılır.

- ```docker inspect konteyner-id``` 
Konteyner hakkında bilgi almak için inspect komutu kullanılır.

- ```docker stats konteyner-id``` 
Çalışan konteynera ait kaynak kullanımı bilgisi için komutu kullanılır.

- ```docker logs konteyner-id```
Konteynera ait günlük bilgisi için logs komutu kullanılır.

- ```docker rm konteyner-id``` 
Konteyner silmek için rm komutu kullanılır.

- ```docker run --rm hello-world``` 
Konteyner çalışmasını bitirdikten sonra otomatik olarak silinmesi için -rm komutu kullanılır.

- ```docker rm $(docker ps -aq)``` ve ```docker sytem prune```
Tüm konteynerları silmek için bu komutlar kullanılır.

### Dockerfile
Özel bir imaj oluşturmak için Dockerfile kullanılır.
- ```FROM``` Kullanılacak imajı ifade eder.
- ```LABEL``` İmaj etiketini ifade eder.
- ```RUN``` Çalıştırılacak komutları ifade eder. (İmaj için gerekli yüklemeler için kullanılır.)
- ```CMD``` Çalıştırılacak komutları ifade eder. (İmaj için gerekli yüklemeler yapıldıktan sonra çalıştırılacak komutlar için kullanılır.)
- ```ENTRYPOINT``` Çalıştırılacak komutların yolunu ifade eder.
- ```COPY``` İmaja kopyalanacak dosyaları ifade eder.
- ```WORKDIR``` Çalışma dizinini ifade eder.
- ```ENV``` Ortam değişkenlerini ifade eder.
- ```EXPOSE``` İmaj port numarasını ifade eder.
- ```VOLUME``` İmaja paylaşılacak/geçirilecek dosyaları ifade eder.

### Kaynaklar
- https://www.yusufsezer.com.tr/docker/
- https://www.youtube.com/watch?v=FlSup_eelYE
