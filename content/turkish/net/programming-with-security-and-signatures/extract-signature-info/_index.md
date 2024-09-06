---
title: İmza Bilgilerini Çıkar
linktitle: İmza Bilgilerini Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanılarak imza bilgilerinin çıkarılması.
type: docs
weight: 80
url: /tr/net/programming-with-security-and-signatures/extract-signature-info/
---
Bir PDF belgesinden imza bilgilerini çıkarma süreci çeşitli senaryolarda oldukça faydalı olabilir. İster imzalanmış bir belgenin gerçekliğini doğrulamanız, ister imza için kullanılan sertifikayı analiz etmeniz gereksin, Aspose.PDF for .NET kitaplığı kullanışlı bir çözüm sunar. Bu eğitimde, sağlanan C# kaynak kodunu kullanarak imza bilgilerini çıkarma adım adım sürecinde size rehberlik edeceğiz.

## Gereksinimler

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. C# programlama dilinin temel bilgisi.
2. Sisteminizde Aspose.PDF for .NET kütüphanesi yüklü olmalıdır.
3. Bir veya daha fazla imza alanına sahip geçerli bir PDF belgesi.

Şimdi uygulama detaylarına geçelim.

## Adım 1: Gerekli Kitaplıkları İçe Aktarma

 Başlamak için, gerekli kütüphaneleri C# projenize aktarmanız gerekir. Bu durumda, şunları aktarmamız gerekir:`Aspose.Pdf` Ve`System.IO` namespaces. Bu, C# dosyanızın başına aşağıdaki kodu ekleyerek yapılabilir:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Adım 2: Belge Yolunu Ayarlama

Sonra, imza bilgilerini çıkarmak istediğiniz PDF belgesinin yolunu ayarlamanız gerekir. Değiştir`"YOUR DOCUMENTS DIRECTORY"` Aşağıdaki kod parçasında belgenizin gerçek yolunu bulabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Adım 3: İmza Bilgilerini Çıkarma

Şimdi, PDF belgesinden imza bilgilerini çıkardığımız kodun ana kısmına geçelim. Belgenin formundaki her alanı yineliyoruz ve bir imza alanı olup olmadığını kontrol ediyoruz. Bir imza alanı bulunursa, sertifikayı çıkarmaya devam ediyoruz. Aşağıdaki kod parçacığını ekleyin:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Sertifikayı çıkarın
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Adım 4: Sertifikayı Çıkarma

Bu adımda, sertifikayı imza alanından çıkarırız ve bir dosya olarak kaydederiz. Çıkarılan sertifika daha fazla analiz edilebilir veya doğrulama amaçları için kullanılabilir. Aşağıdaki kod parçası çıkarma ve kaydetme sürecini gösterir:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Adım 5

: Sertifikayı Kaydetme

Son olarak, çıkarılan sertifikayı bir dosya olarak kaydediyoruz. Bu örnekte, sertifika belirtilen dizinde "input.cer" adıyla kaydedilir. Kodu gereksinimlerinize uyacak şekilde değiştirebilirsiniz. Sertifikayı kaydetmek için kod parçacığı şöyledir:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

İşte bu kadar! Aspose.PDF for .NET kullanarak imza bilgilerini başarıyla çıkardınız. Bu kodu kendi uygulamalarınıza entegre etmekten veya ihtiyaçlarınıza göre değiştirmekten çekinmeyin.

### .NET için Aspose.PDF kullanarak İmza Bilgilerini Çıkarmak için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kütüphanesini kullanarak bir PDF belgesinden imza bilgilerinin nasıl çıkarılacağına dair adım adım bir kılavuz izledik. Gerekli kütüphaneleri içe aktarma, belge yolunu ayarlama, imza bilgilerini çıkarma, sertifikayı çıkarma ve bir dosyaya kaydetme sürecini ele aldık. Bu adımları izleyerek, imza ayrıntılarını kolayca alabilir ve gerektiğinde bunlarla çalışabilirsiniz.

### SSS

#### S: PDF belgesinden imza bilgilerini neden çıkarmam gerekir?

A: Bir PDF belgesinden imza bilgilerini çıkarmak, imzalanmış bir belgenin gerçekliğini doğrulamak ve imza için kullanılan sertifikayı analiz etmek için yararlıdır. Bu süreç, imzalanmış içeriğin bütünlüğünün sağlanmasına yardımcı olur ve yasal ve güvenlik amaçları için önemli olabilir.

#### S: Aspose.PDF for .NET nedir?

A: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF belgeleriyle çalışmasını sağlayan bir kütüphanedir. PDF dosyalarını programatik olarak oluşturmak, değiştirmek ve etkileşim kurmak için çok çeşitli özellikler sunar.

#### S: Aspose.PDF for .NET kullanarak imza bilgilerini çıkarmak için ön koşullar nelerdir?

A: İmza bilgilerini çıkarmak için, C# programlama dili hakkında temel bilgiye, sisteminizde yüklü Aspose.PDF for .NET kütüphanesine ve bir veya daha fazla imza alanı içeren geçerli bir PDF belgesine ihtiyacınız vardır.

