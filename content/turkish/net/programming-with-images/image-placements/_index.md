---
title: Resim Yerleşimleri
linktitle: Resim Yerleşimleri
second_title: .NET API Referansı için Aspose.PDF
description: Görüntüleri bir PDF belgesine yerleştirmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-images/image-placements/
---
Bu derste, PDF belgeleriyle çalışmak ve görüntüler üzerinde işlemler gerçekleştirmek için .NET için Aspose.PDF kütüphanesini kullanacağız. Bir PDF belgesi yükleyeceğiz, görsel yerleştirme bilgilerini çıkaracağız ve görselleri boyutları görünür şekilde getireceğiz.

## 1. Adım: Ortamı ayarlama
Başlamadan önce geliştirme ortamınızı aşağıdakilerle kurduğunuzdan emin olun:
- Aspose.PDF for .NET makinenizde yüklü.
- AC# projesi kullanıma hazır.

## Adım 2: PDF belgesini yükleme
Başlamak için işlemek istediğimiz PDF belgesini yüklememiz gerekiyor. PDF belgesini içeren dizine giden doğru yola sahip olduğunuzdan emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Kaynak PDF belgesini yükleyin
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyasını içeren belgeler dizininizin gerçek yolu ile birlikte.

## 3. Adım: Görüntülerden yerleşim bilgilerini çıkarın
 Artık PDF belgesini yüklediğimize göre görüntülerden yerleşim bilgilerini çıkarabiliriz. Kullanacağız`ImagePlacementAbsorber`belgenin ilk sayfasındaki görüntü konumlarını absorbe etmek için.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// İlk sayfanın içeriğini yükleyin
doc.Pages[1].Accept(abs);
```

Artık belgenin ilk sayfasından resim yerleştirme bilgilerini çıkardık.

## 4. Adım: Görünür boyutlara sahip görselleri alma
Şimdi daha önce çıkardığımız yerleştirme bilgilerinden görselleri görünür boyutlarıyla alacağız.

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

     // Görüntüyü görünür boyutlarda alın
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Kaynaklardan görüntüyü alın
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Gerçek boyutlara sahip bir resim oluşturun
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

Bu döngüde her görüntünün genişlik, yükseklik, sol alt köşenin X ve Y koordinatları, yatay ve dikey çözünürlük gibi özelliklerini alırız. Daha sonra yerleştirme bilgilerini kullanarak her görseli görünür boyutlarıyla alıyoruz.

### Aspose.PDF for .NET kullanarak Görüntü Yerleştirmeleri için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Kaynak PDF belgesini yükleyin
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// İlk sayfanın içeriğini yükle
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
	// Görünür boyutlara sahip resmi alın
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Kaynaklardan görüntüyü al
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Gerçek boyutlarla bitmap oluşturun
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Çözüm
Tebrikler! Artık bir PDF belgesinde görüntü yerleşimleri gerçekleştirmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrendiniz. PDF belgesi yüklemenize, görüntülerden yerleşim bilgilerini çıkarmanıza ve görüntüleri boyutları görünür şekilde almanıza olanak tanıyan sağlanan C# kaynak kodunu açıkladık. Diğer birçok özelliğini keşfetmek için Aspose.PDF ile daha fazla deneme yapmaktan çekinmeyin.

### SSS'ler

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinden görüntü yerleştirme bilgilerini çıkarmanın amacı nedir?

C: Görüntü yerleştirme bilgilerini çıkarmak, bir PDF belgesindeki görüntülerin konumunu, boyutlarını ve çözünürlüğünü almanızı sağlar. Bu bilgi hassas görüntü manipülasyonu ve analizi için gereklidir.

#### S: Aspose.PDF for .NET, bir PDF belgesinden görüntü yerleştirme bilgilerinin çıkarılmasını nasıl kolaylaştırır?

 C: Aspose.PDF for .NET şunları sağlar:`ImagePlacementAbsorber`Bir PDF belgesinden görüntü yerleştirme ayrıntılarını almak için kullanılabilen sınıf. Sağlanan kod, resim yerleştirme bilgilerini almak için bu sınıfın nasıl kullanılacağını gösterir.

#### S: Görüntü yerleştirme bilgileri gerçek dünya senaryolarında ne için kullanılabilir?

C: Görüntü yerleştirme bilgileri, doğru görüntü hizalamasının sağlanması, görüntü boyutlarının hesaplanması, görüntü kalitesinin doğrulanması ve bir PDF belgesinde görüntü kullanımına ilişkin raporlar oluşturulması gibi görevler için değerlidir.

#### S: Kod örneği, görüntü yerleştirme bilgilerinin doğru şekilde çıkarılmasını nasıl sağlıyor?

 C: Kod örneği şunları kullanır:`ImagePlacementAbsorber` Belirtilen bir sayfanın içeriğinde gezinmek, görüntü yerleşimlerini tanımlamak ve bunların genişlik, yükseklik, koordinatlar ve çözünürlük gibi niteliklerini almak için sınıf.

#### S: Kod, görüntüleri birden çok sayfa veya belgede işleyecek şekilde genişletilebilir mi?

C: Evet, kod, görüntü yerleştirme bilgilerini çıkarmak ve görüntüyle ilgili görevleri gerçekleştirmek için birden çok sayfa veya belge yinelenerek genişletilebilir.

#### S: Kod, yerleşim bilgilerine göre görselleri görünür boyutlarıyla nasıl alır?

C: Kod örneği, görüntü verilerini kaynaklardan ayıklar, gerçek boyutları içeren bir bit eşlem görüntüsü oluşturur ve genişlik, yükseklik, koordinatlar ve çözünürlük gibi özellikler sağlar.

#### S: Bu yaklaşım çok sayıda resim içeren büyük PDF belgeleri için etkili midir?

C: Evet, Aspose.PDF for .NET performans ve kaynak kullanımı açısından optimize edilmiştir. Büyük PDF belgelerinden bile görüntü yerleştirme bilgilerini verimli bir şekilde çıkarır.

#### S: Geliştiriciler resim yerleştirme bilgilerini anlamaktan ve kullanmaktan nasıl yararlanabilir?

C: Geliştiriciler, PDF belgelerinde hassas görüntü işleme, hizalama ve analiz sağlayabilirler. Bu bilgi onlara görüntü işleme, raporlama ve kalite güvencesi için uygulamalar oluşturma yetkisi verir.

#### S: Kod, görüntüyle ilgili ek nitelikler veya meta veriler çıkaracak şekilde özelleştirilebilir mi?

C: Kesinlikle, Aspose.PDF for .NET tarafından sağlanan uygun sınıflar ve yöntemler kullanılarak kod, görüntü türü, renk alanı, sıkıştırma ve daha fazlası gibi ek nitelikleri çıkaracak şekilde geliştirilebilir.

#### S: Bu eğitimde sunulan sonucun önemi nedir?

C: Sonuç, eğitimin içeriğini özetlemekte ve Aspose.PDF for .NET'in görüntü yerleştirmenin ötesindeki yeteneklerini geliştirmek için daha fazla araştırılmasını teşvik ederek PDF ile ilgili çeşitli görevlere kapı açmaktadır.