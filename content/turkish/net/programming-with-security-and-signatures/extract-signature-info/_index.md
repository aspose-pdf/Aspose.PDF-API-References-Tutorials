---
title: İmza Bilgilerini Çıkarın
linktitle: İmza Bilgilerini Çıkarın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak imza bilgilerini çıkarma.
type: docs
weight: 80
url: /tr/net/programming-with-security-and-signatures/extract-signature-info/
---
Bir PDF belgesinden imza bilgilerinin çıkarılması işlemi, çeşitli senaryolarda oldukça faydalı olabilir. İmzalı bir belgenin gerçekliğini doğrulamanız veya imza için kullanılan sertifikayı analiz etmeniz gerekiyorsa Aspose.PDF for .NET kütüphanesi uygun bir çözüm sunar. Bu öğreticide, sağlanan C# kaynak kodunu kullanarak imza bilgilerinin çıkarılmasına ilişkin adım adım süreçte size rehberlik edeceğiz.

## Gereksinimler

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Temel C# programlama dili bilgisi.
2. Aspose.PDF for .NET kütüphanesi sisteminizde kuruludur.
3. Bir veya daha fazla imza alanına sahip geçerli bir PDF belgesi.

Şimdi uygulama detaylarına geçelim.

## 1. Adım: Gerekli Kitaplıkları İçe Aktarma

 Başlamak için gerekli kitaplıkları C# projenize aktarmanız gerekir. Bu durumda import etmemiz gerekiyor.`Aspose.Pdf` Ve`System.IO` ad alanları. Bu, C# dosyanızın başına aşağıdaki kodu ekleyerek yapılabilir:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Adım 2: Belge Yolunu Ayarlama

Daha sonra imza bilgilerini çıkarmak istediğiniz PDF belgesinin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin gerçek yolunu içeren aşağıdaki kod parçacığında:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Adım 3: İmza Bilgilerinin Çıkarılması

Şimdi kodun PDF belgesinden imza bilgilerini çıkaracağımız ana kısmına geçelim. Belge formundaki her alanı yineliyoruz ve bunun bir imza alanı olup olmadığını kontrol ediyoruz. İmza alanı bulunursa sertifikayı çıkarmaya devam ederiz. Aşağıdaki kod parçacığını ekleyin:

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

## Adım 4: Sertifikanın Çıkarılması

Bu adımda sertifikayı imza alanından çıkartıp dosya olarak kaydediyoruz. Çıkarılan sertifika daha fazla analiz edilebilir veya doğrulama amacıyla kullanılabilir. Aşağıdaki kod parçacığı, çıkarma ve kaydetme işlemini gösterir:

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

: Sertifikanın Kaydedilmesi

Son olarak çıkarttığımız sertifikayı dosya olarak kaydediyoruz. Bu örnekte sertifika, belirtilen dizine "input.cer" adıyla kaydedilir. Kodu gereksinimlerinize uyacak şekilde değiştirebilirsiniz. Sertifikayı kaydetmeye yönelik kod pasajı aşağıda verilmiştir:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Bu kadar! Aspose.PDF for .NET'i kullanarak imza bilgilerini başarıyla çıkardınız. Bu kodu kendi uygulamalarınıza entegre etmekten veya ihtiyaçlarınıza göre değiştirmekten çekinmeyin.

### Aspose.PDF for .NET kullanarak İmza Bilgilerini Çıkarma için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
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

Bu eğitimde, Aspose.PDF for .NET kitaplığını kullanarak bir PDF belgesinden imza bilgilerinin nasıl çıkarılacağına ilişkin adım adım kılavuzu inceledik. Gerekli kitaplıkların içe aktarılması, belge yolunun ayarlanması, imza bilgilerinin çıkarılması, sertifikanın çıkarılması ve bir dosyaya kaydedilmesi sürecini ele aldık. Bu adımları izleyerek imza ayrıntılarını kolayca alabilir ve gerektiğinde onlarla çalışabilirsiniz.

### SSS'ler

#### S: Neden bir PDF belgesinden imza bilgilerini çıkarmam gerekiyor?

C: Bir PDF belgesinden imza bilgilerinin çıkarılması, imzalı bir belgenin orijinalliğini doğrulamak ve imza için kullanılan sertifikayı analiz etmek için kullanışlıdır. Bu süreç, imzalanan içeriğin bütünlüğünün sağlanmasına yardımcı olur ve yasal ve güvenlik açısından gerekli olabilir.

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF belgeleriyle çalışmasına olanak tanıyan bir kitaplıktır. PDF dosyalarını programlı olarak oluşturmak, değiştirmek ve bunlarla etkileşimde bulunmak için çok çeşitli özellikler sağlar.

#### S: Aspose.PDF for .NET kullanarak imza bilgilerini çıkarmanın önkoşulları nelerdir?

C: İmza bilgilerini çıkarmak için temel C# programlama dili bilgisine, sisteminizde kurulu Aspose.PDF for .NET kitaplığına ve bir veya daha fazla imza alanı içeren geçerli bir PDF belgesine ihtiyacınız vardır.

