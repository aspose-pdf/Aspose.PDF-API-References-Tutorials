---
title: PDF Dosyasında Dosya Bilgilerini Alın
linktitle: PDF Dosyasında Dosya Bilgilerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'in PDF dosyasında GetFileInfo özelliğinin bir PDF belgesi hakkında meta veri bilgilerini almak için nasıl kullanılacağını öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-document/getfileinfo/
---
Aspose.PDF for .NET, geliştiricilerin kendi .NET uygulamalarında PDF dosyaları oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan popüler bir PDF işleme kitaplığıdır. Bu kitaplığın sunduğu özelliklerden biri, bir PDF belgesinin meta verileri hakkında bilgi alma yeteneğidir. Bu öğretici, kullanımın adımlarında size rehberlik edecektir.`GetFileInfo` Aspose.PDF for .NET'in bir PDF belgesinin meta verileri hakkında bilgi alma özelliği.

## 1. Adım: Aspose.PDF for .NET'i kurun

 Aspose.PDF for .NET'i .NET uygulamalarınızda kullanmak için önce kütüphaneyi kurmalısınız. Kütüphanenin en son sürümünü adresinden indirebilirsiniz.[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net).

Kitaplığı indirdikten sonra, ZIP dosyasının içeriğini bilgisayarınızdaki bir klasöre çıkarın. Ardından, .NET projenizde Aspose.PDF for .NET DLL'ye bir referans eklemeniz gerekecektir.

## 2. Adım: PDF Belgesini Yükleyin

 Aspose.PDF for .NET'i yükledikten ve .NET projenize DLL'ye bir referans ekledikten sonra,`GetFileInfo` PDF belgesinin meta verileri hakkında bilgi alma özelliği.

Bu özelliği kullanmanın ilk adımı, hakkında bilgi almak istediğiniz PDF belgesini yüklemektir. Bunu yapmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF belgesini aç
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Yukarıdaki kodda değiştirin`"YOUR DOCUMENT DIRECTORY"`PDF belgenizin bulunduğu dizinin yolu ile. Bu kod, PDF belgesini bir`Document` daha sonra belgenin meta verileri hakkında bilgi almak için kullanabileceğiniz nesne.

## 3. Adım: Belgenin Meta Verilerini Alın

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

Yukarıdaki kodda, her satır PDF belgesinin farklı bir meta veri özelliğini alır ve onu konsola verir. Yalnızca ilgilendiğiniz özellikleri almak için bu kodu özelleştirebilirsiniz.

### Örnek kaynak kodu, Aspose.PDF for .NET kullanarak PDF dosyası bilgilerini alın

 Bir PDF belgesinin meta verilerini almak için tam kaynak kodunu burada bulabilirsiniz.`GetFileInfo` Aspose.PDF for .NET özelliği:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF belgesini aç
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

Bu eğitimde, Aspose.PDF for .NET'in bir PDF belgesinin meta verileri hakkında bilgi almak için nasıl kullanılacağını tartıştık. Bir PDF belgesi yükleyerek ve meta veri özelliklerine erişerek, belgenin özellikleri ve özellikleri hakkında bilgi toplayabilirsiniz. Aspose.PDF for .NET, meta veri bilgilerinin alınması da dahil olmak üzere PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar ve bu da onu .NET uygulamalarında PDF işleme için değerli bir araç haline getirir.

### SSS

#### S: Bir PDF belgesindeki meta veriler nedir?

Y: Bir PDF belgesindeki meta veriler, belgenin özelliklerini ve özelliklerini açıklayan bilgileri ifade eder. Bu bilgiler genellikle belgenin başlığını, yazarını, konusunu, anahtar sözcüklerini, oluşturma tarihini, değiştirilme tarihini ve daha fazlasını içerir.

#### S: Aspose.PDF for .NET'i .NET projeme nasıl kurabilirim?

 C: Aspose.PDF for .NET'i kurmak için kütüphaneyi şu adresten indirmeniz gerekir:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net)İndirdikten sonra, ZIP dosyasının içeriğini çıkartın ve .NET projenizde Aspose.PDF for .NET DLL'ye bir referans ekleyin.

#### S: Kodu yalnızca belirli meta veri özelliklerini alacak şekilde özelleştirebilir miyim?

C: Evet, ihtiyacınız olmayan satırları yorumlayarak belirli meta veri özelliklerini almak için kodu özelleştirebilirsiniz. Koddaki her satır, belirli bir meta veri özelliğine karşılık gelir, böylece gereksinimlerinize göre özellikleri dahil edebilir veya hariç tutabilirsiniz.

#### S: Aspose.PDF for .NET kullanarak ne tür meta veri özellikleri alabilirim?

C: Aspose.PDF for .NET'i kullanarak bir PDF belgesinin yazar, başlık, konu, anahtar sözcükler, oluşturma tarihi ve değiştirme tarihi gibi çeşitli meta veri özelliklerini alabilirsiniz.