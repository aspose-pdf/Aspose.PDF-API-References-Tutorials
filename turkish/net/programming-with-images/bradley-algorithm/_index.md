---
title: Bradley Algoritması
linktitle: Bradley Algoritması
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile Bradley algoritmasını kullanarak bir PDF belgesini dönüştürün.
type: docs
weight: 30
url: /tr/net/programming-with-images/bradley-algorithm/
---

Bu adım adım kılavuz, Bradley Algoritmasının Aspose.PDF for .NET ile nasıl kullanılacağını açıklar. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## 3. Adım: Çıktı dosyalarını tanımlayın

 Ortaya çıkan görüntü ve ikili görüntü için çıktı dosya adlarını tanımlayın. Yer değiştirmek`"resultant_out.tif"` Ve`"37116-bin_out.tif"` çıktı dosyaları için istenen adlarla.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## 4. Adım: Çözünürlük nesnesini oluşturun

 Oluşturmak`Resolution` TIFF görüntüsünün çözünürlüğünü ayarlamak için nesne. Bu örnekte, 300 dpi çözünürlük kullanıyoruz.

```csharp
Resolution resolution = new Resolution(300);
```

## 5. Adım: TiffSettings nesnesini oluşturun

 Oluşturmak`TiffSettings` çıktı TIFF dosyası için ayarları belirtmek üzere nesne. Bu örnekte, LZW sıkıştırması ve piksel başına 1 bit (1 bpp biçimi) renk derinliği kullanıyoruz.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## 6. Adım: TIFF cihazını oluşturun

 kullanarak bir TIFF aygıtı oluşturun.`TiffDevice` çözünürlüğü ve TIFF ayarlarını belirten nesne.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## 7. Adım: İlgili sayfayı dönüştürün ve resmi kaydedin

 Kullan`Process` TIFF aygıtının PDF belgesinin belirli bir sayfasını dönüştürme ve görüntüyü bir TIFF dosyasına kaydetme yöntemi. Dosya çıkış yolunu belirtin.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## 8. Adım: Bradley algoritmasını kullanarak görüntüyü ikili hale getirin

 Kullan`BinarizeBradley`Bradley algoritmasını kullanarak görüntüyü ikili hale getirmek için TIFF cihazının yöntemi. Bu yöntem, orijinal görüntünün bir giriş akışını ve ikili görüntü için bir çıkış akışını alır. Binarizasyon eşiğini belirtin (bu örnekte 0,1).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Aspose.PDF for .NET kullanan Bradley Algorithm için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Çözünürlük nesnesi oluştur
Resolution resolution = new Resolution(300);
// TiffSettings nesnesi oluştur
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// TIFF cihazı oluştur
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET ile Bradley algoritmasını kullanarak dönüştürmeyi başarıyla tamamladınız. Ortaya çıkan görselleri artık projelerinizde veya uygulamalarınızda kullanabilirsiniz.