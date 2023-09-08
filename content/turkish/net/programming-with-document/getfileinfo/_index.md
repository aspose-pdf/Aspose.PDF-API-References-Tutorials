---
title: PDF Dosyasında Dosya Bilgisini Al
linktitle: PDF Dosyasında Dosya Bilgisini Al
second_title: .NET API Referansı için Aspose.PDF
description: Bir PDF belgesi hakkında meta veri bilgilerini almak için Aspose.PDF for .NET'in PDF dosyasında GetFileInfo özelliğini nasıl kullanacağınızı öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF dosyaları oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan popüler bir PDF işleme kitaplığıdır. Bu kitaplığın sunduğu özelliklerden biri, PDF belgesinin meta verileri hakkında bilgi alma yeteneğidir. Bu eğitim, kullanımın adımları konusunda size rehberlik edecektir.`GetFileInfo` Aspose.PDF for .NET'in bir PDF belgesinin meta verileri hakkında bilgi alma özelliği.

## Adım 1: Aspose.PDF for .NET'i yükleyin

 Aspose.PDF for .NET'i .NET uygulamalarınızda kullanmak için öncelikle kütüphaneyi kurmanız gerekir. Kütüphanenin en son sürümünü adresinden indirebilirsiniz.[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net).

Kütüphaneyi indirdikten sonra ZIP dosyasının içeriğini bilgisayarınızdaki bir klasöre çıkarın. Daha sonra .NET projenize Aspose.PDF for .NET DLL dosyasına bir referans eklemeniz gerekecektir.

## Adım 2: PDF Belgesini Yükleyin

Aspose.PDF for .NET'i yükledikten ve .NET projenize DLL'ye bir referans ekledikten sonra, kullanmaya başlayabilirsiniz.`GetFileInfo` PDF belgesinin meta verileri hakkında bilgi alma özelliği.

Bu özelliği kullanmanın ilk adımı, hakkında bilgi almak istediğiniz PDF belgesini yüklemektir. Bunu yapmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// PDF belgesinin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF belgesini açın
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Yukarıdaki kodda değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolu ile birlikte. Bu kod, PDF belgesini bir`Document` daha sonra belgenin meta verileri hakkında bilgi almak için kullanabileceğiniz nesne.

## 3. Adım: Belgenin Meta Verilerini Alın

Bir PDF belgesinin meta verileri hakkında bilgi almak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// Belge bilgilerini alın
DocumentInfo docInfo = pdfDocument.Info;

// Belge bilgilerini göster
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

Yukarıdaki kodda, her satır PDF belgesinin farklı bir meta veri özelliğini alır ve bunu konsola çıkarır. Yalnızca ilgilendiğiniz özellikleri almak için bu kodu özelleştirebilirsiniz.

### Örnek kaynak kodu, Aspose.PDF for .NET'i kullanarak PDF dosyası bilgilerini alma

 Burada, PDF belgesinin meta verilerini almak için kullanılan kaynak kodun tamamı bulunmaktadır.`GetFileInfo` Aspose.PDF for .NET'in özelliği:

```csharp
// PDF belgesinin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF belgesini açın
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Belge bilgilerini alın
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

Bu eğitimde, bir PDF belgesinin meta verileri hakkında bilgi almak için Aspose.PDF for .NET'in nasıl kullanılacağını tartıştık. Bir PDF belgesi yükleyerek ve meta veri özelliklerine erişerek belgenin özellikleri ve özellikleri hakkında bilgi toplayabilirsiniz. Aspose.PDF for .NET, meta veri bilgilerinin alınması da dahil olmak üzere PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar ve bu da onu .NET uygulamalarında PDF manipülasyonu için değerli bir araç haline getirir.

### SSS'ler

#### S: PDF belgesindeki meta veriler nedir?

C: Bir PDF belgesindeki meta veriler, belgenin özelliklerini ve özelliklerini açıklayan bilgileri ifade eder. Bu bilgiler genellikle belgenin başlığını, yazarını, konusunu, anahtar sözcüklerini, oluşturulma tarihini, değiştirilme tarihini ve daha fazlasını içerir.

#### S: Aspose.PDF for .NET'i .NET projeme nasıl kurabilirim?

 C: Aspose.PDF for .NET'i kurmak için kütüphaneyi şuradan indirmeniz gerekir:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net). İndirdikten sonra ZIP dosyasının içeriğini çıkarın ve .NET projenize Aspose.PDF for .NET DLL dosyasına bir referans ekleyin.

#### S: Kodu yalnızca belirli meta veri özelliklerini alacak şekilde özelleştirebilir miyim?

C: Evet, ihtiyacınız olmayan satırlara yorum ekleyerek belirli meta veri özelliklerini almak için kodu özelleştirebilirsiniz. Koddaki her satır belirli bir meta veri özelliğine karşılık gelir; böylece gereksinimlerinize göre özellikleri dahil edebilir veya hariç tutabilirsiniz.

#### S: Aspose.PDF for .NET'i kullanarak ne tür meta veri özelliklerini alabilirim?

C: Aspose.PDF for .NET'i kullanarak bir PDF belgesinin yazar, başlık, konu, anahtar kelimeler, oluşturulma tarihi ve değiştirilme tarihi dahil olmak üzere çeşitli meta veri özelliklerini alabilirsiniz.