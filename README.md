# Azure Synapse Analytics ile Veri Entegrasyonu, Analizi ve Rapor Oluşturma Süreci

Büyük veri analizi ve işleme için kullanılan bir bulut tabanlı veri analitiği platformu olan Azure Synapse Analytics, veri entegrasyonu, analizi ve rapor oluşturma süreçlerini kolaylaştırır. Bu makalede, Azure Synapse Analytics'i oluşturma ve yapılandırma adımlarını, güvenlik önlemlerini, veri entegrasyonu ve rapor oluşturma işlemlerini adım adım inceleyeceğiz.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/6f546674-b5d1-4e9c-9b4d-9787d1fa51ab)

**Azure Synapse Analytics Oluşturma**

Bu aşamada, Azure Synapse Analytics hizmetini oluşturmanız gerekmektedir. Bu hizmet, büyük veri analizi ve işleme için kullanılan bir bulut tabanlı veri analitiği platformudur.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/00b1a1d4-a563-408b-9326-97dd4a5d1ac2)

**Security**

Azure Synapse Analytics'i oluşturduktan sonra, güvenlik önlemlerini gözden geçirip yapılandırmanız gerekmektedir. Bu adım, verilerinizin güvende olduğundan emin olmanızı sağlar.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/6a40ff6f-2f77-43e6-8204-ef7bec72e22e)

**Review and Create**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/dde8b441-0f59-4784-b60c-28861c9eefe1)

**Deployment**

Bu adımda, kaynak gruplarına giderek Azure Synapse Studio'yu açmanız gerekmektedir. Azure Synapse Studio, veri analitiği ve işleme görevlerini gerçekleştirmek için kullanılan bir araçtır.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/e060b9e6-1f37-4b5f-8e4f-a6c1290b98d4)

**Go to resources group**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/71fce2e3-f10b-42c1-8417-d959de2cb509)

**Open Synapse Studio**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/626caa5e-bb4b-4bb5-9634-c87151b2b974)

**Integration Runtime Oluşturma**

Lokal verilerle etkileşimde bulunmak için bir Integration Runtime oluşturmanız gerekmektedir. Bu, Azure ve yerel (lokal) sistem arasında iletişimi sağlar.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/8ff857b8-50f3-433d-b7a8-dab141d25341)

Manage Hub üzerinden sadece isimlendirme yaparak indirilebilir.

**Azure Self Hosted Seçimi**

İsimlendirme yaparak Azure Self Hosted seçimini gerçekleştirebilirsiniz. Bu seçenek, Azure'da barındırılan bir self-hosted çözüm oluşturmanızı sağlar.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/9bba65da-8f6a-431f-9e39-b46d3d7a3cf2)

**İsimlendirme**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/68b6edc1-3c8f-4397-a6e1-c58c066e4cc8)

Bu adımda, Express Setup kurulumunu gerçekleştirmeniz gerekmektedir. Bu adım Self Hosted çözümünüzün kurulumunu hızlı bir şekilde tamamlamanıza olanak sağlar.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/a84a28bc-dc60-4006-92cd-387322656044)

Express Setup'ı tamamladıktan sonra, Exe kurulumunu gerçekleştirmeniz gerekmektedir. Bu adım, Self Hosted çözümünüzün tanımlanmasını sağlar.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/240df75a-1bee-4c73-8705-ceb0abf3299b)

Self Hosted kurulumu tamamlandı.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/4e488dfb-7730-4b67-a9b9-7edd7c8cddee)

**Integrate**

Bu aşamada, yerel sistemden veri alacaksınız ve ilk aşamada bir "staging" (geçici depolama) oluşturacaksınız.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/59c7b26e-77c0-4d8b-b397-291cd0b42c1d)

**Copy Data Tool (Veri Kopyalama Aracı) – Wizard**

Veriye erişeceğiniz kaynak veri deposunu tanımlamanız gerekmektedir. Bu aşamada, kendi yerel SQL veritabanınıza bağlanacaksınız.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/68713669-250f-4552-8945-4bcbae3574d2)

**Source data store**

Veriye nereden erişeceğiniz ile ilgili tanımlama yapmanız gerekmektedir.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/1d335cd4-fc83-4aca-a20f-9afc33be5927)

**New Connection**

Kendi lokanizdeki sql veritabanına bağlanmalısınız.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/e6729d32-d687-4ce7-b1da-2cebbcfd0d8d)

Locale bağlanacağımız için bir önceki aşamada oluşturduğumuz Integration Runtime seçeneğini yaptıktan sonra hangi serverla hangi veritabanına erişmeye çalıştığımızla ilgili tanımlamaları yapıyoruz.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/03bd1a29-08f0-474f-8de8-9daa24b37fa2)

ContosoRetailDW veritabanımızın içinde yer alan tabloları görebiliyoruz. Raporu oluşturacağımız tabloları seçmemiz gerekiyor.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/0418d140-87fc-425e-94e9-67abf16d2fe1)

**Destination**

Azure Blob Storage'da bulunan bir container'ı tanımlayacaksınız. Bu, verilerinizi depolayacağınız yerin belirlenmesini sağlar.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/e0e361e3-cbbd-46f3-b957-ff59bc71f8d0)

**Summary**

