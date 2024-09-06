---
title: SVG Boyutlarını Alın
linktitle: SVG Boyutlarını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla SVG dosyalarını PDF'ye dönüştürmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin. PDF'leri düzenlemek isteyen geliştiriciler için mükemmeldir.
type: docs
weight: 40
url: /tr/net/document-conversion/get-svg-dimensions/
---
## giriiş

Aspose.PDF for .NET dünyasına hoş geldiniz! PDF dosyalarını programatik olarak düzenlemek istiyorsanız doğru yerdesiniz. Aspose.PDF, geliştiricilerin PDF belgelerini kolaylıkla oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan güçlü bir kütüphanedir. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz sizi Aspose.PDF for .NET'i kullanmanın temelleri konusunda yönlendirecek ve SVG boyutlarının nasıl alınacağı ve bunların PDF formatına nasıl dönüştürüleceği üzerinde duracaktır.

## Ön koşullar

Koda geçmeden önce, yerinde olması gereken birkaç şey var:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. Bu eğitim için kullanacağımız IDE bu.
2.  .NET Framework: .NET Framework'ün yüklü olduğundan emin olun. Aspose.PDF çeşitli sürümleri destekler, bu nedenle[belgeleme](https://reference.aspose.com/pdf/net/) uyumluluk için.
3.  Aspose.PDF Kütüphanesi: .NET için Aspose.PDF'nin en son sürümünü şu adresten indirebilirsiniz:[indirme bağlantısı](https://releases.aspose.com/pdf/net/) Eğer önce denemek isterseniz, ayrıca bir tane alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/).
4. Temel C# Bilgisi: C# programlamaya aşinalık, örnekleri daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Başlamak için gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

1. Visual Studio projenizi açın.
2. Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
3. "Aspose.PDF" dosyasını arayın ve paketi yükleyin.

Paketinizi kurduktan sonra kodlamaya başlayabilirsiniz!

## Adım 1: Projenizi Kurun

### Yeni Bir Proje Oluştur

Öncelikle Visual Studio'da yeni bir C# projesi oluşturalım.

- Visual Studio'yu açın ve "Yeni proje oluştur" seçeneğini seçin.
- "Konsol Uygulaması (.NET Framework)" seçeneğini seçin ve "İleri"ye tıklayın.
- Projenize bir isim verin (örneğin, "AsposePDFExample") ve "Oluştur"a tıklayın.

### Yönergeleri Kullanarak Ekle

 Artık projeniz kurulduğuna göre, gerekli using yönergelerini en üste eklemeniz gerekiyor.`Program.cs` dosya:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Bu, Aspose.PDF kütüphanesi tarafından sağlanan sınıflara ve yöntemlere erişmenizi sağlayacaktır.

## Adım 2: SVG Belgesini Yükleyin

### Belge Dizinini Tanımla

SVG belgesini yüklemeden önce, belgeler dizininize giden yolu belirtmeniz gerekir. Değiştir`"YOUR DOCUMENT DIRECTORY"` SVG dosyanızın bulunduğu gerçek yol ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### SVG Belgesini Yükle

 Şimdi, SVG belgesini kullanarak yükleyelim`SvgLoadOptions` sınıf. Bu sınıf, SVG içeriğine göre sayfa boyutunu ayarlamanıza olanak tanır.

```csharp
var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

## Adım 3: Sayfa Kenar Boşluklarını Ayarlayın

SVG içeriğinin PDF'ye mükemmel şekilde uymasını sağlamak için sayfa kenar boşluklarını sıfıra ayarlamanız gerekir. Bu adım, SVG boyutlarının bütünlüğünü korumak için çok önemlidir.

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

## Adım 4: Belgeyi PDF olarak kaydedin

Son olarak, SVG belgesini PDF olarak kaydetme zamanı geldi. Çıktı dosya adını ve yolunu aşağıdaki gibi belirtebilirsiniz:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

Ve işte bu kadar! Aspose.PDF for .NET kullanarak bir SVG dosyasını başarıyla PDF'ye dönüştürdünüz.

## Çözüm

Tebrikler! .NET için Aspose.PDF kullanarak basit ama güçlü bir görevi yeni tamamladınız. Bu kılavuzu izleyerek, bir SVG belgesini nasıl yükleyeceğinizi, kenar boşluklarını nasıl ayarlayacağınızı ve PDF olarak nasıl kaydedeceğinizi öğrendiniz. Aspose.PDF ile olasılıklar sonsuzdur ve bu sadece buzdağının görünen kısmıdır. Karmaşık PDF'ler oluşturmak, var olanları düzenlemek veya formatlar arasında dönüştürme yapmak istiyorsanız, Aspose.PDF sizin için her şeyi yapar. Öyleyse, daha ne bekliyorsunuz? Daha derinlere dalın[belgeleme](https://reference.aspose.com/pdf/net/) ve bu kütüphanenin sunduğu tüm özellikleri keşfedin!

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### Aspose.PDF'yi nasıl yüklerim?
 Aspose.PDF'yi Visual Studio'daki NuGet Paket Yöneticisi aracılığıyla yükleyebilir veya şu adresten indirebilirsiniz:[alan](https://releases.aspose.com/pdf/net/).

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose bir[ücretsiz deneme](https://releases.aspose.com/) satın almadan önce kütüphaneyi test etmeniz için.

### Aspose.PDF için desteği nerede bulabilirim?
 Destek alabilirsiniz[Aspose forumu](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF için geçici lisansı nasıl alabilirim?
 Bir talepte bulunabilirsiniz[geçici lisans](https://purchase.aspose.com/temporary-license/) Aspose web sitesinden.