---
title: Resim Yerleşimleri
linktitle: Resim Yerleşimleri
second_title: Aspose.PDF for .NET API Referansı
description: Resimleri bir PDF belgesine yerleştirmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-images/image-placements/
---

Bu eğitimde, PDF belgeleriyle çalışmak ve görüntüler üzerinde işlemler gerçekleştirmek için Aspose.PDF kitaplığını .NET için kullanacağız. Bir PDF belgesi yükleyeceğiz, görüntü yerleşim bilgilerini çıkaracağız ve boyutları görünür halde görüntüleri alacağız.

## 1. Adım: Ortamı ayarlama
Başlamadan önce, geliştirme ortamınızı aşağıdakilerle kurduğunuzdan emin olun:
- Aspose.PDF for .NET makinenizde yüklü.
- AC# projesi kullanıma hazır.

## 2. Adım: PDF belgesini yükleme
Başlamak için, işlemek istediğimiz PDF belgesini yüklememiz gerekiyor. PDF belgesini içeren dizine giden doğru yola sahip olduğunuzdan emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Kaynak PDF belgesini yükleyin
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyasını içeren belge dizininizin gerçek yolu ile.

## 3. Adım: Görüntülerden yerleşim bilgilerini çıkarın
 Artık PDF belgesini yüklediğimize göre, yerleşim bilgilerini görüntülerden çıkarabiliriz. Kullanacağız`ImagePlacementAbsorber`belgenin ilk sayfasından görüntü konumlarını almak için.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// İlk sayfanın içeriğini yükleyin
doc.Pages[1].Accept(abs);
```

Artık belgenin ilk sayfasından görüntü yerleştirme bilgilerini çıkardık.

## 4. Adım: Görünür boyutlara sahip görüntüleri alma
Şimdi, daha önce çıkardığımız yerleştirme bilgilerinden görselleri görünür boyutlarıyla alacağız.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Görüntü özelliklerini al
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Görüntüyü görünür boyutlarla alın
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Görüntüyü kaynaklardan alın
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Gerçek boyutlara sahip bir görüntü oluşturun
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

Bu döngüde, her görüntünün genişlik, yükseklik, sol alt köşenin X ve Y koordinatları ve yatay ve dikey çözünürlük gibi özelliklerini alırız. Ardından, yerleştirme bilgilerini kullanarak her görüntüyü görünür boyutlarıyla alırız.

### Aspose.PDF for .NET kullanan Görüntü Yerleşimleri için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Kaynak PDF belgesini yükleyin
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// İlk sayfanın içeriğini yükleyin
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Görüntü özelliklerini al
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Görünür boyutlara sahip görüntüyü al
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Kaynaklardan görüntü al
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Gerçek boyutlarla bit eşlem oluştur
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Çözüm
Tebrikler! Artık bir PDF belgesinde görüntü yerleşimleri gerçekleştirmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrendiniz. Bir PDF belgesi yüklemenizi, görüntülerden yerleşim bilgilerini çıkarmanızı ve boyutları görünür halde görüntüleri almanızı sağlayan C# kaynak kodunu açıkladık. Diğer birçok özelliğini keşfetmek için Aspose.PDF ile daha fazlasını denemekten çekinmeyin.