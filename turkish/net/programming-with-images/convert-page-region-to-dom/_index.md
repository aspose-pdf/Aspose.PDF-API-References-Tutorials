---
title: Sayfa Bölgesini DOM'a Dönüştür
linktitle: Sayfa Bölgesini DOM'a Dönüştür
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF sayfasının belirli bir bölgesini kolayca Belge Nesne Modeline (DOM) dönüştürün.
type: docs
weight: 80
url: /tr/net/programming-with-images/convert-page-region-to-dom/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak bir sayfanın belirli bir bölgesinin Belge Nesne Modeline (DOM) nasıl dönüştürüleceğini adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## 3. Adım: Sayfa Bölgesi Dikdörtgenini Alın

 Bu adımda, sayfanın DOM'a dönüştürmek istediğimiz belirli bölgesini temsil eden bir dikdörtgen tanımlayacağız. Kullan`Aspose.Pdf.Rectangle` dikdörtgenin koordinatlarını tanımlayan sınıf.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## 4. Adım: Sayfanın kırpma alanını tanımlayın

 Kullan`CropBox` mülkiyeti`Page` sayfanın kırpma kutusunu istenen bölge dikdörtgenine ayarlamak için nesne.

```csharp
document.Pages[1].CropBox = pageRect;
```

## 5. Adım: Kırpılan PDF belgesini bir akışa kaydedin

 Bu adımda, kırpılmış PDF belgesini kullanarak bir akışa kaydedeceğiz.`MemoryStream` sınıf.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## 6. Adım: Kırpılmış PDF belgesini açın ve onu bir görüntüye dönüştürün

 kullanarak kırpılmış PDF belgesini açın.`Document` sınıflandırın ve bir görüntüye dönüştürün. 300 dpi çözünürlük kullanacağız.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## 7. Adım: Belirli bir sayfayı bir resme dönüştürün

 kullanarak belirli sayfayı bir görüntüye dönüştürün.`Process` yöntemi`pngDevice` nesne. Görüntü çıkış yolunu belirtin.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Aspose.PDF for .NET kullanarak Sayfa Bölgesini DOM'a Dönüştürmek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document document = new Document( dataDir + "AddImage.pdf");
// Belirli sayfa bölgesinin dikdörtgenini alın
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
//CropBox değerini istenen sayfa bölgesinin dikdörtgenine göre ayarlayın
document.Pages[1].CropBox = pageRect;
// Kırpılan belgeyi akışa kaydet
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Kırpılmış PDF belgesini açın ve görüntüye dönüştürün
document = new Document(ms);
// Çözünürlük nesnesi oluştur
Resolution resolution = new Resolution(300);
// Belirtilen özniteliklerle PNG cihazı oluştur
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir sayfanın belirli bir bölgesini başarıyla Belge Nesne Modeline (DOM) dönüştürdünüz. Ortaya çıkan görüntü belirtilen dizine kaydedilir. Artık projelerinizde veya uygulamalarınızda bu imajı kullanabilirsiniz.