#### S: Çıkarma işlemi için gerekli kitaplıkları nasıl içe aktarabilirim?

C: Gerekli kütüphaneleri ekleyerek içe aktarabilirsiniz.`using` için direktifler`Aspose.Pdf` Ve`System.IO` C# dosyanızın başında. Bu yönergeler imza bilgilerini çıkarmak için gereken sınıfları ve yöntemleri kullanmanızı sağlar.

#### S: İmza bilgilerinin çıkarılması için PDF belgesini nasıl belirlerim?

 C: PDF belgesinin yolunu değiştirerek ayarlayabilirsiniz.`"YOUR DOCUMENTS DIRECTORY"` sağlanan kod pasajında belgenizin gerçek yolunu belirtin. Bu yol, imza bilgilerini çıkarmak istediğiniz PDF belgesini yüklemek için kullanılır.

#### S: Bir PDF belgesinden imza bilgilerinin çıkarılması süreci nedir?

C: Çıkarma işlemi, PDF belgesinin form alanlarının yinelenmesini, her alanın bir imza alanı olup olmadığının kontrol edilmesini ve öyleyse ilgili sertifikanın çıkarılmasını içerir. Çıkarılan sertifika daha fazla analiz veya doğrulama için dosya olarak kaydedilebilir.

#### S: Sertifika imza alanından nasıl çıkarılır?

C: Sertifika, imza alanından çıkarılır.`ExtractCertificate()` tarafından sağlanan yöntem`SignatureField` Aspose.PDF for .NET'teki sınıf. Bu yöntem, sertifika verilerini içeren bir akış döndürür.

#### S: Çıkarılan sertifikayı dosya olarak nasıl kaydederim?

 C: Çıkarılan sertifikayı, sertifika akışını okuyup içeriğini bir dosyaya yazarak dosya olarak kaydedebilirsiniz.`FileStream` sınıf. Öğreticide sağlanan kod bu işlemi göstermektedir.

#### S: Çıkarılan bu sertifikayı imza doğrulama için kullanabilir miyim?

C: Evet, çıkarılan sertifika imza doğrulaması için kullanılabilir. İmzalanan belgenin bütünlüğünü sağlamak için sertifikanın ayrıntılarını analiz edebilir ve orijinalliğini doğrulayabilirsiniz.

#### S: Bu kodu kendi uygulamalarıma nasıl entegre edebilirim?

C: Sağlanan kodu, adım adım kılavuzu izleyerek kendi C# uygulamalarınıza entegre edebilirsiniz. Yolları ve dosya adlarını gerektiği gibi değiştirin ve kodu mevcut projelerinize ekleyin.

#### S: Aspose.PDF for .NET'te imza yönetimiyle ilgili başka özellikler var mı?

C: Evet, Aspose.PDF for .NET dijital imzalarla çalışmak için belgeleri imzalamak, imzaları doğrulamak ve zaman damgası bilgileri eklemek gibi çeşitli özellikler sunar. Bu özellikler hakkında daha fazla ayrıntı için resmi belgeleri inceleyebilirsiniz.

#### S: Aspose.PDF for .NET'i kullanmak için ek kaynakları nerede bulabilirim?

 C: .NET için Aspose.PDF kullanımına ilişkin daha fazla bilgi, eğitim ve kaynak için,[Aspose.PDF for .NET](https://reference.aspose.com/pdf/net/).

#### S: Şifrelenmiş PDF belgelerinden imza çıkarmak mümkün müdür?

C: Şifrelenmiş PDF belgelerinden imza çıkarma yeteneği, belgenin şifreleme ayarlarına ve izinlerine bağlı olabilir. İmza bilgilerine erişmek ve bunları çıkarmak için gerekli izinlere sahip olduğunuzdan emin olmanız gerekebilir.

#### S: Tek bir PDF belgesinden birden fazla imzayı çıkarabilir miyim?

C: Evet, sağlanan kodu, PDF belgesindeki tüm imza alanlarını yineleyecek ve her birinden imza bilgilerini çıkaracak şekilde değiştirebilirsiniz. Bu, belgede bulunan birden fazla imza hakkında bilgi almanıza olanak tanır.

#### S: İmza bilgilerini ayıklamak için bazı pratik kullanım durumları nelerdir?

C: İmza bilgilerini çıkarmaya yönelik bazı pratik kullanım örnekleri arasında dijital olarak imzalanmış belgelerin orijinalliğinin doğrulanması, uyumluluk amacıyla sertifika ayrıntılarının analiz edilmesi ve denetim amacıyla imzaların ve imza sahiplerinin kayıtlarının tutulması yer alır.

#### S: İmza bilgilerini alırken herhangi bir yasal husus var mı?

C: İmza bilgilerinin çıkarılmasının, özellikle yasal olarak bağlayıcı belgeler kullanılırken yasal sonuçları olabilir. Bulunduğunuz yargı bölgesindeki elektronik imzalar ve belge orijinalliğiyle ilgili ilgili düzenlemelere ve yasalara uyduğunuzdan emin olun.