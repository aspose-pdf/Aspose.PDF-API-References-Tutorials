---
title: PDF Dosyasında Zaman Damgasıyla Dijital Olarak İmzalayın
linktitle: PDF Dosyasında Zaman Damgasıyla Dijital Olarak İmzalayın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasında zaman damgalı dijital imzanın nasıl gerçekleştirileceğini öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak zaman damgalı PDF dosyasını dijital olarak imzalama sürecinde size yol göstereceğiz. Zaman damgalı dijital imza, zaman damgalı elektronik parmak izi ekleyerek belgenin gerçekliğini ve bütünlüğünü garanti eder.

## 1. Adım: Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Visual Studio'yu makinenize yükleme
- .NET için Aspose.PDF kütüphanesi kuruldu

## 2. Adım: Ortam kurulumu

Başlamak için geliştirme ortamınızı ayarlamak üzere şu adımları izleyin:

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. Gerekli ad alanlarını kod dosyanıza aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## 3. Adım: Zaman damgasıyla dijital imza

İlk adım, PDF dosyasında zaman damgasıyla dijital imzayı gerçekleştirmektir. Sağlanan kod, bu imzanın Aspose.PDF for .NET ile nasıl elde edileceğini gösterir.

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

Bu kod bir PDF dosyası yükler, PFX dosyasını (özel anahtar) ve belirtilen zaman damgası parametrelerini kullanarak zaman damgasına sahip bir dijital imza oluşturur. İmza daha sonra PDF dosyasına eklenir ve " sonekiyle kaydedilir._dışarı".

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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF dosyasında zaman damgalı dijital imzayı başarıyla gerçekleştirdiniz. Bu eğitimde imzanın oluşturulmasından güncellenmiş PDF dosyasının kaydedilmesine kadar adım adım süreç anlatılmıştır. Artık bu özelliği, PDF dosyalarınıza zaman damgası içeren dijital imzalar eklemek için kullanabilirsiniz.

### PDF dosyasında zaman damgasıyla dijital olarak imzalamaya ilişkin SSS

#### S: Zaman damgasıyla dijital olarak imzalamanın amacı nedir?

C: Zaman damgasıyla dijital imzalama, PDF dosyasına zaman damgasıyla birlikte elektronik bir parmak izi ekleyerek belgenin belirli bir zaman noktasında orijinalliğini ve bütünlüğünü garanti eder.

#### S: Bu eğitime başlamak için hangi önkoşullar gerekiyor?

C: Başlamadan önce, C# programlama dilini temel düzeyde anladığınızdan, Visual Studio'nun kurulu olduğundan ve Aspose.PDF kütüphanesinin .NET'in kurulu olduğundan emin olun.

#### S: Geliştirme ortamımı nasıl kurabilirim?

C: Visual Studio'da yeni bir C# projesi oluşturma ve gerekli ad alanlarını içe aktarma da dahil olmak üzere geliştirme ortamınızı kurmak için sağlanan adımları izleyin.

#### S: PDF'ye zaman damgası içeren dijital imzayı nasıl eklerim?

C: Sağlanan örnek kod, bir PDF dosyasının nasıl yükleneceğini, PFX dosyası (özel anahtar) ve belirtilen zaman damgası ayarlarını kullanarak zaman damgasıyla dijital imzanın nasıl oluşturulacağını, imzanın PDF dosyasına nasıl ekleneceğini ve güncellenen dosyanın nasıl kaydedileceğini gösterir.

#### S: PFX dosyası nedir ve örnekte neden kullanılıyor?

C: Bir PFX (Kişisel Değişim Formatı) dosyası özel bir anahtar ve sertifika içerir. Burada dijital imzalara yönelik şifreleme işlevselliği sağlamak için kullanılır. Yer tutucuyu PFX dosyanız ve parolanızla değiştirdiğinizden emin olun.

#### S: Zaman Damgası Ayarları nedir?

C: TimestampSettings, elektronik zaman damgasını imzaya eklemek için kullanılan zaman damgası sunucusunun ayarlarını tanımlar. Zaman damgası sunucusu URL'sini ve isteğe bağlı kullanıcı kimlik bilgilerini içerir.

#### S: Örnektekinin dışında bir zaman damgası sunucusu kullanabilir miyim?
 C: Evet, uyumlu herhangi bir zaman damgası sunucusunu kullanabilirsiniz. URL'yi değiştirin ve gerekirse uygun kullanıcı kimlik bilgilerini sağlayın.`TimestampSettings` nesne.

#### S: İmza dikdörtgenini belirtmenin amacı nedir?

C: İmza dikdörtgeni, PDF sayfasındaki dijital imza görünümünün konumunu ve boyutlarını tanımlar. İmzayı istediğiniz gibi konumlandırmak için bu değerleri ayarlayın.

#### S: İmzalama sırasında zaman damgası sunucusu kullanılamıyorsa ne olur?

C: İmzalama sırasında zaman damgası sunucusu kullanılamıyorsa işlem başarısız olabilir veya daha uzun sürebilir. Zaman damgası sunucunuzun güvenilir ve erişilebilir olduğundan emin olun.

#### S: İmzalı PDF'de zaman damgasının varlığını nasıl doğrulayabilirim?

 C: İmzalı PDF'yi sağlanan örnek kodu kullanarak inceleyebilirsiniz.`TimestampSettings` İmzalama sırasında kullandığınız bilgilerin imza detaylarında mevcut olması gerekir.

#### S: Zaman damgası içeren dijital imzalar yasal olarak bağlayıcı mıdır?

C: Zaman damgalı dijital imzalar birçok yargı alanında yasal değere sahiptir ve genellikle basit dijital imzalardan daha güvenilir kabul edilir. Belirli düzenlemeler için yargı bölgenizdeki hukuk uzmanlarına danışın.

#### S: Bir PDF'ye zaman damgası içeren birden fazla dijital imza ekleyebilir miyim?

C: Evet, imza oluşturma işlemini birden çok kez çağırarak bir PDF dosyasına zaman damgaları içeren birden çok dijital imza ekleyebilirsiniz. Her imzanın kendi zaman damgası olacaktır.