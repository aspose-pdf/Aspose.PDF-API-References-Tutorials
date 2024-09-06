---
title: PDF Dosyasında Dijital Olarak Oturum Açın
linktitle: PDF Dosyasında Dijital Olarak Oturum Açın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasına dijital olarak nasıl imza atacağınızı öğrenin.
type: docs
weight: 40
url: /tr/net/programming-with-security-and-signatures/digitally-sign/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasında dijital olarak imzalama sürecini adım adım anlatacağız. Dijital imza, benzersiz bir elektronik parmak izi ekleyerek belgenin gerçekliğini ve bütünlüğünü garanti eder.

## Adım 1: Ön koşullar

Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi
- Visual Studio'yu makinenize yükleme
- .NET için Aspose.PDF kütüphanesi yüklendi

## Adım 2: Ortam kurulumu

Başlamak için geliştirme ortamınızı kurmak üzere şu adımları izleyin:

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. Gerekli ad alanlarını kod dosyanıza aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Adım 3: Dijital imza

İlk adım PDF dosyasını dijital olarak imzalamaktır. Sağlanan kod, .NET için Aspose.PDF ile dijital imzanın nasıl oluşturulacağını gösterir.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Bu kod bir PDF dosyasını yükler, belirtilen görünümde bir dijital imza oluşturur, ardından eklenen imzayla PDF dosyasını kaydeder.

## Adım 4: İmza Doğrulaması

Dijital imzayı ekledikten sonra PDF dosyasının geçerli bir imza içerip içermediğini kontrol edebilirsiniz.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Bir şey yap
                     }
                 }
             }
         }
     }
}
```

Bu kod PDF dosyasının ilk imzasını doğrular ve imza sertifikalıysa ve belirli izinlere sahipse ek işlemler gerçekleştirir.

### .NET için Aspose.PDF kullanarak Dijital İmza için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // PKCS7/PKCS7Detached nesnelerini kullanın
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// İmza görünümünü ayarla
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Üç imza türünden herhangi birini oluşturun
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Çıktı PDF dosyasını kaydet
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // İmza var mı?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // İlk önce doğrulayın
				{
					if (signature.IsCertified) // Sertifikalı mısınız?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Erişim izni al
						{
							// Bir şey yap
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyasında dijital imzayı başarıyla gerçekleştirdiniz. Bu eğitim, dijital imzayı eklemekten geçerliliğini doğrulamaya kadar adım adım süreci ele aldı. Artık bu özelliği kullanarak PDF dosyalarınızı dijital imzalarla güvence altına alabilirsiniz.

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF dosyasını dijital olarak imzalama sürecinde size rehberlik eder. Dijital imzalar, belgenin gerçekliğini ve bütünlüğünü sağlamak için elektronik bir parmak izi ekler.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

C: Başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olduğunuzdan, Visual Studio'nun ve .NET için Aspose.PDF kütüphanesinin yüklü olduğundan emin olun.

#### S: Geliştirme ortamını nasıl kurarım?

A: Visual Studio'da yeni bir C# projesi oluşturmak ve gerekli ad alanlarını içe aktarmak da dahil olmak üzere geliştirme ortamınızı kurmak için verilen adımları izleyin.

#### S: PDF dosyasına dijital imza nasıl eklerim?

 A: Sağlanan örnek kod, bir PDF dosyasının nasıl yükleneceğini, dijital imzanın nasıl oluşturulacağını, görünümün nasıl belirtileceğini ve imzalanmış PDF dosyasının nasıl kaydedileceğini gösterir. Dijital imza,`Certify` yöntemi`PdfFileSignature` nesne.

#### S: Dijital imzanın geçerliliğini nasıl doğrularım?

A: Dijital imzayı ekledikten sonra, imzanın geçerliliğini doğrulamak için örnek kodu kullanabilirsiniz. İmzanın sertifikalı olup olmadığını ve belirli erişim izinlerine sahip olup olmadığını kontrol eder.

####  S: Ne anlama geliyor?`PKCS7` object represent?

 A:`PKCS7` nesnesi dijital imzalar için kriptografik işlevselliği sağlamak için kullanılır. Sağlanan örnek kodda dijital imzayı oluşturmak için kullanılır.

#### S: Dijital imzanın görünümünü özelleştirebilir miyim?

 A: Evet, dijital imzanın görünümünü, dijital imzanın yolunu belirterek özelleştirebilirsiniz.`SignatureAppearance` mülkiyeti`PdfFileSignature` nesne.

#### S: İmza geçerli değilse ne olur?

A: İmza geçerli değilse doğrulama işlemi başarısız olur ve doğrulama kodu bloğundaki ilgili eylemler yürütülmez.

#### S: Dijital imzalarımın güvenliğini nasıl sağlayabilirim?

A: Dijital imzalar tasarım gereği güvenlidir ve kimlik doğrulama ve bütünlüğü sağlamak için kriptografik teknikler kullanır. Özel anahtarınızı güvende tuttuğunuzdan ve dijital imzaları işlemek için en iyi uygulamaları takip ettiğinizden emin olun.

#### S: Bir PDF'e birden fazla dijital imza ekleyebilir miyim?

 A: Evet, PDF dosyasına birden fazla dijital imza ekleyebilirsiniz.`PdfFileSignature` nesnenin`Sign` veya`Certify` yöntemler. Her imzanın kendine özgü görünümü ve yapılandırması olacaktır.