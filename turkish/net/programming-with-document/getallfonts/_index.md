---
title: Tüm Yazı Tiplerini Alın
linktitle: Tüm Yazı Tiplerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ve örnek kod ile bir PDF belgesinde kullanılan tüm yazı tiplerini programlı olarak almak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-document/getallfonts/
---

Aspose.PDF for .NET, geliştiricilerin programlı olarak PDF belgeleriyle çalışmasını sağlayan güçlü bir kitaplıktır. Sağladığı özelliklerden biri, bir PDF belgesinde kullanılan tüm yazı tiplerini alma yeteneğidir. Bu, bir PDF belgesindeki yazı tiplerini programlı olarak analiz etmeniz veya değiştirmeniz gerektiğinde yararlı olabilir.

Bu eğitimde, bir PDF belgesinde kullanılan tüm yazı tiplerini almak için Aspose.PDF for .NET'in nasıl kullanılacağını tartışacağız. Örnek kaynak koduyla birlikte bunun nasıl yapılacağına dair adım adım bir kılavuz sağlayacağız.

## 1. Adım: Yeni bir C# Konsol Uygulaması oluşturun
Başlamak için Visual Studio'da yeni bir C# Konsol Uygulaması oluşturun. Adını ne istersen koyabilirsin. Proje oluşturulduktan sonra Aspose.PDF for .NET kitaplığına bir referans eklemeniz gerekir.

## Adım 2: Aspose.PDF Ad Alanını İçeri Aktarın
Aspose.PDF ad alanını içe aktarmak için C# dosyanızın en üstüne aşağıdaki kod satırını ekleyin:

```csharp
using Aspose.Pdf;
```

## 3. Adım: PDF Belgesini Yükleyin
Yazı tiplerini almak istediğiniz PDF belgesini yükleyin:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4. Adım: Tüm Yazı Tiplerini Alın
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

### Aspose.PDF for .NET kullanarak Get All Fonts için örnek kaynak kodu
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
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde kullanılan tüm yazı tiplerini nasıl elde edeceğimizi tartıştık. Bir PDF belgesindeki yazı tiplerini programlı olarak analiz etmeniz veya değiştirmeniz gerekiyorsa, bir PDF belgesinde kullanılan tüm yazı tiplerini almak yararlı olabilir. Aspose.PDF for .NET, bir PDF belgesinde kullanılan tüm yazı tiplerini almak da dahil olmak üzere, PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar.


