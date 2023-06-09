---
title: CGM'den PDF'ye dönüştürücü
linktitle: CGM'den PDF'ye dönüştürücü
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak CGM dosyalarını kolayca PDF'e dönüştürün.
type: docs
weight: 20
url: /tr/net/document-conversion/cgm-to-pdf/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak CGM'yi PDF'ye dönüştürmek için adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kolayca takip etmenize yardımcı olacak adım adım yönergeler sağlayacağız.

## giriiş

Bir CGM dosyasını PDF'ye dönüştürmek, teknik çizimlerinizi evrensel olarak paylaşmanıza ve görüntülemenize olanak tanır. Aspose.PDF for .NET ile bu dönüştürmeyi kolayca gerçekleştirebilir ve yüksek kaliteli PDF dosyaları elde edebilirsiniz.

## Ortam kurulumu

Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET ile çalışacak şekilde yapılandırdığınızdan emin olun. Aşağıdaki adımları takip et:

1. Visual Studio'yu veya C# geliştirmeyle uyumlu başka bir IDE'yi kurun.
2. Yeni bir C# projesi oluşturun.
3. Gerekli bağımlılıkları eklemek için Aspose.PDF for .NET paketini NuGet aracılığıyla kurun.

## CGM dosyasını PDF'ye dönüştürün

Bir CGM dosyasını PDF'ye dönüştürmek için şu adımları izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// CGMLoadOption kullanarak bir LoadOption nesnesi oluşturun
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Belge nesnesi örneği oluşturma
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Ortaya çıkan PDF belgesini kaydedin
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

 Yukarıdaki kodda, değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` dönüştürülecek CGM dosyanızın bulunduğu dizinin gerçek yolu ile. Bu kod, CGM dosyasını kullanarak yükler.`CgmLoadOptions` class'ı kullanarak bir PDF belgesi oluşturur.`Document` nesne. Son olarak, ortaya çıkan PDF belgesi kaydedilir.

### Aspose.PDF for .NET kullanarak CGM'den PDF'e dönüştürme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// CGMLoadOption kullanarak LoadOption nesnesini oluşturun
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Belge nesnesini örneklendir
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Ortaya çıkan PDF belgesini kaydedin
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## Çözüm

Tebrikler! Artık bir CGM dosyasını Aspose.PDF for .NET kullanarak PDF'ye nasıl dönüştüreceğinizi biliyorsunuz. CGM yükleme seçeneklerini başlatmaktan elde edilen PDF belgesini kaydetmeye kadar sürecin her adımını inceledik. Bu işlevi kendi projelerinize entegre etmek için sağlanan kod örneklerini kullanın. Aspose.PDF for .NET ile deneyler yapın ve PDF dosyalarını işlemek için sunduğu genişletilmiş olasılıkları keşfedin.
