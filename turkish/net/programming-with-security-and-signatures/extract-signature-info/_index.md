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