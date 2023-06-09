---
title: Görüntüleri Çıkar
linktitle: Görüntüleri Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF dosyasından görüntüleri kolayca çıkarın.
type: docs
weight: 120
url: /tr/net/programming-with-images/extract-images/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak bir PDF dosyasından görüntüleri nasıl çıkaracağınızı adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF belgesini açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## 3. Adım: Belirli bir görüntüyü çıkarın

 Bu adımda, belirli bir sayfadan belirli bir görüntüyü çıkaracağız. Kullan`Images` sayfanın toplanması`s `İstenen görüntüye erişmek için Resources` nesnesi. Aşağıdaki örnekte ilk sayfadan indeksi 1 olan görseli çıkarıyoruz.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## 4. Adım: Ayıklanan görüntüyü kaydedin

 Ayıklanan görüntüyü kullanarak bir dosyaya kaydedin.`Save` yöntemi`xImage`nesne. Çıktı yolunu ve görüntü formatını belirtin (bu örnekte JPEG formatını kullanıyoruz).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## 5. Adım: Güncellenmiş PDF dosyasını kaydedin

 Güncellenmiş PDF dosyasını kullanarak kaydedin.`Save` yöntemi`pdfDocument` nesne. PDF dosyası için çıktı yolunu belirtin.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Görüntüleri Çıkarmak için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Belirli bir görüntüyü ayıklayın
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Çıktı görüntüsünü kaydet
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Güncellenmiş PDF dosyasını kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF'den görüntüleri başarıyla çıkardınız. Ayıklanan görüntü belirtilen dizine kaydedilir ve güncellenen PDF dosyası da kaydedilir. Artık bu dosyaları özel ihtiyaçlarınız için kullanabilirsiniz.