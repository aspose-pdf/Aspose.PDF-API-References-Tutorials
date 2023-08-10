---
title: İmza Bilgilerini Çıkarın
linktitle: İmza Bilgilerini Çıkarın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak imza bilgilerini çıkarma.
type: docs
weight: 80
url: /tr/net/programming-with-security-and-signatures/extract-signature-info/
---
Bir PDF belgesinden imza bilgilerini çıkarma işlemi, çeşitli senaryolarda oldukça yararlı olabilir. Aspose.PDF for .NET kitaplığı, ister imzalanmış bir belgenin orijinalliğini doğrulamanız, ister imza için kullanılan sertifikayı analiz etmeniz gereksin, uygun bir çözüm sunar. Bu öğreticide, sağlanan C# kaynak kodunu kullanarak imza bilgilerini ayıklama işleminde size adım adım rehberlik edeceğiz.

## Gereksinimler

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. C# programlama dili hakkında temel bilgi.
2. Sisteminizde kurulu olan Aspose.PDF for .NET kitaplığı.
3. Bir veya daha fazla imza alanına sahip geçerli bir PDF belgesi.

Şimdi uygulama detaylarına geçelim.

## 1. Adım: Gerekli Kitaplıkları İçe Aktarma

 Başlamak için gerekli kitaplıkları C# projenize aktarmanız gerekir. Bu durumda import etmemiz gerekiyor.`Aspose.Pdf` Ve`System.IO` ad alanları. Bu, C# dosyanızın başına aşağıdaki kodu ekleyerek yapılabilir:

```csharp
using Aspose.Pdf;
using System.IO;
```

## 2. Adım: Belge Yolunu Ayarlama

Ardından, imza bilgilerini çıkarmak istediğiniz PDF belgesinin yolunu belirlemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin gerçek yolu ile aşağıdaki kod parçacığında:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## 3. Adım: İmza Bilgilerini Çıkarma

Şimdi imza bilgilerini PDF belgesinden çıkardığımız kodun ana kısmına geçelim. Belgenin formundaki her alanı yineliyoruz ve bunun bir imza alanı olup olmadığını kontrol ediyoruz. Bir imza alanı bulunursa, sertifikayı çıkarmaya devam ederiz. Aşağıdaki kod parçacığını ekleyin:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Sertifikayı ayıklayın
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

## 4. Adım: Sertifikayı Çıkarma

Bu adımda imza alanından sertifikayı çıkartıp dosya olarak kaydediyoruz. Çıkarılan sertifika daha fazla analiz edilebilir veya doğrulama amacıyla kullanılabilir. Aşağıdaki kod parçacığı, çıkarma ve kaydetme sürecini gösterir:

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

Son olarak, çıkarılan sertifikayı bir dosya olarak kaydediyoruz. Bu örnekte, sertifika belirtilen dizine "input.cer" adıyla kaydedilmiştir. Gereksinimlerinize uyacak şekilde kodu değiştirebilirsiniz. İşte sertifikayı kaydetmek için kod pasajı:

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

Bu öğreticide, Aspose.PDF for .NET kitaplığı kullanılarak bir PDF belgesinden imza bilgilerinin nasıl çıkarılacağına ilişkin adım adım bir kılavuz üzerinde yürüdük. Gerekli kitaplıkların içe aktarılması, belge yolunun ayarlanması, imza bilgilerinin çıkarılması, sertifikanın çıkarılması ve bir dosyaya kaydedilmesi sürecini ele aldık. Bu adımları izleyerek imza ayrıntılarını kolayca alabilir ve gerektiğinde bunlarla çalışabilirsiniz.

### SSS

#### S: Neden bir PDF belgesinden imza bilgileri almam gerekiyor?

C: İmza bilgilerini bir PDF belgesinden çıkarmak, imzalanmış bir belgenin gerçekliğini doğrulamak ve imza için kullanılan sertifikayı analiz etmek için kullanışlıdır. Bu süreç, imzalanan içeriğin bütünlüğünün sağlanmasına yardımcı olur ve yasal ve güvenlik amaçları için gerekli olabilir.

#### S: Aspose.PDF for .NET nedir?

Y: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF belgeleriyle çalışmasını sağlayan bir kitaplıktır. Programlı olarak PDF dosyaları oluşturmak, değiştirmek ve bunlarla etkileşim kurmak için çok çeşitli özellikler sağlar.

#### S: Aspose.PDF for .NET kullanarak imza bilgilerini ayıklamak için ön koşullar nelerdir?

C: İmza bilgilerini ayıklamak için temel C# programlama dili bilgisine, sisteminizde kurulu Aspose.PDF for .NET kitaplığına ve bir veya daha fazla imza alanı içeren geçerli bir PDF belgesine ihtiyacınız var.

#### S: Çıkarma işlemi için gerekli kitaplıkları nasıl içeri aktarırım?

