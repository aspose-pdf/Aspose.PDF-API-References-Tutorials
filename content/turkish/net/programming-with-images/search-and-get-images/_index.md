---
title: PDF Dosyasında Görüntüleri Ara ve Al
linktitle: PDF Dosyasında Görüntüleri Ara ve Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarından zahmetsizce resim çıkarmayı öğrenin. PDF işleme becerilerinizi geliştirmek için bu adım adım kılavuzu izleyin.
type: docs
weight: 260
url: /tr/net/programming-with-images/search-and-get-images/
---
## giriiş

Aspose.PDF for .NET kullanarak PDF dosyalarından resim çıkarmak için basit bir yol mu arıyorsunuz? Doğru yerdesiniz! Bu makalede, bir PDF belgesine gömülü resimleri etkili bir şekilde nasıl arayacağınız ve alacağınız konusunda ayrıntılara dalacağız. İster deneyimli bir geliştirici olun, ister PDF manipülasyon dünyasına yeni adım atıyor olun, bu kılavuz sizi tüm süreçte adım adım yönlendirecektir.

## Ön koşullar

Kodun ince ayrıntılarına girmeden önce, listenizde işaretlemeniz gereken birkaç ön koşul var. 

### .NET Çerçevesi

Bilgisayarınızda .NET Framework'ün yüklü olduğundan emin olun. Aspose.PDF for .NET çeşitli sürümlerle uyumludur, ancak en son özelliklerin ve iyileştirmelerin keyfini çıkarmak için en son kararlı sürümü kullanmak en iyisidir.

### Aspose.PDF Kütüphanesi

 Aspose.PDF kütüphanesine erişiminiz olması gerekecek. Eğer henüz yoksa, şu bağlantıdan indirebilirsiniz:[.NET için Aspose.PDF'yi indirin](https://releases.aspose.com/pdf/net/) Ayrıca, şunları keşfedebilirsiniz:[bir aylık ücretsiz deneme](https://releases.aspose.com/) Projelerinizi hiçbir maliyet olmadan başlatmak için.

### Geliştirme Ortamı

Kodu sorunsuz bir şekilde yazmak ve çalıştırmak için Visual Studio veya tercih ettiğiniz herhangi bir IDE gibi uygun bir geliştirme ortamının kurulması gerekir.

## Paketleri İçe Aktar

Aspose.PDF for .NET ile çalışmak için öncelikle projenize uygun ad alanlarını içe aktarmanız gerekir. Yapmanız gerekenler şunlardır:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

 Bu paketlerin her biri PDF belgelerini düzenlerken belirli amaçlara hizmet eder.`Aspose.Pdf` namespace işlemlerinizin temel taşıdır, diğer ikisi ise PDF içindeki görseller ve metinlerle ilgilenmenize yardımcı olur.

## Adım 1: Belge Yolunuzu Ayarlayın

Her şeyden önce, PDF dosyanızın bulunduğu yolu tanımlamanız gerekir. Bu kod parçası bunu ayarlar:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 "BELGE DİZİNİNİZ" ifadesini PDF dosyanızı içeren dizinin gerçek yoluyla değiştirin, örneğin:`C:\Documents\`.

## Adım 2: PDF Belgesini açın

 Sonra, PDF belgesini uygulamanıza yüklemek isteyeceksiniz. Bu, yeni bir`Document` Az önce belirttiğiniz dosya yoluna sahip örnek:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

## Adım 3: ImagePlacementAbsorber'ı oluşturun

 PDF içindeki görselleri aramak için bir`ImagePlacementAbsorber` nesne. Bu sınıf, çıkarma işlemi sırasında PDF'den görüntülerin alınmasına yardımcı olur:

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

## Adım 4: Tüm Sayfalar için Absorber'ı Kabul Edin

 Bu adım,`Document` görüntü emiciyi tüm sayfalara uygulamak. Belgenin herhangi bir yerine yerleştirilen herhangi bir görüntünün tanımlanmasını sağlar:

```csharp
doc.Pages.Accept(abs);
```

## Adım 5: Görüntü Yerleşimlerinde Döngü

Artık görselleri özümsediğinize göre, onları derinlemesine incelemenin zamanı geldi. PDF'den çıkarılan her görsel yerleşimini dolaşacaksınız:

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    // Görüntü özelliklerini elde etmek için sonraki adımlar
}
```

## Adım 6: Görüntü Özelliklerini Çıkarın

 Döngünün içinde, her görüntü hakkında değerli özellikleri almaya başlayabilirsiniz.`imagePlacement` nesnenin boyutlarına ve çözünürlüğüne erişebilirsiniz:

```csharp
XImage image = imagePlacement.Image; // Resmi al

Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
```

## Çözüm

İşte bu kadar! Bu adımları izleyerek, .NET için Aspose.PDF kullanarak PDF dosyalarından resimleri etkili bir şekilde arayabilir ve alabilirsiniz. Sadece birkaç satır kodla, değerli resimleri ve özelliklerini çıkarabilir, uygulamanızda birçok olasılığa kapılar açabilirsiniz.

## SSS

### Aspose.PDF kütüphanesini kullanmak ücretsiz mi?  
Aspose.PDF for .NET ücretli bir kütüphanedir, ancak bir ay boyunca ücretsiz deneme sürümünü indirebilirsiniz.

### Şifreyle korunan PDF dosyalarından resim çıkarabilir miyim?  
Evet, ancak belgeyi açarken şifreyi girmeniz gerekiyor.

### PDF'den hangi tür görseller çıkarılabilir?  
Tüm gömülü görseller, formatlarından (JPEG, PNG, vb.) bağımsız olarak çıkarılabilir.

### Çıkarabileceğim görüntü sayısında bir sınır var mı?  
Kesin bir sınır yok; PDF dosyasının kendisine bağlı.

### Çıkarılan görüntüleri diske kaydedebilir miyim?  
 Evet, görüntüleri kullanarak diske kaydedebilirsiniz.`XImage` Kodunuzdaki nesne.