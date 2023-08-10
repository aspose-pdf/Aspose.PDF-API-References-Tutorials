---
title: PDF Dosyasında Dosya Bilgilerini Ayarla
linktitle: PDF Dosyasında Dosya Bilgilerini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET'i kullanarak PDF dosyasındaki dosya bilgilerini nasıl kullanacağınızı öğrenin.
type: docs
weight: 310
url: /tr/net/programming-with-document/setfileinfo/
---
Aspose.PDF for .NET kullanarak PDF dosyalarını yönetmeyi gerektiren bir proje üzerinde çalışıyorsanız, kullanmak isteyebileceğiniz özelliklerden biri, bir PDF belgesi için dosya bilgilerini ayarlama yeteneğidir. Dosya bilgileri, yazar, oluşturma tarihi, anahtar sözcükler, değiştirilme tarihi, konu ve başlık gibi çeşitli ayrıntıları içerir. Bu kılavuz, Aspose.PDF for .NET ile C# kaynak kodunu kullanarak bir PDF belgesi için dosya bilgilerini ayarlama sürecinde size yol gösterecektir.

## Aspose.PDF for .NET kullanarak dosya bilgilerini ayarlamak için adım adım kılavuz

1. Visual Studio IDE'nizde yeni bir C# projesi oluşturun.
2. Projenizde Aspose.PDF for .NET kitaplığına bir referans ekleyin.
3. Dosya bilgilerini değiştirmek istediğiniz PDF dosyasının yolunu sağlayarak yeni bir PDF belge nesnesi oluşturun.

## Adım 1: Belgeler dizinine giden yolu ayarlayın.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF belgesini açın

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Adım 3: PDF belgesinin dosya bilgilerine erişmek için DocumentInfo nesnesini kullanın.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Adım 4: DocumentInfo nesnesinin özelliklerini kullanarak istenen dosya bilgisi değerlerini ayarlayın.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Adım 5: Güncellenmiş PDF belgesini belirtilen konuma kaydedin.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Adım 6: Dosya bilgilerinin başarıyla güncellendiğini doğrulayın.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Aspose.PDF for .NET kullanarak bir PDF belgesi için dosya bilgilerini başarıyla ayarladınız.

### Aspose.PDF for .NET kullanarak Set File Info için örnek kaynak kodu


```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Belge bilgilerini belirtin
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Çözüm

Sonuç olarak, Aspose.PDF for .NET, PDF belgeleri için dosya bilgilerini ayarlamanın basit ve etkili bir yolunu sunar. Yukarıda belirtilen adımları izleyerek, C# kaynak kodunu kullanarak PDF belgeleriniz için istediğiniz dosya bilgisi değerlerini kolayca ayarlayabilirsiniz.

### PDF dosyasında ayarlanan dosya bilgileri için SSS

#### S: Örnekte belirtilmeyen ek dosya bilgisi özelliklerini ayarlayabilir miyim?

 A: Evet, kullanarak ek dosya bilgisi özellikleri ayarlayabilirsiniz.`DocumentInfo` Aspose.PDF for .NET'te nesne. bu`DocumentInfo`class, üretici, sürüm ve özel özellikler gibi ek bilgiler ayarlamanıza izin veren çeşitli özellikler sağlar.

#### S: Dosya bilgilerini mevcut bir PDF belgesinden almak mümkün müdür?

 C: Evet, Aspose.PDF for .NET'i kullanarak mevcut bir PDF belgesinden dosya bilgilerini alabilirsiniz. Bunu yapmak için,`DocumentInfo` dosya bilgileri özelliklerine erişmek ve PDF belgesinde saklanan bilgileri okumak için nesne.

#### S: Dosya bilgilerinin ayarlanması orijinal PDF belgesini değiştirir mi?

C: Hayır, Aspose.PDF for .NET kullanılarak dosya bilgilerinin ayarlanması orijinal PDF belgesini değiştirmez. Bunun yerine, güncellenmiş dosya bilgileriyle yeni bir PDF belgesi oluşturur. Orijinal PDF belgesi değişmeden kalır.