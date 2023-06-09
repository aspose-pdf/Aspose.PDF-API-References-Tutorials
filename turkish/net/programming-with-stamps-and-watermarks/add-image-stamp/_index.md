---
title: Resim Damgası Ekle
linktitle: Resim Damgası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinize nasıl kolayca resim damgası ekleyeceğinizi öğrenin.
type: docs
weight: 20
url: /tr/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl görüntü arabelleği ekleyeceğinizi adım adım anlatacağız. PDF belgesindeki belirli bir sayfaya özel bir görüntü arabelleği eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi aç
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: çerçeve arabelleği oluşturma

Artık PDF belgesini yüklediğinize göre, eklenecek görüntü damgasını oluşturabilirsiniz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// Çerçeve arabelleğini oluştur
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

Yukarıdaki kod, "aspose-logo.jpg" dosyasını kullanarak yeni bir görüntü arabelleği oluşturur. Görüntü dosyası yolunun doğru olduğundan emin olun.

## Adım 4: Görüntü Arabelleği Özelliklerini Yapılandırma

Görüntü damgasını PDF belgesine eklemeden önce, damganın opaklık, boyut, konum vb. gibi çeşitli özelliklerini yapılandırabilirsiniz. Bunu şu şekilde yapabilirsiniz:

```csharp
// Görüntü arabelleği özelliklerini yapılandırma
imageStamp. Background = true;
imageStamp. XIndent = 100;
imageStamp. YIndent = 100;
imageStamp. Height = 300;
imageStamp. Width = 300;
imageStamp.Rotate = Rotate.on270;
imageStamp. Opacity = 0.5;
```

Bu özellikleri ihtiyaçlarınıza göre ayarlayabilirsiniz.

## 5. Adım: Görüntü damgasını PDF'ye ekleme

Artık görüntü damgası hazır olduğuna göre, onu PDF belgesinin belirli bir sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
// Çerçeve arabelleğini belirli sayfaya ekleyin
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Yukarıdaki kod, görüntü arabelleğini PDF belgesinin ilk sayfasına ekler. Gerekirse başka bir sayfa belirtebilirsiniz.

## 6. Adım: Çıktı belgesini kaydedin

Görüntü arabelleğini ekledikten sonra, değiştirilen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Add Image Stamp için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "AddImageStamp.pdf");

// Resim damgası oluştur
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
imageStamp.Background = true;
imageStamp.XIndent = 100;
imageStamp.YIndent = 100;
imageStamp.Height = 300;
imageStamp.Width = 300;
imageStamp.Rotate = Rotation.on270;
imageStamp.Opacity = 0.5;

// Belirli bir sayfaya damga ekle
pdfDocument.Pages[1].AddStamp(imageStamp);
dataDir = dataDir + "AddImageStamp_out.pdf";

// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir görüntü arabelleğinin nasıl ekleneceğini öğrendiniz. Artık bu bilgiyi kendi projelerinize uygulayarak PDF belgelerine özel resim damgaları ekleyebilirsiniz.