Lokalde Sql veri tabanından azuredaki containera kopyalacağını belirtiyor. Diğer bir ifadeyle Staging oluşturulacak.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/be699090-39e2-4fea-8a12-6d6b1fc244e3)

Pipeline işlemi tamamlandı.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/4ce7687c-4a01-463c-9c3d-bdb510411cff)

**Pipeline**

Verileri yerel SQL veritabanından Azure Blob Storage'a kopyalamak için bir pipeline oluşturmanız gerekmektedir.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/59fe99ae-04d2-434a-a05b-cf6667fa3d50)

Pipeline ForEach içinde oluşturuldu çünkü 4 tablo seçimi yaptığımız için her biri için arka tarafta copy taskları oluşturdu.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/cc3d3fd7-55ec-47cc-911d-e2381a3e6f8e)

**DWH oluşturma**

Verileri analiz etmek için SQL havuzu (SQL pool) oluşturmanız gerekmektedir. Bu adımı gerçekleştirmek için "Data" bölümünde yer alan "+" simgesine tıklayarak yeni bir SQL veritabanı oluşturmayı seçmelisiniz.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/d0fa2144-0282-4d1e-9f5d-8543355d6e93)

**Dedicated Pool Oluşturma**

SQL pool için bir "Dedicated Pool" oluşturmanız gerekmektedir. Bu havuz, yönetim merkezi (manage hub) bölümünden oluşturulduğu için "manage pool" ifadesine tıklayarak yönetim merkezi sayfasına yönlendirileceksiniz.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/25bf01ac-c539-4a87-9069-80f585af2ebf)

**Not:** Dedicated pool, manage hub kısmından oluşturulduğu için aşağıdaki manage pool ifadesine tıklayarak manage hub sayfasına yönlendirebilmektedir.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/dea628a8-6881-441b-855a-264a3cf52de1)

**Review and Create**

Dedicated Pool oluşturduktan sonra, inceleme yaparak işleminizi tamamlayabilir ve havuzu oluşturabilirsiniz.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/07dee706-619d-42e6-9464-7f2dcebc97fa)

**Deployment**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/c97ddb89-8226-4965-b9bf-ca102e49d54b)

**Staging to DWH**

Copy Data aracını kullanarak oluşturduğunuz "staging" veritabanını SQL havuzuna aktarmanız gerekmektedir. Bu adımda kaynak veri deposunu tanımladıktan sonra verileri hedefe aktarmanız sağlanır.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/2c643361-a769-451e-a436-9afa8a0be768)

**Source data store**

Kaynaktaki bulunan tablolarımın container bilgisini tanımını tamamlamamız gerekiyor.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/70ffabd1-6a21-4590-a7a6-d23415902f6e)

**Destination**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/a68ae4cd-91e8-4b47-bda9-8f57c4c1b0b7)

**Settings**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/ecbd4ce9-b3a6-475c-a273-03fef5fa95d9)

**Summary**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/1a0b3d1c-1800-480f-b222-7e411e795a9e)

**Deployment**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/35e0701b-4149-4079-883e-a4f0f864a970)

Aktarım gerçekleşti.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/7771d260-c23f-48a3-b8b8-872e8802b72a)

**Power Bi Bağlantısı**

Power BI ile bağlantı kurmak için yeni bir bağlantı servisi (linked service) oluşturmanız gerekmektedir. Bu bağlantı servisi, Power BI ile veri paylaşımını sağlar.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/7b44f35f-ae33-4dae-bf27-85d326593956)

**New Linked Service**

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/dd651dd2-bb11-4b31-8417-a2f759f633a2)

**Develop**

Develop alanında Power BI bağlantınızı görebilirsiniz.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/525c1e8c-3b67-49f0-96cf-8ca06e5e3b1e)

**New Power BI Dataset**

Oluşturduğunuz veri kümesine bağlanmak istediğinizi belirterek yeni bir Power BI veri kümesi oluşturmanız gerekmektedir.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/94dd070d-fb36-4bcc-a3db-dbafa8f1ec18)

Power BI raporunu hazır hale getirerek indirebilirsiniz. Bu adımda, veritabanınıza aktarılan tabloya bağlanarak rapor oluşturabilir ve analiz yapabilirsiniz.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/b22456d4-1136-4dfd-a2e4-561bc310bdeb)

**SQL’e bağlanma**

Aktarılan tablonuzun veritabanına bağlanma işlemini gerçekleştirebilirsiniz. Bu adımda, SQL'e bağlanarak verileri sorgulayabilir ve işleyebilirsiniz.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/2997289d-e39c-4894-ad79-99a7cb85dd3e)

Aktarım yaptığımız tablomuzun veritabını da aşağıdaki görselde görmekteyiz.

![image](https://github.com/aysegulyigitbi/Azure-Synapse-Analytics/assets/127193220/fe14be07-5fc7-4f8f-ba65-c21d2f300d14)

Yukarıdaki aşamalar, Azure Synapse Analytics kullanarak veri entegrasyonu, veri analizi ve rapor oluşturma sürecini anlatmaktadır. Bu aşamaları takip ederek, yerel ve bulut tabanlı kaynaklardan veri alabilir, işleyebilir ve görselleştirebilirsiniz.
