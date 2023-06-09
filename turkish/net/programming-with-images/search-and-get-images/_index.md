---
title: Görüntüleri Arayın ve Alın
linktitle: Görüntüleri Arayın ve Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntüleri aramak ve almak için adım adım kılavuz.
type: docs
weight: 260
url: /tr/net/programming-with-images/search-and-get-images/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde nasıl resim arayacağınızı ve görüntüleri alacağınızı göstereceğiz. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

PDF belgenize giden doğru yolu sağladığınızdan emin olun.

## 2. Adım: Görüntü Konumlarını Arama

PDF belgesindeki görüntülerin konumlarını aramak için aşağıdaki kodu kullanın:

```csharp
// Görüntü konumlarını aramak için bir ImagePlacementAbsorber nesnesi oluşturun
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Belgenin tüm sayfaları için emiciyi kabul edin
doc.Pages.Accept(abs);
```

Bu, soğurucudaki görüntülerin konumlarını toplayacaktır.

## 3. Adım: Görüntü konumlarına göz atın ve görüntüleri ve özelliklerini alın

Ardından, toplanan görüntü konumlarına göz atacağız ve görüntüleri ve özelliklerini alacağız. Aşağıdaki kodu kullanın:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //ImagePlacement nesnesini kullanarak görüntüyü alın
     XImage image = imagePlacement.Image;

     // Görüntü konumu özelliklerini görüntüleyin
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Bu, tüm görüntü konumlarına göz atacak, eşleşen görüntüleri alacak ve özelliklerini gösterecektir.

### Aspose.PDF for .NET kullanarak Search And Get Images için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Görüntü yerleştirme araması yapmak için ImagePlacementAbsorber nesnesi oluşturun
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Tüm sayfalar için emiciyi kabul edin
doc.Pages.Accept(abs);
// Tüm ImagePlacement'lar arasında geçiş yapın, image ve ImagePlacement Özelliklerini alın
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// ImagePlacement nesnesini kullanarak görüntüyü alın
	XImage image = imagePlacement.Image;
	// Tüm yerleşimler için resim yerleşimi özelliklerini göster
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki görselleri başarıyla aradınız ve elde ettiniz. Artık görüntüleri ayıklamak ve özelliklerini PDF dosyalarından almak için bu yöntemi kendi projelerinize uygulayabilirsiniz.