---
title: PDF Dosyasında Dosya Bilgilerini Alın
linktitle: PDF Dosyasında Dosya Bilgilerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'in PDF dosyasında GetFileInfo özelliğinin bir PDF belgesi hakkında meta veri bilgilerini almak için nasıl kullanılacağını öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF dosyaları oluşturmasını, düzenlemesini ve dönüştürmesini sağlayan popüler bir PDF düzenleme kütüphanesidir. Bu kütüphanenin sunduğu özelliklerden biri de bir PDF belgesinin meta verileri hakkında bilgi alabilme yeteneğidir. Bu eğitim, sizi kullanma adımlarında yönlendirecektir`GetFileInfo` Aspose.PDF for .NET'in bir PDF belgesinin meta verileri hakkında bilgi alma özelliği.

## Adım 1: .NET için Aspose.PDF'yi yükleyin

 .NET uygulamalarınızda Aspose.PDF for .NET'i kullanmak için önce kütüphaneyi yüklemeniz gerekir. Kütüphanenin en son sürümünü şu adresten indirebilirsiniz:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net).

Kütüphaneyi indirdikten sonra, ZIP dosyasının içeriğini bilgisayarınızdaki bir klasöre çıkarın. Daha sonra .NET projenizde Aspose.PDF for .NET DLL'sine bir referans eklemeniz gerekecektir.

## Adım 2: PDF Belgesini Yükleyin

 Aspose.PDF for .NET'i yükledikten ve .NET projenize DLL'ye bir başvuru ekledikten sonra, kullanmaya başlayabilirsiniz.`GetFileInfo` Bir PDF belgesinin meta verileri hakkında bilgi almaya yarayan özellik.

Bu özelliği kullanmanın ilk adımı, hakkında bilgi almak istediğiniz PDF belgesini yüklemektir. Bunu yapmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini açın
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Yukarıdaki kodda şunu değiştirin:`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kod. Bu kod PDF belgesini bir`Document` Daha sonra belgenin meta verileri hakkında bilgi almak için kullanabileceğiniz nesne.

## Adım 3: Belgenin Meta Verilerini Alın

Bir PDF belgesinin meta verileri hakkında bilgi almak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// Belge bilgilerini al
DocumentInfo docInfo = pdfDocument.Info;

// Belge bilgilerini göster
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

Yukarıdaki kodda, her satır PDF belgesinin farklı bir meta veri özelliğini alır ve bunu konsola çıktı olarak verir. Bu kodu yalnızca ilgilendiğiniz özellikleri alacak şekilde özelleştirebilirsiniz.

### Örnek kaynak kodu, .NET için Aspose.PDF kullanarak PDF dosya bilgilerini alır

 İşte PDF belgesinin meta verilerini almak için tam kaynak kodu:`GetFileInfo` Aspose.PDF for .NET'in özelliği:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini açın
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Belge bilgilerini al
DocumentInfo docInfo = pdfDocument.Info;

// Belge bilgilerini göster
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Çözüm

Bu eğitimde, bir PDF belgesinin meta verileri hakkında bilgi almak için Aspose.PDF for .NET'in nasıl kullanılacağını ele aldık. Bir PDF belgesini yükleyerek ve meta veri özelliklerine erişerek, belgenin özellikleri ve karakteristikleri hakkında bilgi toplayabilirsiniz. Aspose.PDF for .NET, meta veri bilgilerini almak da dahil olmak üzere PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar ve bu da onu .NET uygulamalarında PDF düzenleme için değerli bir araç haline getirir.

### SSS

#### S: PDF belgesinde meta veri nedir?

A: Bir PDF belgesindeki meta veriler, belgenin özelliklerini ve karakteristiklerini tanımlayan bilgileri ifade eder. Bu bilgiler genellikle belgenin başlığını, yazarını, konusunu, anahtar sözcüklerini, oluşturma tarihini, değiştirme tarihini ve daha fazlasını içerir.

#### S: .NET projemde Aspose.PDF for .NET'i nasıl kurabilirim?

 A: .NET için Aspose.PDF'yi yüklemek için, kütüphaneyi şu adresten indirmeniz gerekir:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net). İndirdikten sonra, ZIP dosyasının içeriğini çıkarın ve .NET projenize Aspose.PDF for .NET DLL'sine bir referans ekleyin.

#### S: Kodu yalnızca belirli meta veri özelliklerini alacak şekilde özelleştirebilir miyim?

A: Evet, ihtiyacınız olmayan satırları yorumlayarak belirli meta veri özelliklerini almak için kodu özelleştirebilirsiniz. Koddaki her satır belirli bir meta veri özelliğine karşılık gelir, böylece gereksinimlerinize göre özellikleri dahil edebilir veya hariç tutabilirsiniz.

#### S: Aspose.PDF for .NET kullanarak hangi tür meta veri özelliklerini alabilirim?

A: Aspose.PDF for .NET'i kullanarak, yazar, başlık, konu, anahtar sözcükler, oluşturulma tarihi ve değiştirilme tarihi dahil olmak üzere bir PDF belgesinin çeşitli meta veri özelliklerini alabilirsiniz.