---
title: PDF Dosyasında Dijital Olarak Oturum Açın
linktitle: PDF Dosyasında Dijital Olarak Oturum Açın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasında dijital olarak nasıl oturum açacağınızı öğrenin.
type: docs
weight: 40
url: /tr/net/programming-with-security-and-signatures/digitally-sign/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasını dijital olarak imzalama sürecinde size yol göstereceğiz. Dijital imza, benzersiz bir elektronik parmak izi ekleyerek belgenin gerçekliğini ve bütünlüğünü garanti eder.

## 1. Adım: Önkoşullar

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Visual Studio'yu makinenize yükleme
- .NET için Aspose.PDF kitaplığı kurulu

## 2. Adım: Ortam kurulumu

Başlamak için, geliştirme ortamınızı kurmak üzere şu adımları izleyin:

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. Gerekli ad alanlarını kod dosyanıza aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## 3. Adım: Dijital imza

İlk adım, PDF dosyasını dijital olarak imzalamaktır. Sağlanan kod, Aspose.PDF for .NET ile dijital imzanın nasıl oluşturulacağını gösterir.

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

Bu kod bir PDF dosyası yükler, belirtilen görünüme sahip bir dijital imza oluşturur ve ardından eklenen imzayla PDF dosyasını kaydeder.

## 4. Adım: İmza Doğrulaması

Dijital imzayı ekledikten sonra, PDF dosyasının geçerli bir imza içerip içermediğini kontrol edebilirsiniz.

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

Bu kod, PDF dosyasının ilk imzasını doğrular ve imza onaylıysa ve belirli izinlere sahipse ek eylemler gerçekleştirir.

### Aspose.PDF for .NET kullanarak Digitally Sign için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // PKCS7/PKCS7Detached nesneleri kullanın
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
				if (signature.VerifySigned(sigNames[0] as string)) // İlkini doğrula
				{
					if (signature.IsCertified) // Sertifikalı mı?
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyasında başarıyla dijital imza gerçekleştirdiniz. Bu eğitim, dijital imzanın eklenmesinden geçerliliğinin doğrulanmasına kadar adım adım süreci kapsıyordu. Artık PDF dosyalarınızı dijital imzalarla güvenceye almak için bu özelliği kullanabilirsiniz.

### SSS

#### S: Bu eğitimin amacı nedir?

C: Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF dosyasını dijital olarak imzalama sürecinde size rehberlik eder. Dijital imzalar, belgenin orijinalliğini ve bütünlüğünü sağlamak için bir elektronik parmak izi ekler.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

C: Başlamadan önce, C# programlama dilini temel düzeyde anladığınızdan, Visual Studio'nun kurulu olduğundan ve Aspose.PDF kitaplığının .NET için kurulu olduğundan emin olun.

#### S: Geliştirme ortamını nasıl kurarım?

Y: Visual Studio'da yeni bir C# projesi oluşturmak ve gerekli ad alanlarını içeri aktarmak dahil olmak üzere, geliştirme ortamınızı ayarlamak için sağlanan adımları izleyin.

#### S: Bir PDF dosyasına nasıl dijital imza eklerim?

 Y: Sağlanan örnek kod, bir PDF dosyasının nasıl yükleneceğini, dijital imza oluşturulacağını, görünümün nasıl belirleneceğini ve imzalı PDF dosyasının nasıl kaydedileceğini gösterir. Dijital imza kullanılarak eklenir`Certify` yöntemi`PdfFileSignature` nesne.

#### S: Dijital imzanın geçerliliğini nasıl doğrularım?

C: Dijital imzayı ekledikten sonra, imzanın geçerliliğini doğrulamak için örnek kodu kullanabilirsiniz. İmzanın onaylı olup olmadığını ve belirli erişim izinlerine sahip olup olmadığını kontrol eder.

####  S: ne yapar`PKCS7` object represent?

 C:`PKCS7` nesne, dijital imzalar için kriptografik işlevsellik sağlamak için kullanılır. Sağlanan örnek kodda dijital imza oluşturmak için kullanılır.

#### S: Dijital imzanın görünümünü özelleştirebilir miyim?

 C: Evet, dijital imzanın görünümünü, görüntüdeki yolu belirterek özelleştirebilirsiniz.`SignatureAppearance` mülkiyeti`PdfFileSignature` nesne.

#### S: İmza geçerli değilse ne olur?

C: İmza geçerli değilse, doğrulama işlemi başarısız olur ve doğrulama kodu bloğundaki karşılık gelen eylemler yürütülmez.

#### S: Dijital imzalarımın güvenliğini nasıl sağlayabilirim?

C: Dijital imzalar, tasarım gereği güvenlidir ve orijinalliği ve bütünlüğü sağlamak için kriptografik teknikler kullanır. Özel anahtarınızı güvende tuttuğunuzdan ve dijital imzaları işlemek için en iyi uygulamaları takip ettiğinizden emin olun.

#### S: Bir PDF'ye birden fazla dijital imza ekleyebilir miyim?

 Y: Evet, aşağıdakileri kullanarak bir PDF dosyasına birden çok dijital imza ekleyebilirsiniz:`PdfFileSignature` nesnenin`Sign` veya`Certify` yöntemler. Her imzanın kendi görünümü ve konfigürasyonu olacaktır.