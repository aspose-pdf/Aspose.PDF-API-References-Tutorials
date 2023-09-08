---
title: PDF Dosyasındaki Görselleri Arayın ve Alın
linktitle: PDF Dosyasındaki Görselleri Arayın ve Alın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki görselleri aramak ve almak için adım adım kılavuz.
type: docs
weight: 260
url: /tr/net/programming-with-images/search-and-get-images/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak PDF dosyasındaki görselleri nasıl arayacağınızı ve alacağınızı anlatacağız. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- .NET için Aspose.PDF kütüphanesi kuruldu. Aspose'un resmi web sitesinden indirebilirsiniz.

## 1. Adım: PDF belgesini yükleme

Başlamak için PDF belgesini yüklemek üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Belgeyi aç
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

PDF belgenize doğru yolu girdiğinizden emin olun.

## 2. Adım: Görsel Konumlarını Arama

PDF belgesindeki görsellerin konumlarını aramak için aşağıdaki kodu kullanın:

```csharp
// Resim konumlarını aramak için bir ImagePlacementAbsorber nesnesi oluşturun
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Belgenin tüm sayfaları için emiciyi kabul edin
doc.Pages.Accept(abs);
```

Bu, emicideki görüntülerin konumlarını toplayacaktır.

## 3. Adım: Görsel konumlarına göz atın ve görselleri ve özelliklerini alın

Daha sonra, toplanan görsel konumlarına göz atacağız ve görselleri ve özelliklerini alacağız. Aşağıdaki kodu kullanın:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // ImagePlacement nesnesini kullanarak görüntüyü alın
     XImage image = imagePlacement.Image;

     // Görüntü konumu özelliklerini görüntüleme
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Bu, tüm görsel konumlarına göz atacak, eşleşen görselleri alacak ve özelliklerini gösterecektir.

### Aspose.PDF for .NET kullanarak Görüntü Arama ve Alma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Resim yerleştirme araması gerçekleştirmek için ImagePlacementAbsorber nesnesi oluşturun
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Tüm sayfalar için emiciyi kabul edin
doc.Pages.Accept(abs);
// Tüm ImagePlacement'lar arasında dolaşın, görseli ve ImagePlacement Özelliklerini alın
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// ImagePlacement nesnesini kullanarak görüntüyü alın
	XImage image = imagePlacement.Image;
	// Tüm yerleşimler için resim yerleşimi özelliklerini görüntüle
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki görselleri başarıyla aradınız ve elde ettiniz. Artık görüntüleri ayıklamak ve özelliklerini PDF dosyalarından almak için bu yöntemi kendi projelerinize uygulayabilirsiniz.

### PDF dosyasındaki görselleri aramak ve almak için SSS'ler

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde görsel aramanın ve elde etmenin amacı nedir?

C: Bir PDF belgesindeki görüntüleri aramak ve elde etmek, PDF dosyasındaki görüntüleri bulmanıza ve çıkarmanıza olanak tanır. Bu, içeriğin analiz edilmesi, görüntü özelliklerinin doğrulanması veya görüntülerin daha fazla işlenmesi gibi çeşitli amaçlar için yararlı olabilir.

#### S: PDF belgesindeki görselleri arama süreci nasıl çalışır?

 C: Süreç şunları kullanmayı içerir:`ImagePlacementAbsorber` PDF belgesinin tüm sayfalarında görüntü yerleşimleri için arama gerçekleştirmek için nesneyi seçin. Emici, belgedeki her görüntünün konumu, boyutu ve çözünürlüğü hakkında bilgi toplar.

####  Soru: Programın amacı nedir?`ImagePlacement` object in the code?

 C:`ImagePlacement`nesne, bir görüntünün PDF belgesi içindeki yerleşimini temsil eder. Görüntünün boyutları, koordinatları ve çözünürlüğü gibi ayrıntılara erişmenizi sağlayan özellikler sağlar.

#### S: Aranan ve elde edilen görselleri belirli kriterlere göre filtreleyebilir miyim?

C: Sağlanan kod, PDF belgesindeki tüm görseller hakkında bilgi toplar. Görüntüleri belirli kriterlere (ör. görüntü türü, boyutlar, çözünürlük) göre filtrelemek istiyorsanız, uygun filtreleme koşullarını içerecek şekilde kodu değiştirmeniz gerekebilir.

#### S: Yerleşim bilgilerini aldıktan sonra gerçek görsel içeriğine nasıl erişebilirim?

 C:`XImage` elde edilen nesne`ImagePlacement` nesne gerçek görüntü içeriğini temsil eder. Bunu daha da işleyebilirsiniz`XImage` nesneyi bir dosyaya kaydetmek veya uygulamanızda görüntülemek gibi.

#### S: Elde edilen görüntü özellikleriyle ne yapabilirim?

C: Elde edilen görüntü özellikleri (genişlik, yükseklik, koordinatlar ve çözünürlük) çeşitli amaçlarla kullanılabilir. Özellikleri analiz edebilir, kullanıcıya görüntüleyebilir veya daha sonraki işlemler için girdi olarak kullanabilirsiniz.

#### S: Bu yöntemi kullanarak PDF belgesindeki görüntüleri değiştirebilir veya düzenleyebilir miyim?

C: Sağlanan kod, resim yerleştirme bilgilerinin aranmasına ve elde edilmesine odaklanmaktadır. Görüntüleri değiştirmek veya düzenlemek için Aspose.PDF kütüphanesini kullanarak görüntü işleme gibi ek işlevleri entegre etmeniz gerekebilir.

#### S: Bu yöntemi kendi projelerime nasıl entegre edebilirim?

C: Bu yöntemi projelerinize entegre etmek için özetlenen adımları izleyin ve kodu gerektiği gibi değiştirin. Elde edilen görsel yerleştirme bilgilerini ve özelliklerini uygulamanızın gereksinimlerine göre kullanabilirsiniz.

#### S: Aspose.PDF for .NET, PDF belgelerinde görüntü manipülasyonuyla ilgili başka özellikler sunuyor mu?

C: Evet, Aspose.PDF for .NET, PDF belgelerindeki görüntülerle çalışmak için görüntü ekleme, yeniden boyutlandırma, döndürme, çıkartma ve daha fazlasını içeren bir dizi özellik sunar. Tüm yeteneklerini keşfetmek için kitaplığın belgelerini ve örneklerini inceleyebilirsiniz.