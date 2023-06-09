---
title: Görüntüleri Küçült
linktitle: Görüntüleri Küçült
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntülerin boyutunu küçültmek için adım adım kılavuz.
type: docs
weight: 280
url: /tr/net/programming-with-images/shrink-images/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntülerin boyutunu nasıl küçülteceğinizi anlatacağız. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- Aspose.PDF kitaplığı for .NET kurulu. Aspose resmi sitesinden indirebilirsiniz.

## 1. Adım: PDF belgesini yükleme

Başlamak için, PDF belgesini yüklemek üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// belgeyi aç
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

PDF belgenize giden doğru yolu sağladığınızdan emin olun.

## 2. Adım: Optimizasyon seçeneklerinin başlatılması

Ardından, görüntülerin boyutunu küçültmek için optimizasyon seçeneklerini başlatacağız. Aşağıdaki kodu kullanın:

```csharp
// Optimizasyon Seçeneklerini Başlat
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// CompressImages seçeneğini etkinleştirin
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Görüntü kalitesini ayarla
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

Optimizasyon ayarlarını ihtiyaçlarınıza göre ayarlayabilirsiniz.

## 3. Adım: PDF belgesinin optimizasyonu

Şimdi resimlerin boyutunu küçülterek PDF belgesini optimize edeceğiz. Aşağıdaki kodu kullanın:

```csharp
// OptimizationOptions'ı kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// Güncellenen belgeyi kaydedin
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

Güncellenmiş PDF belgesi için istenen yolu ve dosya adını sağladığınızdan emin olun.

### Aspose.PDF for .NET kullanarak Görüntüleri Küçültmek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Optimizasyon Seçeneklerini Başlat
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// CompressImages seçeneğini ayarla
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// ImageQuality seçeneğini ayarlayın
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// OptimizationOptions kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntülerin boyutunu başarıyla küçülttünüz. Artık PDF dosyalarındaki görüntülerin boyutunu optimize etmek için bu yöntemi kendi projelerinize uygulayabilirsiniz.