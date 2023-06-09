---
title: XMP Meta Verilerini Alın
linktitle: XMP Meta Verilerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'in GetXmpMetadata özelliğinin, C# kaynak kodunu kullanarak bir PDF belgesinden XMP meta verilerini ayıklamak için nasıl kullanılacağını öğrenin.
type: docs
weight: 200
url: /tr/net/programming-with-document/getxmpmetadata/
---

 Aspose.PDF for .NET, geliştiricilerin kendi .NET uygulamalarında PDF dosyaları oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan popüler bir PDF işleme kitaplığıdır. Bu kitaplığın sunduğu özelliklerden biri, XMP meta verilerini bir PDF belgesinden çıkarma yeteneğidir. Bu öğretici, kullanımın adımlarında size rehberlik edecektir.`GetXmpMetadata` Aspose.PDF for .NET'in bir PDF belgesinden XMP meta verilerini ayıklama özelliği.

## 1. Adım: Aspose.PDF for .NET'i kurun

 Aspose.PDF for .NET'i .NET uygulamalarınızda kullanmak için önce kütüphaneyi kurmalısınız. Kütüphanenin en son sürümünü adresinden indirebilirsiniz.[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net).

Kitaplığı indirdikten sonra, ZIP dosyasının içeriğini bilgisayarınızdaki bir klasöre çıkarın. Ardından, .NET projenizde Aspose.PDF for .NET DLL'ye bir referans eklemeniz gerekecektir.

## 2. Adım: PDF Belgesini Yükleyin

 Aspose.PDF for .NET'i yükledikten ve .NET projenize DLL'ye bir referans ekledikten sonra,`GetXmpMetadata` XMP meta verilerini bir PDF belgesinden çıkarma özelliği.

Bu özelliği kullanmanın ilk adımı, XMP meta verilerini ayıklamak istediğiniz PDF belgesini yüklemektir. Bunu yapmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini aç
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 Yukarıdaki kodda değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolu ile. Bu kod, PDF belgesini bir`Document` XMP meta verilerini ayıklamak için kullanabileceğiniz nesne.

## 3. Adım: XMP Meta Verilerini Çıkarın

XMP meta verilerini bir PDF belgesinden çıkarmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Yukarıdaki kodda,`xmp:CreateDate`, `xmp:Nickname` , Ve`xmp:CustomProperty`bir PDF belgesinden çıkarabileceğiniz XMP meta veri özelliklerine örneklerdir. Bu özellik adlarını, ayıklamak istediğiniz diğer XMP meta veri özelliklerinin adlarıyla değiştirebilirsiniz.

### Aspose.PDF for .NET kullanarak XMP Meta Verilerini Almak için Örnek Kaynak Kodu

 XMP meta verilerini bir PDF belgesinden ayıklamak için tam kaynak kodunu burada bulabilirsiniz.`GetXmpMetadata` Aspose.PDF for .NET özelliği:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini aç
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// XMP meta verilerini ayıklayın
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Yukarıdaki kodda değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolu ile. Bu kod, XMP meta verilerini PDF belgesinden çıkaracak ve konsola çıkaracaktır.