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

### SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinden görüntü yerleştirme bilgilerini çıkarmanın amacı nedir?

C: Görüntü yerleştirme bilgilerinin çıkarılması, bir PDF belgesindeki görüntülerin konumunu, boyutlarını ve çözünürlüğünü almanıza olanak tanır. Bu bilgi, hassas görüntü manipülasyonu ve analizi için gereklidir.

#### S: Aspose.PDF for .NET, bir PDF belgesinden görüntü yerleştirme bilgilerinin çıkarılmasını nasıl kolaylaştırır?

 C: Aspose.PDF for .NET şunları sağlar:`ImagePlacementAbsorber`bir PDF belgesinden görüntü yerleştirme ayrıntılarını almak için kullanılabilen sınıf. Sağlanan kod, görüntü yerleştirme bilgilerini almak için bu sınıfın nasıl kullanılacağını gösterir.

#### S: Görüntü yerleştirme bilgileri gerçek dünya senaryolarında ne için kullanılabilir?

Y: Görüntü yerleştirme bilgileri, doğru görüntü hizalamasının sağlanması, görüntü boyutlarının hesaplanması, görüntü kalitesinin doğrulanması ve bir PDF belgesinde görüntü kullanımına ilişkin raporlar oluşturulması gibi görevler için değerlidir.

#### S: Kod örneği, görüntü yerleştirme bilgilerinin doğru şekilde çıkarılmasını nasıl sağlıyor?

 C: Kod örneği,`ImagePlacementAbsorber` belirtilen bir sayfanın içeriğinde gezinmek, görüntü yerleşimlerini belirlemek ve bunların genişlik, yükseklik, koordinatlar ve çözünürlük gibi niteliklerini almak için sınıf.

#### S: Kod, birden çok sayfa veya belgedeki görüntüleri işlemek için genişletilebilir mi?

C: Evet, görüntü yerleştirme bilgilerini çıkarmak ve görüntüyle ilgili görevleri gerçekleştirmek için birden çok sayfa veya belge yinelenerek kod genişletilebilir.

#### S: Kod, yerleştirme bilgilerine göre görselleri görünür boyutlarıyla nasıl alır?

C: Kod örneği, kaynaklardan görüntü verilerini çıkarır, gerçek boyutlara sahip bir bitmap görüntüsü oluşturur ve genişlik, yükseklik, koordinatlar ve çözünürlük gibi özellikler sağlar.

#### S: Bu yaklaşım, çok sayıda resim içeren büyük PDF belgeleri için verimli midir?

C: Evet, Aspose.PDF for .NET, performans ve kaynak kullanımı için optimize edilmiştir. Büyük PDF belgelerinden bile görüntü yerleştirme bilgilerini verimli bir şekilde çıkarır.

#### S: Geliştiriciler, görüntü yerleştirme bilgilerini anlamaktan ve kullanmaktan nasıl yararlanabilir?

C: Geliştiriciler, PDF belgelerinde hassas görüntü işleme, hizalama ve analiz sağlayabilir. Bu bilgi, görüntü işleme, raporlama ve kalite güvencesi için uygulamalar oluşturmalarını sağlar.

#### S: Kod, görüntüyle ilgili ek öznitelikleri veya meta verileri ayıklamak için özelleştirilebilir mi?

C: Kesinlikle, Aspose.PDF for .NET tarafından sağlanan uygun sınıflar ve yöntemler kullanılarak görüntü tipi, renk alanı, sıkıştırma ve daha fazlası gibi ek öznitelikleri çıkarmak için kod geliştirilebilir.

#### S: Bu öğreticide sağlanan sonucun önemi nedir?

C: Sonuç, öğreticinin içeriğini özetliyor ve Aspose.PDF for .NET'in görüntü yerleştirmelerin ötesindeki yeteneklerinden yararlanarak PDF ile ilgili çeşitli görevlere kapıları açarak daha fazla keşfedilmesini teşvik ediyor.