#### S: Çıkarma işlemi için gerekli kütüphaneleri nasıl içe aktarabilirim?

A: Gerekli kütüphaneleri ekleyerek içe aktarabilirsiniz.`using` için yönergeler`Aspose.Pdf` Ve`System.IO` C# dosyanızın başında. Bu yönergeler, imza bilgilerini çıkarmak için gereken sınıfları ve yöntemleri kullanmanızı sağlar.

#### S: İmza bilgilerinin çıkarılacağı PDF belgesini nasıl belirlerim?

 A: PDF belgesinin yolunu değiştirerek ayarlayabilirsiniz`"YOUR DOCUMENTS DIRECTORY"` Sağlanan kod parçacığında belgenizin gerçek yolu ile. Bu yol, imza bilgilerini çıkarmak istediğiniz PDF belgesini yüklemek için kullanılır.

#### S: PDF belgesinden imza bilgisi çıkarma süreci nasıldır?

A: Çıkarma işlemi, PDF belgesinin form alanlarında yineleme yapmayı, her alanın bir imza alanı olup olmadığını kontrol etmeyi ve öyleyse ilişkili sertifikayı çıkarmayı içerir. Çıkarılan sertifika, daha fazla analiz veya doğrulama için bir dosya olarak kaydedilebilir.

#### S: İmza alanından sertifika nasıl çıkarılır?

A: Sertifika, imza alanından şu şekilde çıkarılır:`ExtractCertificate()` tarafından sağlanan yöntem`SignatureField` .NET için Aspose.PDF'deki sınıf. Bu yöntem sertifika verilerini içeren bir akış döndürür.

#### S: Çıkarılan sertifikayı dosya olarak nasıl kaydederim?

 A: Sertifika akışını okuyup içeriğini bir dosyaya yazarak çıkarılan sertifikayı bir dosya olarak kaydedebilirsiniz.`FileStream` sınıf. Eğitimde sağlanan kod bu süreci göstermektedir.

#### S: Bu çıkarılan sertifikayı imza doğrulaması için kullanabilir miyim?

A: Evet, çıkarılan sertifika imza doğrulaması için kullanılabilir. İmzalanan belgenin bütünlüğünü sağlamak için sertifikanın ayrıntılarını analiz edebilir ve gerçekliğini doğrulayabilirsiniz.

#### S: Bu kodu kendi uygulamalarıma nasıl entegre edebilirim?

A: Sağlanan kodu adım adım kılavuzu izleyerek kendi C# uygulamalarınıza entegre edebilirsiniz. Gerektiğinde yolları ve dosya adlarını değiştirin ve kodu mevcut projelerinize dahil edin.

#### S: Aspose.PDF for .NET'te imza yönetimiyle ilgili başka özellikler var mı?

C: Evet, Aspose.PDF for .NET, belgeleri imzalama, imzaları doğrulama ve zaman damgası bilgileri ekleme gibi dijital imzalarla çalışmak için bir dizi özellik sunar. Bu özellikler hakkında daha fazla ayrıntı için resmi belgeleri inceleyebilirsiniz.

#### S: Aspose.PDF for .NET'i kullanmak için ek kaynakları nerede bulabilirim?

 A: .NET için Aspose.PDF'i kullanma hakkında daha fazla bilgi, eğitim ve kaynak için,[Aspose.PDF for .NET](https://reference.aspose.com/pdf/net/).

#### S: Şifrelenmiş PDF belgelerinden imza çıkarmak mümkün müdür?

A: Şifrelenmiş PDF belgelerinden imzaları çıkarma yeteneği, belgenin şifreleme ayarlarına ve izinlerine bağlı olabilir. İmza bilgilerine erişmek ve bunları çıkarmak için gerekli izinlere sahip olduğunuzdan emin olmanız gerekebilir.

#### S: Tek bir PDF belgesinden birden fazla imzayı çıkarabilir miyim?

C: Evet, PDF belgesindeki tüm imza alanlarında yineleme yapmak ve her birinden imza bilgilerini çıkarmak için sağlanan kodu değiştirebilirsiniz. Bu, belgede bulunan birden fazla imza hakkında bilgi çıkarmanıza olanak tanır.

#### S: İmza bilgilerinin çıkarılması için bazı pratik kullanım durumları nelerdir?

A: İmza bilgilerinin çıkarılması için bazı pratik kullanım durumları arasında, dijital olarak imzalanmış belgelerin gerçekliğini doğrulamak, uyumluluk amaçları doğrultusunda sertifika ayrıntılarını analiz etmek ve denetim amaçları doğrultusunda imzaların ve imzalayanların kaydını tutmak yer alır.

#### S: İmza bilgilerinin çıkarılmasında herhangi bir hukuki husus var mıdır?

A: İmza bilgilerinin çıkarılması, özellikle yasal olarak bağlayıcı belgeleri ele alırken yasal sonuçlar doğurabilir. Yargı bölgenizde elektronik imzalar ve belge gerçekliğiyle ilgili ilgili düzenlemelere ve yasalara uyduğunuzdan emin olun.