---
title: PDF Dosyasında Zaman Damgasıyla Dijital İmza
linktitle: PDF Dosyasında Zaman Damgasıyla Dijital İmza
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasında zaman damgalı dijital imzanın nasıl oluşturulacağını öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasında zaman damgasıyla dijital olarak imza atma sürecini adım adım anlatacağız. Zaman damgalı dijital imza, zaman damgalı elektronik bir parmak izi ekleyerek belgenin gerçekliğini ve bütünlüğünü garanti eder.

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
```

## Adım 3: Zaman damgalı dijital imza

İlk adım, PDF dosyasında zaman damgalı dijital imzayı gerçekleştirmektir. Sağlanan kod, .NET için Aspose.PDF ile bu imzanın nasıl elde edileceğini gösterir.

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

Bu kod bir PDF dosyasını yükler, PFX dosyası (özel anahtar) ve belirtilen zaman damgası parametrelerini kullanarak zaman damgası olan bir dijital imza oluşturur. İmza daha sonra PDF dosyasına eklenir ve " son ekiyle kaydedilir_dışarı".

### .NET için Aspose.PDF kullanarak Zaman Damgasıyla Dijital İmzalama için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyasında zaman damgalı dijital imzayı başarıyla gerçekleştirdiniz. Bu eğitim, imzanın oluşturulmasından güncellenmiş PDF dosyasının kaydedilmesine kadar olan adım adım süreci kapsıyordu. Artık bu özelliği kullanarak PDF dosyalarınıza zaman damgalı dijital imzalar ekleyebilirsiniz.

### PDF dosyasında zaman damgasıyla dijital imzalamaya ilişkin SSS

#### S: Zaman damgası ile dijital imzalama yapmanın amacı nedir?

A: Zaman damgasıyla dijital olarak imzalamak, PDF dosyasına zaman damgalı elektronik bir parmak izi ekleyerek belgenin belirli bir zamandaki gerçekliğini ve bütünlüğünü garanti altına alır.

#### S: Bu eğitimi başlatmak için hangi ön koşullara ihtiyaç var?

C: Başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olduğunuzdan, Visual Studio'nun ve .NET için Aspose.PDF kütüphanesinin yüklü olduğundan emin olun.

#### S: Geliştirme ortamımı nasıl kurabilirim?

A: Visual Studio'da yeni bir C# projesi oluşturmak ve gerekli ad alanlarını içe aktarmak da dahil olmak üzere geliştirme ortamınızı kurmak için verilen adımları izleyin.

#### S: PDF'e zaman damgalı dijital imza nasıl eklerim?

A: Sağlanan örnek kod, bir PDF dosyasının nasıl yükleneceğini, PFX dosyası (özel anahtar) ve belirtilen zaman damgası ayarlarını kullanarak zaman damgalı bir dijital imzanın nasıl oluşturulacağını, imzanın PDF dosyasına nasıl ekleneceğini ve güncellenmiş dosyanın nasıl kaydedileceğini göstermektedir.

#### S: PFX dosyası nedir ve örnekte neden kullanılmıştır?

A: Bir PFX (Kişisel Değişim Biçimi) dosyası özel bir anahtar ve sertifika içerir. Burada dijital imzalar için kriptografik işlevsellik sağlamak için kullanılır. Yer tutucuyu PFX dosyanız ve parolanızla değiştirdiğinizden emin olun.

#### S: TimestampSettings nedir?

A: TimestampSettings, elektronik zaman damgasını imzaya eklemek için kullanılan zaman damgası sunucusunun ayarlarını tanımlar. Zaman damgası sunucusu URL'sini ve isteğe bağlı kullanıcı kimlik bilgilerini içerir.

#### S: Örnekteki zaman damgası sunucusunun dışında bir zaman damgası sunucusu kullanabilir miyim?
 A: Evet, herhangi bir uyumlu zaman damgası sunucusunu kullanabilirsiniz. URL'yi değiştirin ve gerekirse uygun kullanıcı kimlik bilgilerini sağlayın.`TimestampSettings` nesne.

#### S: İmza dikdörtgenini belirtmenin amacı nedir?

A: İmza dikdörtgeni, dijital imzanın PDF sayfasındaki görünümünün konumunu ve boyutlarını tanımlar. İmzayı istediğiniz gibi konumlandırmak için bu değerleri ayarlayın.

#### S: İmzalama sırasında zaman damgası sunucusuna ulaşılamıyorsa ne olur?

A: İmzalama sırasında zaman damgası sunucusu kullanılamıyorsa, işlem başarısız olabilir veya daha uzun sürebilir. Zaman damgası sunucunuzun güvenilir ve erişilebilir olduğundan emin olun.

#### S: İmzalanmış PDF'de zaman damgasının varlığını nasıl doğrulayabilirim?

 A: İmzalanmış PDF'yi verilen örnek kodu kullanarak inceleyebilirsiniz.`TimestampSettings` İmzalama sırasında kullandığınız bilgilerin imza detaylarında mevcut olması gerekmektedir.

#### S: Zaman damgalı dijital imzalar hukuken bağlayıcı mıdır?

A: Zaman damgalı dijital imzalar birçok yargı alanında yasal değere sahiptir ve genellikle basit dijital imzalardan daha güvenilir kabul edilir. Belirli düzenlemeler için yargı alanınızdaki hukuk uzmanlarına danışın.

#### S: Bir PDF'e zaman damgalı birden fazla dijital imza ekleyebilir miyim?

C: Evet, imza oluşturma sürecini birden fazla kez çağırarak bir PDF dosyasına zaman damgalı birden fazla dijital imza ekleyebilirsiniz. Her imzanın kendi zaman damgası olacaktır.