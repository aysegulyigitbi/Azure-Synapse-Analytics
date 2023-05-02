# Azure Synapse Analytics: Veri Sanallaştırma ve PolyBase

Herkese merhabalar, bu yazıda Azure Synapse Analytics'in Veri Sanallaştırma ve PolyBase özelliklerine dair bilgi vermek istiyorum. Veri Sanallaştırma, verilerin fiziksel konumundan bağımsız olarak kullanıcılara sunulmasını sağlayan bir işlem. PolyBase ise farklı veri kaynaklarındaki verileri SQL Server üzerinden sorgulamak için kullanılan bir teknolojidir. Ayrıca, makalede Azure Synapse Analytics oluşturma ve SQL veritabanı oluşturma adımlarını da işleyeceğiz. Umarım faydalı olur!

![image](https://user-images.githubusercontent.com/127193220/235667584-dba3110a-30bb-4e34-a824-e8811eaaf4d7.png)

Veri Sanallaştırma Nedir?
Veri sanallaştırma, verilerin fiziksel konumundan bağımsız olarak, son kullanıcıya tablo halinde sunulabilmesini sağlayan bir işlemdir. Bu sayede verilerin taşınması ya da formatı hakkında endişe etmeden, kullanıcılara anında erişim sağlanabilir.
Verilerin farklı kaynaklardan ve farklı formatlarda olması durumunda bile, polybaseangine'de create external table komutları kullanılarak tüm veriler SQL içerisinde birleştirilebilir.
Büyük verinin kullanıldığı alanlarda ETL yerine ELT daha avantajlıdır. ELT, verilerin önce işlenip, ardından yüklenmesi anlamına gelir. Bu sayede daha hızlı bir veri işleme süreci elde edilir. 
Azure Synapse Analytics SQL Pool, ETL'den ELT'ye geçişi mümkün kılarak modern veri ambarlarına entegre olabilme özelliği sunar.

PolyBase nedir?
PolyBase, farklı veri kaynaklarındaki verileri SQL Server üzerinden sorgulamak için kullanılan bir teknolojidir. Bu sayede farklı formatlarda ve farklı kaynaklarda bulunan verilerin tek bir noktada birleştirilmesi mümkün olur. PolyBase kullanarak verileri tarayabilir, SQL Server içerisinde dışarıya veri aktarabilir ve verileri birleştirebilirsiniz. Bu teknoloji, LinkedIn gibi büyük ölçekli veri hizmetleri tarafından da kullanılır.

Not: Azure Synapse Analytics şu an DataLake Storagelara ve Azure Storagelara bağlanabiliyor ve Csv, json gibi formattaki verileri işleyebiliyor. Ek olarak, Azure Synapse Analytics datalakeler ile çalışmaktadır.

![image](https://user-images.githubusercontent.com/127193220/235667970-2128b59e-75fc-4233-9041-bb8f7603f139.png)

## Azure Synapse Analytics Oluşturma

![image](https://user-images.githubusercontent.com/127193220/235668323-44a85bb0-f5aa-47af-9a22-dc7510f7ead8.png)

Security

Azure Synapse Analytics oluşturmak için öncelikle güvenlik ayarlarını yapmanız gerekiyor. Kullanıcı adı ve şifre belirleyerek güvenlik önlemlerini alabilirsiniz.

![image](https://user-images.githubusercontent.com/127193220/235668522-6bb832b7-a0a2-474b-962c-2bd94208a106.png)

Review and Create

Ardından "Review and Create" seçeneği ile Azure Synapse Analytics'i oluşturabilirsiniz.

![image](https://user-images.githubusercontent.com/127193220/235668932-d4f18e9d-7cc0-4a4b-8f2b-a8fdad23c390.png)

Deployment

![image](https://user-images.githubusercontent.com/127193220/235669034-17e61795-012e-4079-9882-e7a431277ac5.png)

Go to resource group

Deployment işlemi tamamlandıktan sonra "Go to resource group" butonuna tıklayarak oluşturduğunuz Azure Synapse Analytics kaynağına ulaşabilirsiniz.

![image](https://user-images.githubusercontent.com/127193220/235669164-e3c128e8-7a4c-42c5-a7f2-ce1fc5f59d42.png)

Workspace

Workspace'a erişmek için Serveless SQL Endpoint'ini kullanabilirsiniz.

![image](https://user-images.githubusercontent.com/127193220/235669280-3002c5d4-53b9-49bf-b87e-eefdf401e4e6.png)

SQL'e Bağlanma

![image](https://user-images.githubusercontent.com/127193220/235669375-00a8031a-90f6-4379-a0bf-e472583296d9.png)

Synapse Studio

İşlemlerimizi SQL üzerinden yapabileceğimiz gibi Synapse Studio üzerinden de yapabiliriz.

![image](https://user-images.githubusercontent.com/127193220/235669507-0699382a-15c1-49b9-a06e-d09d2d4db33d.png)

SQL Veritabanı Oluşturma

Data bölümünden + işaretine tıklayarak SQL database'i seçiyoruz.

![image](https://user-images.githubusercontent.com/127193220/235669617-e87dc04a-c876-4be3-9368-7c0bb49430ae.png)

Burada Dedicated bir pool mu yoksa serverless mı oluşturacağımızla ilgili seçeneğimiz ve Database'in adını belirleyeceğimiz alanlar bulunuyor.

![image](https://user-images.githubusercontent.com/127193220/235669708-2af5ebf6-1c52-46f8-90a3-22c5d805dbf4.png)

Database oluşturuldu.

![image](https://user-images.githubusercontent.com/127193220/235669781-5b80c129-3f10-4185-a76d-31eeb26512c9.png)

Linked sekmesinde ise oluşturduğumuz container görebiliyoruz.

![image](https://user-images.githubusercontent.com/127193220/235669856-a17a1d59-2353-497c-83c0-64c5b0e65dab.png)

Verileri yüklemek için öncelikle bir container oluşturmanız gerekiyor. Container oluşturduktan sonra "Upload" butonuna tıklayarak verilerinizi yükleyebiliriz.

![image](https://user-images.githubusercontent.com/127193220/235669968-5221cc72-9905-474b-afe0-5ad4d3d1d778.png)

Synapse Studioda csv dosyasını sorgulayabiliriz.

![image](https://user-images.githubusercontent.com/127193220/235670072-f8aa6290-7900-4522-9474-30f910b2365e.png)

Select TOP 100 rows

![image](https://user-images.githubusercontent.com/127193220/235670175-65a8bcfe-ec30-412d-be74-dad44765201a.png)

SQL'de veri kaynağını tarif ederek kullanma

Master Key ve Credential oluşturma

![image](https://user-images.githubusercontent.com/127193220/235670259-23cc388d-7033-4717-846c-3380b63fca75.png)

External Data Source Oluşturma

![image](https://user-images.githubusercontent.com/127193220/235670350-2ac84001-85de-4134-8a53-a07db49abe19.png)

Kaynaktan Veri Setini Okuma

![image](https://user-images.githubusercontent.com/127193220/235670476-2d705bf3-c740-40d8-a90f-79af96d5a998.png)

Json Dökümanını Okuma

İlk aşama olarak Json verisini yüklememiz gerekiyor.

![image](https://user-images.githubusercontent.com/127193220/235670565-c65e1bd5-a6b2-450a-965b-5388e074a1a2.png)

JSON_VALUE yardımıyla sorgumuzu oluşturuyoruz.

![image](https://user-images.githubusercontent.com/127193220/235670642-1bdb6db8-d313-4361-9ee2-45d57f653872.png)

Klasörlerin içinden verileri okuma

![image](https://user-images.githubusercontent.com/127193220/235670733-90e05ddf-bf23-443d-ae5a-66c61622989b.png)

![image](https://user-images.githubusercontent.com/127193220/235670778-2e25d65b-2bb8-4cd9-9f9d-e7b285106cb3.png)