A: Gerekli kütüphaneleri ekleyerek içe aktarabilirsiniz.`using` direktifler`Aspose.Pdf` Ve`System.IO` C# dosyanızın başında. Bu yönergeler, imza bilgilerini ayıklamak için gerekli sınıfları ve yöntemleri kullanmanızı sağlar.

#### S: İmza bilgilerini ayıklamak için PDF belgesini nasıl belirtebilirim?

 A: Değiştirerek PDF belgesine giden yolu ayarlayabilirsiniz.`"YOUR DOCUMENTS DIRECTORY"` sağlanan kod parçacığında belgenizin gerçek yolu ile birlikte. Bu yol, imza bilgilerini çıkarmak istediğiniz PDF belgesini yüklemek için kullanılır.

#### S: Bir PDF belgesinden imza bilgilerini çıkarma süreci nedir?

C: Ayıklama işlemi, PDF belgesinin form alanları arasında yineleme yapmayı, her alanın bir imza alanı olup olmadığını kontrol etmeyi ve öyleyse ilişkili sertifikayı çıkarmayı içerir. Ayıklanan sertifika, daha fazla analiz veya doğrulama için bir dosya olarak kaydedilebilir.

#### S: İmza alanından sertifika nasıl çıkarılır?

A: Sertifika, kullanılarak bir imza alanından çıkarılır.`ExtractCertificate()` tarafından sağlanan yöntem`SignatureField` Aspose.PDF for .NET'te sınıf. Bu yöntem, sertifika verilerini içeren bir akış döndürür.

#### S: Ayıklanan sertifikayı dosya olarak nasıl kaydedebilirim?

 Y: Çıkarılan sertifikayı, sertifika akışını okuyarak ve içeriğini kullanarak bir dosyaya yazarak bir dosya olarak kaydedebilirsiniz.`FileStream` sınıf. Öğreticide sağlanan kod bu işlemi gösterir.

#### S: Çıkarılan bu sertifikayı imza doğrulaması için kullanabilir miyim?

C: Evet, çıkarılan sertifika imza doğrulaması için kullanılabilir. İmzalanan belgenin bütünlüğünden emin olmak için sertifikanın ayrıntılarını analiz edebilir ve orijinalliğini doğrulayabilirsiniz.

#### S: Bu kodu kendi uygulamalarıma nasıl entegre edebilirim?

A: Sağlanan kodu, adım adım kılavuzu izleyerek kendi C# uygulamalarınıza entegre edebilirsiniz. Yolları ve dosya adlarını gerektiği gibi değiştirin ve kodu mevcut projelerinize dahil edin.

#### S: Aspose.PDF for .NET'te imza yönetimi ile ilgili başka özellikler var mı?

Y: Evet, Aspose.PDF for .NET dijital imzalarla çalışmak için belgeleri imzalama, imzaları doğrulama ve zaman damgası bilgisi ekleme gibi bir dizi özellik sunar. Bu özellikler hakkında daha fazla ayrıntı için resmi belgeleri inceleyebilirsiniz.

#### S: Aspose.PDF for .NET'i kullanmak için ek kaynakları nereden bulabilirim?

 C: .NET için Aspose.PDF kullanımına ilişkin daha fazla bilgi, eğitim ve kaynak için,[Aspose.PDF for .NET](https://reference.aspose.com/pdf/net/).

#### S: Şifrelenmiş PDF belgelerinden imza çıkarmak mümkün mü?

Y: Şifrelenmiş PDF belgelerinden imza çıkarma yeteneği, belgenin şifreleme ayarlarına ve izinlerine bağlı olabilir. İmza bilgilerine erişmek ve bunları çıkarmak için gerekli izinlere sahip olduğunuzdan emin olmanız gerekebilir.

#### S: Tek bir PDF belgesinden birden fazla imza çıkarabilir miyim?

C: Evet, sağlanan kodu PDF belgesindeki tüm imza alanlarında yinelemek ve her birinden imza bilgilerini çıkarmak için değiştirebilirsiniz. Bu, belgede bulunan birden fazla imza hakkında bilgi almanıza olanak tanır.

#### S: İmza bilgilerini ayıklamak için bazı pratik kullanım durumları nelerdir?

Y: İmza bilgilerini ayıklamak için bazı pratik kullanım örnekleri arasında, dijital olarak imzalanmış belgelerin orijinalliğinin doğrulanması, uyumluluk amacıyla sertifika ayrıntılarının analiz edilmesi ve denetim amacıyla imzaların ve imzalayanların bir kaydının tutulması yer alır.

#### S: İmza bilgilerini alırken herhangi bir yasal husus var mı?

Y: İmza bilgilerinin alınmasının, özellikle yasal olarak bağlayıcı belgelerle çalışırken yasal sonuçları olabilir. Kendi yetki alanınızdaki elektronik imzalar ve belge gerçekliği ile ilgili düzenlemelere ve yasalara uyduğunuzdan emin olun.