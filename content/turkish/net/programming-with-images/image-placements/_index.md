---
title: Resim Yerleşimleri
linktitle: Resim Yerleşimleri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgelerindeki görüntü yerleşimlerini nasıl çıkaracağınızı ve düzenleyeceğinizi öğrenin. Örnekler ve kod parçacıkları içeren adım adım kılavuz.
type: docs
weight: 170
url: /tr/net/programming-with-images/image-placements/
---
## giriiş

PDF dosyalarındaki resimlerle çalışmak zor olabilir, ancak Aspose.PDF for .NET ile ter dökmeden resim özelliklerini kolayca düzenleyebilir ve çıkarabilirsiniz. Resim boyutlarını almak, çıkarmak veya çözünürlük gibi diğer özellikleri almak istiyorsanız, Aspose.PDF ihtiyacınız olan araçlara sahiptir. Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF belgesindeki resim yerleşimlerini nasıl çıkaracağınıza dair adım adım bir kılavuzda size yol gösterecektir. Paketleri içe aktarmaktan genişlik, yükseklik ve çözünürlük gibi resim özelliklerini almaya kadar her şeyi ele alacağız.

## Ön koşullar

Eğitime başlamadan önce, yerinde olması gereken birkaç şey var. İşte hızlı bir kontrol listesi:

1.  Aspose.PDF for .NET: Aspose.PDF for .NET kütüphanesini yüklediğinizden emin olun. İndirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
2. Geliştirme Ortamı: Bilgisayarınızda Visual Studio veya .NET destekli herhangi bir IDE'nin yüklü olması gerekir.
3. Bir PDF Belgesi: Görüntüler içeren bir örnek PDF belgesi hazırlayın. Bu örnek için, adlı bir dosya kullanacağız`ImagePlacement.pdf`.
4. Temel C# Bilgisi: Bu rehber başlangıç seviyesindekilere uygun olsa da, temel C# bilgisi kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Kodun ince ayrıntılarına girmeden önce yapmanız gereken ilk şey gerekli ad alanlarını içe aktarmaktır. Bu paketler, .NET için Aspose.PDF'de PDF belgeleri ve görüntü düzenlemeyle çalışmak için çok önemlidir.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

Bu paketler PDF'lerle çalışmanıza olanak tanır (`Aspose.Pdf`), görüntü yerleşimlerini manipüle edin (`Aspose.Pdf.ImagePlacement`), ve görüntü akışlarını ve grafikleri yönetin (`System.Drawing` Ve`System.IO`).

Artık ön koşullar ve paketler hazır olduğuna göre, eğitimin her bir bölümünü basit ve anlaşılması kolay bir kılavuzda ele alalım.

## Adım 1: PDF Belgesini Yükleyin

İlk adım PDF belgesini projenize yüklemektir. Bu, PDF dosyası içindeki görsellerle çalışmanın temeli olacaktır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

 Bu adımda, PDF belgesinin dosya yolunu kullanarak tanımlıyoruz`dataDir`ve sonra yeni bir örnek oluşturma`Aspose.Pdf.Document` sınıf. Bu, PDF dosyasını programımıza yüklememizi sağlar. Basit, değil mi? Tıpkı okumaya başlamak için bir kitabı açmak gibi, artık içindeki içeriği keşfetmeye hazırız.

## Adım 2: Görüntü Yerleştirme Emicisini Başlatın

Görüntüleri çıkarmak için "Görüntü Yerleşimi Emicisi" adı verilen bir şeye ihtiyacımız var. Bunu, belirli bir sayfadaki tüm görüntü bilgilerini emen bir araç olarak düşünün.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

 Burada, bir örnek oluşturuyoruz`ImagePlacementAbsorber`. Bu nesne, belirli bir PDF sayfasındaki tüm resim yerleşimleri hakkında bilgi toplayacak ve depolayacaktır. Bunu, bir sayfayı büyüteçle tarayıp üzerindeki tüm resimleri tanımlamak gibi düşünün!

## Adım 3: İlk Sayfadaki Absorber'ı Kabul Edin

Sonra, emiciye PDF'in hangi sayfasının taranacağını söylememiz gerekir. Bu örnekte, ilk sayfaya odaklanacağız.

```csharp
doc.Pages[1].Accept(abs);
```

 The`Accept` yöntem, PDF belgesinin ilk sayfasını herhangi bir görüntü açısından tarar ve sonuçları belgenin içinde depolar.`ImagePlacementAbsorber`Bu, büyütece resimlerin nerede aranacağını söylemek gibi bir şey.

## Adım 4: Her Görüntü Yerleşiminde Döngü Yapın

Sayfayı taradığımıza göre, sayfada bulunan her bir resmi tarayıp özelliklerini almamız gerekiyor.

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

Bu döngü sayfada bulunan her bir resmin içinden geçer. Genişliği, yüksekliği, sol alt x'i (LLX), sol alt y'yi (LLY) ve resmin çözünürlüğünü (hem yatay hem de dikey) yazdırıyoruz. Bu ayrıntılar, PDF içindeki her bir resmin boyutunu ve konumunu anlamanıza yardımcı olur.

## Adım 5: Görünür Boyutlara Sahip Görüntüyü Çıkarın

Görüntüler hakkında bilgi topladıktan sonra, gerçek görüntüyü boyutlarıyla birlikte çıkarmak isteyebilirsiniz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır.

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

 Bu kod parçacığı, görüntüyü PDF'den alır ve onu, tanımlandığı gibi gerçek boyutlarına ölçekler.`ImagePlacement` nesne. Görüntüyü bir bellek akışına kaydederek ve ölçekleyerek, çıkardığınız görüntünün PDF'de görüntülendiği tam boyutu korumasını sağlarsınız.

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF belgesinden görüntü yerleşimlerini çıkarmak, adım adım açıkladığınızda oldukça basittir. Bir PDF'yi yüklemekten görüntü özelliklerini almaya ve görüntüleri gerçek boyutlarıyla çıkarmaya kadar her şeyi ele aldık. Aspose.PDF, PDF'lerle çalışmayı ve içerikleri düzenlemeyi inanılmaz derecede basit hale getirerek, görüntüler, metin ve çok daha fazlasıyla verimli bir şekilde çalışmanıza olanak tanır.

## SSS

### PDF'in belirli bir sayfasından görsel çıkarabilir miyim?  
 Evet, kullanırken sayfa numarasını belirterek`Accept` Bu yöntemle istediğiniz belirli sayfaya odaklanabilirsiniz.

### Çıkarım için hangi görüntü formatları destekleniyor?  
Aspose.PDF PNG, JPEG, BMP ve daha fazlası dahil olmak üzere çeşitli formatları destekler.

### Çıkarılan görselde değişiklik yapmak mümkün müdür?  
 Kesinlikle! Çıkardıktan sonra, şunu kullanabilirsiniz:`System.Drawing` Görüntüyü düzenlemek için namespace.

### Şifreyle korunan PDF'lerden resim çıkarabilir miyim?  
Evet yapabilirsiniz, ancak görüntüleri çıkarmadan önce uygun kimlik bilgilerini kullanarak PDF'in kilidini açmanız gerekir.

### Aspose.PDF for .NET tüm .NET framework'lerinde çalışır mı?  
Evet, .NET Framework, .NET Core ve .NET 5 ve üzeri sürümleri destekler.