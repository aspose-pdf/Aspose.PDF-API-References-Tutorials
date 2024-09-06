---
title: Tüm Yazı Tiplerini PDF Dosyasına Alın
linktitle: Tüm Yazı Tiplerini PDF Dosyasına Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ve örnek kod ile Aspose.PDF for .NET'i kullanarak bir PDF dosyasında kullanılan tüm yazı tiplerini programlı bir şekilde nasıl alacağınızı öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-document/getallfonts/
---
Aspose.PDF for .NET, geliştiricilerin PDF dosyalarıyla programatik olarak çalışmasını sağlayan güçlü bir kütüphanedir. Sağladığı özelliklerden biri de PDF dosyasında kullanılan tüm yazı tiplerini alabilme yeteneğidir. Bu, bir PDF dosyasındaki yazı tiplerini programatik olarak analiz etmeniz veya düzenlemeniz gerektiğinde faydalı olabilir.

Bu eğitimde, bir PDF belgesinde kullanılan tüm yazı tiplerini almak için Aspose.PDF for .NET'in nasıl kullanılacağını ele alacağız. Bunu nasıl yapacağınıza dair adım adım bir kılavuz ve örnek kaynak kodu sağlayacağız.

## Adım 1: Yeni bir C# Konsol Uygulaması Oluşturun
Başlamak için Visual Studio'da yeni bir C# Konsol Uygulaması oluşturun. İstediğiniz ismi verebilirsiniz. Proje oluşturulduktan sonra, Aspose.PDF for .NET kitaplığına bir başvuru eklemeniz gerekir.

## Adım 2: Aspose.PDF Ad Alanını İçe Aktarın
Aspose.PDF ad alanını içe aktarmak için C# dosyanızın en üstüne aşağıdaki kod satırını ekleyin:

```csharp
using Aspose.Pdf;
```

## Adım 3: PDF Belgesini Yükleyin
Yazı tiplerini almak istediğiniz PDF belgesini yükleyin:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Adım 4: Tüm Yazı Tiplerini Alın
PDF belgesinde kullanılan tüm yazı tiplerini edinin:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Adım 5: Tüm Yazı Tiplerini Yazdır
PDF belgesinde kullanılan tüm yazı tiplerini yazdır:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### .NET için Aspose.PDF kullanarak Tüm Yazı Tiplerini Al için örnek kaynak kodu
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde kullanılan tüm yazı tiplerini nasıl edineceğinizi ele aldık. Bir PDF belgesinde kullanılan tüm yazı tiplerini edinmek, bir PDF belgesindeki yazı tiplerini programatik olarak analiz etmeniz veya değiştirmeniz gerekiyorsa faydalı olabilir. Aspose.PDF for .NET, bir PDF belgesinde kullanılan tüm yazı tiplerini edinme dahil olmak üzere PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar.

### SSS

#### S: PDF belgesinde kullanılan tüm yazı tiplerini neden almam gerekir?

A: PDF belgesinde kullanılan tüm yazı tiplerini edinmek, yazı tipini değiştirme veya yazı tipi özelleştirme gibi çeşitli amaçlar için yazı tiplerini programlı olarak analiz etmeniz veya değiştirmeniz gerektiğinde yararlı olabilir.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde kullanılan tüm yazı tiplerini nasıl edinebilirim?

 A: .NET için Aspose.PDF'i kullanarak bir PDF belgesinde kullanılan tüm yazı tiplerini şu şekilde alabilirsiniz:`GetAllFonts` yöntemi`FontUtilities` sınıf. Bu yöntem bir dizi döndürür`Aspose.Pdf.Text.Font` PDF belgesinde kullanılan yazı tiplerini temsil eden nesneler.

#### S: Yazı tiplerini belirli kriterlere göre filtreleyebilir miyim?

A: Evet, Aspose.PDF for .NET kullanarak yazı tiplerini belirli kriterlere göre filtreleyebilirsiniz. Tüm yazı tiplerini aldıktan sonra, yazı tiplerini programatik olarak analiz edebilir ve gerektiği gibi filtreleme mantığını uygulayabilirsiniz.

#### S: Aspose.PDF for .NET çeşitli yazı tipi formatlarıyla uyumlu mudur?

A: Evet, Aspose.PDF for .NET, TrueType, OpenType ve Type 1 yazı tipleri dahil olmak üzere çeşitli yazı tipi biçimleriyle uyumludur. Farklı yazı tipi biçimleriyle çalışabilir ve bunları PDF belge düzenlemesi sırasında işleyebilir.