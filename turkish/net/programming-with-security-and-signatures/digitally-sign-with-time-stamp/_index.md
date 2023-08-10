---
title: PDF Dosyasında Zaman Damgasıyla Dijital Olarak İmzalayın
linktitle: PDF Dosyasında Zaman Damgasıyla Dijital Olarak İmzalayın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasında zaman damgalı bir dijital imzayı nasıl gerçekleştireceğinizi öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak zaman damgalı PDF dosyasında dijital olarak imzalama sürecinde size yol göstereceğiz. Zaman damgalı dijital imza, zaman damgalı bir elektronik parmak izi ekleyerek belgenin orijinalliğini ve bütünlüğünü garanti eder.

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
		// Üç imza türünden herhangi birini oluşturun
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Çıktı PDF dosyasını kaydet
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyasında zaman damgalı bir dijital imzayı başarıyla gerçekleştirdiniz. Bu eğitim, imza oluşturmaktan güncellenmiş PDF dosyasını kaydetmeye kadar adım adım süreci kapsıyordu. Artık PDF dosyalarınıza zaman damgalı dijital imzalar eklemek için bu özelliği kullanabilirsiniz.

### PDF dosyasında zaman damgasıyla dijital olarak imzalamayla ilgili SSS

#### S: Zaman damgasıyla dijital olarak imzalamanın amacı nedir?

Y: Zaman damgasıyla dijital olarak imzalama, bir PDF dosyasına zaman damgasıyla birlikte elektronik bir parmak izi ekleyerek, belgenin belirli bir zamanda orijinalliğini ve bütünlüğünü sağlar.

#### S: Bu eğitime başlamak için hangi ön koşullar gerekiyor?

C: Başlamadan önce, C# programlama dilini temel düzeyde anladığınızdan, Visual Studio'nun kurulu olduğundan ve Aspose.PDF kitaplığının .NET için kurulu olduğundan emin olun.

#### S: Geliştirme ortamımı nasıl kurabilirim?

Y: Geliştirme ortamınızı ayarlamak için, Visual Studio'da yeni bir C# projesi oluşturmak ve gerekli ad alanlarını içe aktarmak dahil olmak üzere sağlanan adımları izleyin.

#### S: Zaman damgalı bir dijital imzayı PDF'ye nasıl eklerim?

Y: Sağlanan örnek kod, bir PDF dosyasının nasıl yükleneceğini, bir PFX dosyası (özel anahtar) ve belirtilen zaman damgası ayarlarını kullanarak bir zaman damgasıyla dijital imzanın nasıl oluşturulacağını, imzanın PDF dosyasına nasıl ekleneceğini ve güncellenmiş dosyanın nasıl kaydedileceğini gösterir.

#### S: PFX dosyası nedir ve örnekte neden kullanılmıştır?

C: Bir PFX (Kişisel Değişim Biçimi) dosyası, özel bir anahtar ve sertifika içerir. Burada dijital imzalar için kriptografik işlevsellik sağlamak için kullanılır. Yer tutucuyu PFX dosyanız ve parolanızla değiştirdiğinizden emin olun.

#### S: Zaman Damgası Ayarları nedir?

A: TimestampSettings, elektronik zaman damgasını imzaya eklemek için kullanılan zaman damgası sunucusunun ayarlarını tanımlar. Zaman damgası sunucusu URL'sini ve isteğe bağlı kullanıcı kimlik bilgilerini içerir.

#### S: Örnektekinden farklı bir zaman damgası sunucusu kullanabilir miyim?
 C: Evet, herhangi bir uyumlu zaman damgası sunucusunu kullanabilirsiniz. URL'yi değiştirin ve gerekirse, ilgili kullanıcı kimlik bilgilerini`TimestampSettings` nesne.

#### S: İmza dikdörtgenini belirtmenin amacı nedir?

C: İmza dikdörtgeni, PDF sayfasındaki dijital imza görünümünün konumunu ve boyutlarını tanımlar. İmzayı istediğiniz gibi konumlandırmak için bu değerleri ayarlayın.

#### S: İmzalama sırasında zaman damgası sunucusu kullanılamıyorsa ne olur?

Y: İmzalama sırasında zaman damgası sunucusu kullanılamıyorsa, işlem başarısız olabilir veya daha uzun sürebilir. Zaman damgası sunucunuzun güvenilir ve erişilebilir olduğundan emin olun.

#### S: İmzalı PDF'de bir zaman damgasının varlığını nasıl doğrulayabilirim?

 A: Sağlanan örnek kodu kullanarak imzalanmış PDF'yi inceleyebilirsiniz. bu`TimestampSettings` imzalama sırasında kullandığınız imza detaylarında mevcut olmalıdır.

#### S: Zaman damgalı dijital imzalar yasal olarak bağlayıcı mı?

C: Zaman damgalı dijital imzalar, birçok yargı alanında yasal değere sahiptir ve genellikle basit dijital imzalardan daha güvenilir kabul edilir. Belirli düzenlemeler için yargı alanınızdaki hukuk uzmanlarına danışın.

#### S: PDF'ye zaman damgalı birden çok dijital imza ekleyebilir miyim?

C: Evet, imza oluşturma sürecini birden çok kez çağırarak bir PDF dosyasına zaman damgalı birden çok dijital imza ekleyebilirsiniz. Her imzanın kendi zaman damgası olacaktır.