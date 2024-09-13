---
title: PDF Dosyasında Resim Bilgileri
linktitle: PDF Dosyasında Resim Bilgileri
second_title: Aspose.PDF for .NET API Referansı
description: Kapsamlı adım adım kılavuzumuzla Aspose.PDF for .NET'i kullanarak PDF'lerden görüntü bilgilerini çıkarmayı öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-images/image-information/
---
## giriiş

PDF dosyaları günümüzde her yerdedir; neredeyse her profesyonel ve kişisel belge bir noktada bu biçime girer. İster bir rapor, ister bir broşür veya bir e-kitap olsun, bu dosyalarla programatik olarak nasıl etkileşim kurulacağını anlamak sayısız olasılık sunar. Yaygın bir gereksinim, PDF dosyalarından görüntü bilgilerini çıkarmaktır. Bu kılavuzda, bir PDF belgesine gömülü görüntüler hakkında önemli ayrıntıları çıkarmak için .NET için Aspose.PDF kitaplığının nasıl kullanılacağına derinlemesine bakacağız.

## Ön koşullar

Kodlamanın inceliklerine dalmadan önce, yerine getirmeniz gereken birkaç ön koşul vardır:

1. Geliştirme Ortamı: Bir .NET geliştirme ortamı kurulumuna ihtiyacınız olacak. Bu, Visual Studio veya herhangi bir .NET uyumlu IDE olabilir.
2.  Aspose.PDF Kütüphanesi: Aspose.PDF kütüphanesine erişiminiz olduğundan emin olun. Bunu şuradan indirebilirsiniz:[Aspose web sitesi](https://releases.aspose.com/pdf/net/). 
3. Temel C# Bilgisi: C# ve nesne yönelimli programlama kavramlarına aşinalık, eğitimi zahmetsizce takip etmenize yardımcı olacaktır.
4. PDF Belgesi: Kodunuzu test etmek için görseller içeren bir örnek PDF belgesini elinizin altında bulundurun. 

## Paketleri İçe Aktarma

Aspose.PDF kütüphanesini kullanmaya başlamak için, gerekli ad alanlarını C# dosyanıza aktarmanız gerekir. İşte kısa bir özet:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Bu ad alanları, PDF dosyalarını düzenlemek ve görüntü verilerini çıkarmak için gereken sınıflara ve yöntemlere erişmenizi sağlayacaktır.

Artık her şeyi ayarladığınıza göre, bunu yönetilebilir adımlara bölmenin zamanı geldi. Bir PDF belgesi yükleyen, her sayfayı inceleyen ve belgedeki her görüntünün boyutlarını ve çözünürlüğünü çıkaran bir C# programı yazacağız.

## Adım 1: Belgeyi Başlatın

 Bu adımda, PDF dosyanızın yolunu kullanarak PDF belgesini başlatacağız. Şunu değiştirmelisiniz:`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın bulunduğu gerçek yol ile.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Kaynak PDF dosyasını yükleyin
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
 Biz bir tane yaratıyoruz`Document` PDF'yi belirtilen dizinden yükleyen nesne. Bu, dosyanın içeriğiyle çalışmamıza olanak tanır.

## Adım 2: Varsayılan Çözünürlüğü Ayarlayın ve Veri Yapılarını Başlatın

Sonra, hesaplamalar için yararlı olan görüntüler için varsayılan bir çözünürlük ayarlayacağız. Ayrıca, görüntü adlarını tutacak bir dizi ve grafiksel durumları yönetecek bir yığın hazırlayacağız.

```csharp
// Görüntü için varsayılan çözünürlüğü tanımlayın
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Resim adlarını tutacak dizi listesi nesnesini tanımlayın
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
 The`defaultResolution` değişkeni, görüntülerin çözünürlüğünü doğru bir şekilde hesaplamamıza yardımcı olur.`graphicsState`Yığın, dönüşüm operatörleriyle karşılaştığımızda belgenin geçerli grafiksel durumunu depolamak için bir araç görevi görür.

## Adım 3: Sayfadaki Her Operatörü İşle

Şimdi belgenin ilk sayfasındaki tüm operatörleri dolaşıyoruz. Ağır kaldırmanın gerçekleştiği yer burasıdır. 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // İşlem operatörleri...
}
```
PDF dosyasındaki her operatör, görüntüleyiciye görseller de dahil olmak üzere grafik öğelerinin nasıl yönetileceğini söyleyen bir komuttur.

## Adım 4: GSave/GRestore Operatörlerini Yönetin

Döngü içerisinde grafiksel durumda yapılan değişiklikleri takip etmek için grafik kaydetme ve geri yükleme komutlarını işleyeceğiz.

```csharp
if (opSaveState != null) 
{
    // Önceki durumu kaydet
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    // Önceki durumu geri yükle
    graphicsState.Pop();
}
```
`GSave` mevcut grafik durumunu kaydederken`GRestore` son kaydedilen durumu geri yükler ve görüntüleri işlerken herhangi bir dönüşümü geri almamızı sağlar.

## Adım 5: Dönüşüm Matrislerini Yönetin

Daha sonra, görüntülere dönüşümler uygularken dönüşüm matrislerinin birleştirilmesini ele alacağız.

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
Bir dönüşüm matrisi uygulandığında, görüntüye uygulanan herhangi bir ölçekleme veya ötelemeyi takip edebilmemiz için bunu grafik durumunda saklanan geçerli matrisle çarparız.

## Adım 6: Görüntü Bilgilerini Çıkarın

Son olarak, resimler için çizim operatörünü işleyip boyutlar, çözünürlükler gibi gerekli bilgileri çıkarıyoruz.

```csharp
else if (opDo != null) 
{
    // Nesneleri çizen Do operatörünü kullanın
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        // Bilgileri çıktı olarak al
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
Burada, operatörün bir görüntü çizmekten sorumlu olup olmadığını kontrol ediyoruz. Eğer öyleyse, karşılık gelen XImage nesnesini alırız, ölçeklenmiş boyutlarını ve çözünürlüğünü hesaplarız ve gerekli bilgileri yazdırırız.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyasından görüntü bilgilerinin nasıl çıkarılacağına dair çalışan bir örnek oluşturdunuz. Bu yetenek, raporlama, veri çıkarma veya hatta özel PDF görüntüleyicileri gibi çeşitli uygulamalar için PDF belgelerini analiz etmesi veya düzenlemesi gereken geliştiriciler için inanılmaz derecede yararlı olabilir. 


## SSS

### Aspose.PDF kütüphanesi nedir?
Aspose.PDF kütüphanesi, .NET uygulamalarında PDF dosyaları oluşturmak, düzenlemek ve dönüştürmek için güçlü bir araçtır.

### Kütüphaneyi ücretsiz kullanabilir miyim?
 Evet, Aspose ücretsiz deneme sunuyor. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### Hangi tür görüntü formatları çıkarılabilir?
Kütüphane, PDF'ye gömüldükleri sürece JPEG, PNG ve TIFF gibi çeşitli resim formatlarını destekler.

### Aspose ticari amaçlı mı kullanılıyor?
 Evet, Aspose ürünlerini ticari olarak kullanabilirsiniz. Lisanslama için şu adresi ziyaret edin:[satın alma sayfası](https://purchase.aspose.com/buy).

### Aspose için nasıl destek alabilirim?
 Destek forumuna erişebilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).