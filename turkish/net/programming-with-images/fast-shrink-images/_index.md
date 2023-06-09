---
title: Görüntüleri Hızlı Küçült
linktitle: Görüntüleri Hızlı Küçült
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF dosyasındaki görüntülerin boyutunu hızla azaltın.
type: docs
weight: 130
url: /tr/net/programming-with-images/fast-shrink-images/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki görüntülerin boyutunu nasıl hızlı bir şekilde küçültebileceğinizi adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Süreyi sıfırlayın

Başlamadan önce, sıkıştırma performansını ölçmek için süreyi başlatacağız. Başlangıç zamanını kaydetmek için aşağıdaki kodu ekleyin:

```csharp
var time = DateTime.Now.Ticks;
```

## 2. Adım: Belge dizinini tanımlayın

 Doğru belge dizinini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## 4. Adım: Optimizasyon seçeneklerini başlatın

 Bu adımda, görüntü sıkıştırma için optimizasyon seçeneklerini başlatacağız. Bir örneğini oluştur`OptimizationOptions` ve uygun seçenekleri ayarlayın. Bu örnekte, görüntü sıkıştırmayı etkinleştiriyoruz, görüntü kalitesini 75 olarak ayarlıyoruz ve hızlı sıkıştırma sürümünü kullanıyoruz.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## 5. Adım: PDF belgesini optimize edin

 Bu adımda, daha önce tanımlanan optimizasyon seçeneklerini kullanarak PDF belgesini optimize edeceğiz. Ara`OptimizeResources` yöntemi`pdfDocument` nesne ve optimizasyon seçeneklerini geçin.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 6. Adım: Güncellenmiş PDF belgesini kaydedin

 Güncellenmiş PDF belgesini kullanarak kaydedin.`Save` yöntemi`pdfDocument` nesne. PDF dosyası için çıktı yolunu belirtin.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Görüntüleri Hızlı Küçültmek için örnek kaynak kodu 
```csharp
// Zamanı Başlat
var time = DateTime.Now.Ticks;
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Optimizasyon Seçeneklerini Başlat
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// CompressImages seçeneğini ayarla
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// ImageQuality seçeneğini ayarlayın
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// Görüntü Sıkıştırma Sürümünü hızlı olarak ayarlayın
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// OptimizationOptions kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF'deki görüntülerin boyutunu hızla küçülttünüz. Optimize edilmiş PDF dosyası belirtilen dizine kaydedilir. Artık daha verimli depolama veya paylaşım ihtiyaçları için bu PDF dosyasını küçültülmüş resimlerle kullanabilirsiniz.