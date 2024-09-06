---
title: PDF Özelliklerini Alın
linktitle: PDF Özelliklerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak kutu boyutları ve dönüş gibi PDF özelliklerini elde etmek için adım adım kılavuz.
type: docs
weight: 100
url: /tr/net/programming-with-pdf-pages/get-properties/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF'nin özelliklerini almak için adım adım süreci adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği kendi projelerinizde anlamanıza ve uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak sanat kutusu, kırpma kutusu, kırpma kutusu vb. gibi bir PDF sayfasının farklı özelliklerine nasıl erişeceğinizi öğreneceksiniz.

## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi
- Geliştirme ortamınıza .NET için Aspose.PDF yüklendi

## Adım 1: Belge dizinini ayarlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, özelliklerini almak istediğiniz PDF dosyasının konumudur. "YOUR DOCUMENTS DIRECTORY" ifadesini uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: PDF belgesini açın
 Daha sonra, PDF belgesini şu şekilde açmanız gerekir:`Document` Aspose.PDF sınıfı. PDF dosyasına doğru yolu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Adım 3: Sayfa Koleksiyonuna Erişim
 Artık belgenin sayfa koleksiyonuna şu şekilde erişebilirsiniz:`Pages` mülkiyeti`pdfDocument` nesne.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Adım 4: Belirli bir sayfaya gidin
Daha sonra koleksiyondaki sayfanın dizinini kullanarak belirli bir sayfaya atlayabilirsiniz. Aşağıdaki örnekte ikinci sayfaya (dizin 1) erişiyoruz.

```csharp
Page pdfPage = pageCollection[1];
```

## Adım 5: Sayfa özelliklerini alın
 Artık PDF sayfasının sanat kutusu, kırpma kutusu, kırpma kutusu vb. gibi farklı özelliklerini, ilgili özellikleri kullanarak elde edebilirsiniz.`pdfPage` nesne.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### .NET için Aspose.PDF kullanarak Get Properties için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Sayfa koleksiyonunu al
PageCollection pageCollection = pdfDocument.Pages;
// Belirli sayfayı al
Page pdfPage = pageCollection[1];
// Sayfa özelliklerini al
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Çözüm
Tebrikler! Aspose.PDF for .NET kullanarak bir PDF'nin özelliklerini başarıyla elde ettiniz. Bir PDF belgesini nasıl açacağınızı, belirli bir sayfaya nasıl gideceğinizi ve boyut kutuları ve dönüş gibi çeşitli sayfa özelliklerini nasıl elde edeceğinizi öğrendiniz. Artık bu bilgileri, PDF dosyalarınızın özelliklerine göre işlenmesini özelleştirmek için kullanabilirsiniz.

Gelişmiş özellikler ve özelleştirme olanakları hakkında daha fazla bilgi için resmi Aspose.PDF for .NET belgelerine göz atmayı unutmayın.

### SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF'nin özelliklerini nasıl alabilirim?

A: Aspose.PDF for .NET kullanarak bir PDF'nin özelliklerini almak için şu adımları izleyebilirsiniz:

1. Özelliklerini almak istediğiniz PDF dosyasının yolunu belirterek belge dizinini ayarlayın.
2.  PDF belgesini kullanarak açın`Document` Aspose.PDF sınıfı, PDF dosyasına doğru yolu sağlar.
3.  Belgenin sayfa koleksiyonuna erişmek için şunu kullanın:`Pages` mülkiyeti`pdfDocument` nesne.
4. Koleksiyondaki sayfanın dizinini kullanarak belirli bir sayfaya atlayın (indeksleme 1'den başlar).
5.  ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number ve Rotation gibi PDF sayfasının farklı özelliklerini, ilgili özellikleri kullanarak elde edin.`pdfPage` nesne.

#### S: Aspose.PDF for .NET kullanarak alabileceğim bir PDF sayfasının farklı özellikleri nelerdir?

A: Aspose.PDF for .NET kullanarak bir PDF sayfasının çeşitli özelliklerini alabilirsiniz, örneğin:

- ArtBox: Sayfanın görselinin boyutlarını gösterir.
- BleedBox: Sayfanın taşma boyutunu temsil eder.
- CropBox: Kırpma işleminden sonra sayfanın görünür içeriğinin boyutlarını temsil eder.
- MediaBox: Sayfanın fiziksel medyasının boyutlarını temsil eder.
- TrimBox: Sayfanın kırpılan içeriğinin boyutlarını temsil eder.
- Dikdörtgen: Sayfanın sınırlayıcı kutusunun boyutlarını temsil eder.
- Sayfa Numarası: Belgedeki sayfa numarasını gösterir.
- Döndür: Sayfanın dönüş açısını gösterir.

#### S: PDF belgesinde belirli bir sayfanın özelliklerini almak için o sayfaya nasıl erişebilirim?

 A: PDF belgesinde belirli bir sayfaya erişmek ve özelliklerini almak için şunu kullanabilirsiniz:`Pages` mülkiyeti`pdfDocument` nesneyi belgenin sayfa koleksiyonuna erişmek için kullanabilirsiniz. Daha sonra, koleksiyondaki sayfanın dizinini kullanarak istediğiniz sayfaya atlayabilirsiniz. Örneğin, ikinci sayfaya erişmek için kullanabilirsiniz`pdfDocument.Pages[1]` (indeksleme 1'den başlar).

#### S: Alınan özellikler üzerinde sayfa kutularını değiştirme veya yeniden boyutlandırma gibi işlemler yapabilir miyim?

A: Evet, Aspose.PDF for .NET kullanarak bir PDF sayfasının özelliklerini aldığınızda, bunlar üzerinde çeşitli işlemler gerçekleştirebilirsiniz. Örneğin, sayfa kutularının boyutlarını değiştirebilir, sayfayı döndürebilir veya alınan bilgileri PDF belgesinin özel işlenmesi ve düzenlenmesi için kullanabilirsiniz.

#### S: Aspose.PDF for .NET şifrelenmiş veya parola korumalı PDF dosyalarından özellik çıkarmayı destekliyor mu?

C: Evet, Aspose.PDF for .NET şifrelenmiş veya parola korumalı PDF dosyalarından özellikleri çıkarmayı destekler. PDF belgesini açmak için doğru parolayı sağladığınız sürece, eğitimde gösterilen aynı yaklaşımı kullanarak özelliklerine erişebilir ve bunları alabilirsiniz.