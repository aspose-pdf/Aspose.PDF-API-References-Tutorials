---
title: Dosya Boyutunu Optimize Edin
linktitle: Dosya Boyutunu Optimize Edin
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzu kullanarak Aspose.PDF for .NET ile PDF belgelerinizin dosya boyutunu nasıl optimize edeceğinizi öğrenin.
type: docs
weight: 250
url: /tr/net/programming-with-document/optimizefilesize/
---
Aspose.PDF for .NET, geliştiricilerin kendi .NET uygulamalarında PDF dosyaları oluşturmasına, düzenlemesine ve değiştirmesine olanak sağlayan bir kitaplıktır. Bu kitaplığın en kullanışlı özelliklerinden biri, bir PDF belgesinin dosya boyutunu optimize etme yeteneğidir. Bu yazıda, Aspose.PDF for .NET kullanarak bir PDF belgesinin dosya boyutunu optimize etmek için adım adım bir kılavuz sağlayacağız.

## 1. Adım: PDF Belgesini Yükleyin

 Bir PDF belgesinin dosya boyutunu optimize etmenin ilk adımı, belgeyi uygulamanıza yüklemektir. Bunu kullanarak yapabilirsiniz`Document`Aspose.PDF for .NET kitaplığı tarafından sağlanan sınıf. İşte bir PDF belgesinin nasıl yükleneceği ile ilgili bir örnek:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 değiştirdiğinizden emin olun`YOUR DOCUMENT DIRECTORY` PDF belgenizi içeren dizinin yolu ile.

## 2. Adım: Optimizasyon Seçeneklerini Ayarlayın

 PDF belgesini yükledikten sonra, belgenin hangi bölümlerini optimize etmek istediğinizi belirtmek için optimizasyon seçeneklerini ayarlayabilirsiniz. bu`OptimizationOptions` Aspose.PDF for .NET kitaplığı tarafından sağlanan sınıf, PDF belgesinin dosya boyutunu optimize etmek için çeşitli seçenekler belirtmenize izin verir. İşte bazı optimizasyon seçeneklerinin nasıl ayarlanacağına dair bir örnek:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

Bu örnekte, aşağıdaki seçenekleri ayarlıyoruz:
- `LinkDuplcateStreams`: Bu seçenek, PDF belgesindeki yinelenen akışların kaldırılmasını sağlar ve bu da dosya boyutunun küçültülmesine yardımcı olabilir.
- `RemoveUnusedObjects`: Bu seçenek, PDF belgesindeki kullanılmayan nesnelerin kaldırılmasını sağlar ve bu da dosya boyutunun küçültülmesine yardımcı olabilir.
- `RemoveUnusedStreams`Bu seçenek, dosya boyutunu daha da azaltabilen PDF belgesindeki kullanılmayan akışların kaldırılmasını sağlar.
- `CompressImages`: Bu seçenek, dosya boyutunu önemli ölçüde azaltabilen PDF belgesindeki görüntülerin sıkıştırılmasını sağlar.
- `ImageQuality`: Bu seçenek, sıkıştırılmış görüntülerin kalitesini ayarlar. Daha düşük bir kalite ayarı daha küçük bir dosya boyutuna neden olur, ancak daha düşük kaliteli bir görüntüye de neden olabilir.

## 4. Adım: PDF Belgesini Optimize Edin

 Artık optimizasyon seçeneklerini ayarladığınıza göre, PDF belgesini kullanarak optimize edebilirsiniz.`OptimizeResources` tarafından sağlanan yöntem`Document` sınıf. İşte PDF belgesinin nasıl optimize edileceğine dair bir örnek:

```csharp
// Kullanılmayan nesneleri kaldırarak dosya boyutunu optimize edin
pdfDocument.OptimizeResources(optimizationOptions);
```

## 5. Adım: Optimize Edilmiş PDF Belgesini Kaydedin

PDF belgesini optimize ettikten sonra, optimize edilmiş sürümü yeni bir dosyaya kaydedebilirsiniz. Optimize edilmiş PDF belgesinin nasıl kaydedileceğine ilişkin bir örnek aşağıda verilmiştir:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Dosya Boyutunu Optimize Etme için Örnek Kaynak Kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
// Kullanılmayan nesneleri kaldırarak dosya boyutunu optimize edin
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
```
