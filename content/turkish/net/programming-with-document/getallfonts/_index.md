---
title: Tüm Yazı Tiplerini PDF Dosyasında Al
linktitle: Tüm Yazı Tiplerini PDF Dosyasında Al
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuz ve örnek kodla, bir PDF dosyasında kullanılan tüm yazı tiplerini programlı olarak almak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-document/getallfonts/
---
Aspose.PDF for .NET, geliştiricilerin PDF dosyasıyla programlı olarak çalışmasını sağlayan güçlü bir kütüphanedir. Sağladığı özelliklerden biri, bir PDF dosyasında kullanılan tüm yazı tiplerini alabilme yeteneğidir. Bir PDF dosyasındaki yazı tiplerini programlı olarak analiz etmeniz veya değiştirmeniz gerekiyorsa bu yararlı olabilir.

Bu eğitimde, bir PDF belgesinde kullanılan tüm yazı tiplerini elde etmek için Aspose.PDF for .NET'in nasıl kullanılacağını tartışacağız. Örnek kaynak koduyla birlikte bunun nasıl yapılacağına dair adım adım bir kılavuz sunacağız.

## 1. Adım: Yeni bir C# Konsol Uygulaması oluşturun
Başlamak için Visual Studio'da yeni bir C# Konsol Uygulaması oluşturun. İstediğiniz ismi verebilirsiniz. Proje oluşturulduktan sonra Aspose.PDF for .NET kütüphanesine bir referans eklemeniz gerekir.

## Adım 2: Aspose.PDF Ad Alanını İçe Aktarın
Aspose.PDF ad alanını içe aktarmak için C# dosyanızın en üstüne aşağıdaki kod satırını ekleyin:

```csharp
using Aspose.Pdf;
```

## 3. Adım: PDF Belgesini Yükleyin
Yazı tiplerini almak istediğiniz PDF belgesini yükleyin:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Adım 4: Tüm Yazı Tiplerini Alın
PDF belgesinde kullanılan tüm yazı tiplerini edinin:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Adım 5: Tüm Yazı Tiplerini Yazdırın
PDF belgesinde kullanılan tüm yazı tiplerini yazdırın:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Aspose.PDF for .NET kullanarak Tüm Yazı Tiplerini Al için örnek kaynak kodu
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde kullanılan tüm yazı tiplerinin nasıl elde edileceğini tartıştık. Bir PDF belgesindeki yazı tiplerini programlı olarak analiz etmeniz veya değiştirmeniz gerekiyorsa, bir PDF belgesinde kullanılan tüm yazı tiplerini almak yararlı olabilir. Aspose.PDF for .NET, PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar; buna bir PDF belgesinde kullanılan tüm yazı tiplerinin alınması da dahildir.

### SSS'ler

#### S: Bir PDF belgesinde kullanılan tüm yazı tiplerini neden almam gerekiyor?

C: Yazı tipi değiştirme veya yazı tipi özelleştirme gibi çeşitli amaçlar için yazı tiplerini programlı olarak analiz etmeniz veya değiştirmeniz gerekiyorsa, bir PDF belgesinde kullanılan tüm yazı tiplerini almak yararlı olabilir.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde kullanılan tüm yazı tiplerini nasıl edinebilirim?

 C: Bir PDF belgesinde kullanılan tüm yazı tiplerini Aspose.PDF for .NET kullanarak,`GetAllFonts` yöntemi`FontUtilities` sınıf. Bu yöntem bir dizi döndürür`Aspose.Pdf.Text.Font` PDF belgesinde kullanılan yazı tiplerini temsil eden nesneler.

#### S: Yazı tiplerini belirli ölçütlere göre filtreleyebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak yazı tiplerini belirli kriterlere göre filtreleyebilirsiniz. Tüm yazı tiplerini aldıktan sonra, yazı tiplerini programlı olarak analiz edebilir ve gerektiği gibi filtreleme mantığı uygulayabilirsiniz.

#### S: Aspose.PDF for .NET çeşitli yazı tipi formatlarıyla uyumlu mudur?

C: Evet, Aspose.PDF for .NET; TrueType, OpenType ve Type 1 yazı tipleri de dahil olmak üzere çeşitli yazı tipi formatlarıyla uyumludur. Farklı yazı tipi formatlarıyla çalışabilir ve PDF belgesinin işlenmesi sırasında bunları işleyebilir.