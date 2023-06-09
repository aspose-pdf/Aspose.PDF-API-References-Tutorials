---
title: Resimleri Yeniden Boyutlandır
linktitle: Resimleri Yeniden Boyutlandır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntüleri yeniden boyutlandırmak için adım adım kılavuz.
type: docs
weight: 250
url: /tr/net/programming-with-images/resize-images/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntülerin nasıl yeniden boyutlandırılacağını anlatacağız. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- Aspose.PDF kitaplığı for .NET kurulu. Aspose resmi sitesinden indirebilirsiniz.

## 1. Adım: PDF belgesini yükleme

Başlamak için, PDF belgesini yüklemek üzere aşağıdaki kodu kullanın:

```csharp
// Zamanı başlat
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// belgeyi aç
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

PDF belgenize giden doğru yolu sağladığınızdan emin olun.

## 2. Adım: Optimizasyon seçeneklerinin başlatılması

Resimleri yeniden boyutlandırmadan önce, optimizasyon seçeneklerini başlatmamız gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Optimizasyon Seçeneklerini Başlat
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// CompressImages seçeneğini etkinleştirin
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Görüntü kalitesini ayarla
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// ResizeImages seçeneğini etkinleştirin
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Maksimum çözünürlüğü ayarla
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

Optimizasyon ayarlarını ihtiyaçlarınıza göre ayarlayabilirsiniz.

## 3. Adım: PDF belgesinin optimizasyonu

Şimdi tanımladığımız optimizasyon seçeneklerini kullanarak PDF belgesini optimize edeceğiz. Aşağıdaki kodu kullanın:

```csharp
// OptimizationOptions'ı kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Güncellenen belgeyi kaydedin
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Güncellenmiş PDF belgesi için istenen yolu ve dosya adını sağladığınızdan emin olun.

### Aspose.PDF for .NET kullanarak Görüntüleri Yeniden Boyutlandırmak için örnek kaynak kodu 
```csharp
// Zamanı Başlat
var time = DateTime.Now.Ticks;
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// Optimizasyon Seçeneklerini Başlat
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// CompressImages seçeneğini ayarla
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// ImageQuality seçeneğini ayarlayın
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// ResizeImage seçeneğini ayarla
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// MaxResolution seçeneğini ayarlayın
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// OptimizationOptions kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntüleri başarıyla yeniden boyutlandırdınız. PDF dosyalarındaki görüntülerin boyutunu değiştirmek için artık bu yöntemi kendi projelerinize uygulayabilirsiniz.