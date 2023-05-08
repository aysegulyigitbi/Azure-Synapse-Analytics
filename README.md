# Azure Synapse Studio: Serverless SQL Pools ile CSV Dosyaları Sorgulama

## SQL Server’a bağlanma

Serverless Sql Endpoint’i kullanarak SQL’e bağlanacağız.
Arkada sanal bir sunucuya bağlandı ve onun içerisinde de sanal bir veri tabanı oluşturup çalıştırabileceğiz.

![image](https://user-images.githubusercontent.com/127193220/236759035-23a21eea-0034-4287-96dc-1618d1f1e355.png)

Arkada sanal bir sunucuya bağlandı ve onun içerisinde de sanal bir veri tabanı oluşturup çalıştırabileceğiz.

![image](https://user-images.githubusercontent.com/127193220/236759093-56873662-b3c7-44ba-b506-70e42b35cf5b.png)

## Database Oluşturma

![image](https://user-images.githubusercontent.com/127193220/236759178-3c77c640-e1af-4d90-9850-31f6f33bbe99.png)

### System Table ve External Table

Veritabanımızı oluşturup içine baktığımızda burada System ve External tablolar ile karşılaşıyoruz.

![image](https://user-images.githubusercontent.com/127193220/236759325-d1d64c5a-d843-4434-a92e-555c5f7b49ba.png)

Burada fiziksel bir tablo oluşturamıyoruz. Yani Create Table desteği vermiyor.

![image](https://user-images.githubusercontent.com/127193220/236759425-414f8a7a-d699-46b4-9347-dfb0d4147ee6.png)

Normal bir tablo oluşturamadığımız için insert vb. işlemleri yapamıyoruz.
Fakat External Table oluşturabiliriz. Dışarıdaki bir diskteki format sorgulamamızı sağlıyor.
Yani sadece viewler ve external table oluşturabilirken fakat fiziksel olarak bir tablo oluştamıyoruz.

## Synapse Studio

![image](https://user-images.githubusercontent.com/127193220/236759565-889b05a2-dab5-4539-8b50-202f8595c84a.png)

## Open Synapse Studio

### Azure Synapse serverless SQL pools Kullanarak Csv Sorgulama

CSV dosyaları, birçok işletmede yaygın olarak kullanılan bir dosya biçimidir ve sunucusuz SQL havuzunu kullanarak tek bir CSV dosyasını sorgulayabilirsiniz. 

CSV dosyalarının farklı biçimleri olabilir:
•	Başlık satırı olan ve olmayan
•	Virgül ve sekmeyle ayrılmış değerler
•	Windows ve Unix stili satır sonları
•	Alıntılanmayan ve alıntılanmayan değerler ve kaçan karakterler

OPENROWSET işlevi, dosyanızın URL'sini sağlayarak CSV dosyasının içeriğini okumanızı sağlar.

Amaç: Azure Synapse ortamına csv dosyalarını yükleyip, sorgulamak.

Azure Synapse ara yüzünde container altında klasör oluşturuyoruz.

![image](https://user-images.githubusercontent.com/127193220/236759853-b05644d4-b068-44b3-8ff3-98d23e5b228a.png)

İstersek web arayüzünden upload işlemine tabi tutarak ya da explorer arayüzünden oluşturduğumuz klasörün içine dosyalarımızı atama işlemini yapabiliriz.

![image](https://user-images.githubusercontent.com/127193220/236759896-95c5a764-0c61-47e8-a201-87c6644b9b44.png)

Klasörün içine girip mevcutta bulunan dosyalarımızı sürükle bırak metoduyla ekliyoruz.

![image](https://user-images.githubusercontent.com/127193220/236759977-23f5080c-dafd-44f7-987b-5ba0a85ddcef.png)

Explorer üzerinden yüklediğimiz csv dosyasını web arayüz üzerinden de eş zamanlı yüklendiğini görebiliriz.

![image](https://user-images.githubusercontent.com/127193220/236760048-63cef073-b355-444e-92b2-496037b4c789.png)

Yüklenen csv dosyasını sorgularken 2 yöntem kullanabiliriz.
1.	Web Portalında sorgulama
2.	SQL Server üzerinden sorgulama

Klasöre sağ tılayıp New SQL Scripte tıklayarak sorgulayabiliriz.

![image](https://user-images.githubusercontent.com/127193220/236760191-f96c65be-c55f-4ae7-8eb3-d7efdd50ec68.png)

### Select TOP 100 rows

Dosyamızın yolunu, formatını ve hangi versiyonda parse edileceğiyle ilgili bilgilere erişebiiliyoruz.

![image](https://user-images.githubusercontent.com/127193220/236760303-f6b3ac34-4504-422c-96c4-44b5324796af.png)

### RUN

Diskteki csv dosyasını okumak için sol yukardaki run butonuna tıklıyoruz.

![image](https://user-images.githubusercontent.com/127193220/236760398-59e779a1-16a5-4ef1-8833-2dae1848e481.png)

### Klasöre yeni dosyalar ekleme

Explorer ara yüzünde klasörümüze var olan dosyaları sürükle bırak metoduyla ekliyoruz.

![image](https://user-images.githubusercontent.com/127193220/236760520-7a9e6ec5-6fc7-470e-b747-5f6f45682182.png)

Web arayüzünde bütün dosyalarımızı sorgulamak için Sales1 alanını * ile değiştirerek hepsini okumasını belirtiyoruz.

![image](https://user-images.githubusercontent.com/127193220/236760620-d4d6c94d-d45c-4b56-a0e0-7cd538062802.png)

Çıktı sonuçlarında da görebileceğimiz üzere kolon isimlerini ve typlerını istediğimiz gibi göremedik bu yüzden With kullanarak scriptimizi sorgulayabiliriz.

![image](https://user-images.githubusercontent.com/127193220/236760696-89341a60-047a-414c-9e24-223a43600500.png)

## 2.Yöntem Sql Server ile sorgulama

İlk olarak synapse üzerinden herhangi bir yere ulaşmam için Credential tanımlamam gerekiyor.
![image](https://user-images.githubusercontent.com/127193220/236760903-97034342-ab55-4e47-a268-caf89f389312.png)

1) Public DATA SOURCE belirtme
--Public bir Container açalım. portalde Soldaki Container bölümümden public açabilirsin.
Public access seviyesindeki seçimimizde hem blobların hem de containerların public erişim yetkisi veriyoruz

![image](https://user-images.githubusercontent.com/127193220/236761025-9edc3ede-4fc6-4a77-b63b-6a9d3035203b.png)

## Containerın URL’ini alma

https://denemesynapselake.blob.core.windows.net/publicdenemecontainer

![image](https://user-images.githubusercontent.com/127193220/236761106-68096eb4-0703-4b1d-95fb-0b97d771390c.png)

SQL Server’da location belirttiğimiz yere URL’yi kopyalıp, yapıştırıyoruz.

![image](https://user-images.githubusercontent.com/127193220/236761179-c68fcc62-9715-484b-ba8b-b670bf492f3d.png)

Oluşturduğumuz Containerın içine csv dosyası atıyoruz.

![image](https://user-images.githubusercontent.com/127193220/236761266-f1343a00-baad-48a1-bd96-402ffe7ca4d7.png)

Ve bu attığımız dosyayı okumasını belirtiyoruz.

![image](https://user-images.githubusercontent.com/127193220/236761336-49e58e1b-5bf5-45cb-8d6d-13d89c4bc17a.png)

## Private DATA SOURCE belirtme

Credential belirtmek lazım.
İlk önce master key belirtiyoruz bu sayede şifrelenmesi gereken nesneler şifreleniyor.

![image](https://user-images.githubusercontent.com/127193220/236761386-8e821244-61f9-44e1-9ccc-58096049bb96.png)

Ardından credential tanımlıyoruz. Manage Identity diyerek synapse’in yetkilerini kullanmasını söylüyoruz.

![image](https://user-images.githubusercontent.com/127193220/236761452-dca97323-542d-4bf9-857f-0a2ed1015c68.png)

Oluşturduğumuz Credential’I data source oluştururken kullanacağız.

![image](https://user-images.githubusercontent.com/127193220/236761516-26fd835a-2699-42f4-b117-3016318134fb.png)

Şu an diskin içindeki private bir veriyi okuyabiliriz.

![image](https://user-images.githubusercontent.com/127193220/236761805-edf6bf4c-4948-4015-8cfb-73f6ecbe14b3.png)
