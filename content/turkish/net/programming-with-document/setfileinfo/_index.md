---
title: PDF Dosyasında Dosya Bilgilerini Ayarla
linktitle: PDF Dosyasında Dosya Bilgilerini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET'i kullanarak PDF dosyasındaki dosya bilgilerini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 310
url: /tr/net/programming-with-document/setfileinfo/
---
Aspose.PDF for .NET kullanarak PDF dosyalarını yönetmeyi gerektiren bir proje üzerinde çalışıyorsanız, kullanmak isteyebileceğiniz özelliklerden biri PDF belgesi için dosya bilgilerini ayarlama yeteneğidir. Dosya bilgileri yazar, oluşturma tarihi, anahtar sözcükler, değişiklik tarihi, konu ve başlık gibi çeşitli ayrıntıları içerir. Bu kılavuz, Aspose.PDF for .NET ile C# kaynak kodunu kullanarak PDF belgesi için dosya bilgilerini ayarlama sürecinde size yol gösterecektir.

## Aspose.PDF for .NET kullanarak dosya bilgilerini ayarlamaya yönelik adım adım kılavuz

1. Visual Studio IDE'nizde yeni bir C# projesi oluşturun.
2. Projenize Aspose.PDF for .NET kütüphanesine bir referans ekleyin.
3. Dosya bilgilerini değiştirmek istediğiniz PDF dosyasının yolunu sağlayarak yeni bir PDF belge nesnesi oluşturun.

## Adım 1: Belgeler dizinine giden yolu ayarlayın.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF belgesini açın

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Adım 3: PDF belgesinin dosya bilgilerine erişmek için DocumentInfo nesnesini kullanın.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Adım 4: DocumentInfo nesnesinin özelliklerini kullanarak istenilen dosya bilgisi değerlerini ayarlayın.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Adım 5: Güncellenen PDF belgesini belirtilen konuma kaydedin.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Adım 6: Dosya bilgilerinin başarıyla güncellendiğini doğrulayın.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Aspose.PDF for .NET kullanarak bir PDF belgesi için dosya bilgilerini başarıyla ayarladınız.

### .NET için Aspose.PDF kullanarak Set File Info için örnek kaynak kodu


```csharp
// Belgeler dizinine giden yol.
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
// Çıktı belgesini kaydet
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Çözüm

Sonuç olarak, Aspose.PDF for .NET, PDF belgeleri için dosya bilgilerini ayarlamanın basit ve etkili bir yolunu sağlar. Yukarıda belirtilen adımları izleyerek, C# kaynak kodunu kullanarak PDF belgeleriniz için istediğiniz dosya bilgisi değerlerini kolayca ayarlayabilirsiniz.

### PDF dosyasındaki set dosyası bilgilerine ilişkin SSS

#### S: Örnekte belirtilmeyen ek dosya bilgisi özelliklerini ayarlayabilir miyim?

 A: Evet, ek dosya bilgisi özelliklerini kullanarak ayarlayabilirsiniz.`DocumentInfo` .NET için Aspose.PDF'deki nesne.`DocumentInfo`sınıf, üretici, sürüm ve özel özellikler gibi ek bilgileri ayarlamanıza olanak tanıyan çeşitli özellikler sağlar.

#### S: Mevcut bir PDF belgesinden dosya bilgilerini almak mümkün müdür?

 A: Evet, Aspose.PDF for .NET kullanarak mevcut bir PDF belgesinden dosya bilgilerini alabilirsiniz. Bunu yapmak için,`DocumentInfo` PDF belgesinde saklanan bilgileri okumak ve dosya bilgi özelliklerine erişmek için kullanılan nesne.

#### S: Dosya bilgilerini ayarlamak orijinal PDF belgesini değiştirir mi?

A: Hayır, Aspose.PDF for .NET kullanarak dosya bilgilerini ayarlamak orijinal PDF belgesini değiştirmez. Bunun yerine, güncellenmiş dosya bilgileriyle yeni bir PDF belgesi oluşturur. Orijinal PDF belgesi değişmeden kalır.