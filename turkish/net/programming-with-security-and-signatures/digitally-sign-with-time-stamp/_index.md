---
title: Zaman Damgasıyla Dijital Olarak İmzalayın
linktitle: Zaman Damgasıyla Dijital Olarak İmzalayın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasında zaman damgalı bir dijital imzayı nasıl gerçekleştireceğinizi öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını zaman damgasıyla dijital olarak imzalama sürecinde size yol göstereceğiz. Zaman damgalı dijital imza, zaman damgalı bir elektronik parmak izi ekleyerek belgenin gerçekliğini ve bütünlüğünü garanti eder.

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
```

## 3. Adım: Zaman damgalı dijital imza

İlk adım, PDF dosyasında zaman damgalı dijital imzayı gerçekleştirmektir. Sağlanan kod, Aspose.PDF for .NET ile bu imzanın nasıl elde edileceğini gösterir.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Bu kod bir PDF dosyası yükler, bir PFX dosyası (özel anahtar) ve belirtilen zaman damgası parametrelerini kullanarak zaman damgalı bir dijital imza oluşturur. İmza daha sonra PDF dosyasına eklenir ve " soneki ile kaydedilir._dışarı".

### Aspose.PDF for .NET kullanarak Digitally Sign With Time Stamp için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Kullanıcı/Şifre atlanabilir
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//Üç imza türünden herhangi birini oluşturun
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Çıktı PDF dosyasını kaydet
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyasında zaman damgalı bir dijital imzayı başarıyla gerçekleştirdiniz. Bu eğitim, imza oluşturmaktan güncellenmiş PDF dosyasını kaydetmeye kadar adım adım süreci kapsıyordu. Artık PDF dosyalarınıza zaman damgalı dijital imzalar eklemek için bu özelliği kullanabilirsiniz.