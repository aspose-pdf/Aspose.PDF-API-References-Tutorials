---
title: PDF Özelliklerini Alın
linktitle: PDF Özelliklerini Alın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak kutu boyutları ve döndürme gibi PDF özelliklerini elde etmek için adım adım kılavuz.
type: docs
weight: 100
url: /tr/net/programming-with-pdf-pages/get-properties/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF'nin özelliklerini elde etmek için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.PDF for .NET'i kullanarak bir PDF sayfasının resim kutusu, kırpma kutusu, kırpma kutusu vb. gibi farklı özelliklerine nasıl erişeceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET, geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini ayarlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, özelliklerini almak istediğiniz PDF dosyasının konumudur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini açın
 Daha sonra, PDF belgesini kullanarak açmanız gerekir.`Document` Aspose.PDF sınıfı. PDF dosyasının doğru yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## 3. Adım: Sayfa Koleksiyonuna Erişin
 Artık belgenin sayfa koleksiyonuna şunu kullanarak erişebilirsiniz:`Pages` mülkiyeti`pdfDocument` nesne.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4. Adım: Belirli bir sayfaya gidin
Daha sonra koleksiyondaki sayfanın dizinini kullanarak belirli bir sayfaya atlayabilirsiniz. Aşağıdaki örnekte ikinci sayfaya (indeks 1) erişiyoruz.

```csharp
Page pdfPage = pageCollection[1];
```

## 5. Adım: Sayfa özelliklerini alın
 Artık PDF sayfasının resim kutusu, kırpma kutusu, kırpma kutusu vb. gibi farklı özelliklerini, PDF sayfasının ilgili özelliklerini kullanarak elde edebilirsiniz.`pdfPage` nesne.

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

### Aspose.PDF for .NET kullanarak Get Properties için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Sayfa koleksiyonunu alın
PageCollection pageCollection = pdfDocument.Pages;
// Belirli bir sayfayı al
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
Tebrikler! Aspose.PDF for .NET kullanarak bir PDF'nin özelliklerini başarıyla elde ettiniz. Bir PDF belgesini nasıl açacağınızı, belirli bir sayfaya nasıl gideceğinizi ve boyut kutuları ve döndürme gibi çeşitli sayfa özelliklerini nasıl alacağınızı öğrendiniz. Artık bu bilgiyi, PDF dosyalarınızın özelliklerine göre işlenmesini özelleştirmek için kullanabilirsiniz.

Gelişmiş özellikler ve kişiselleştirme olanakları hakkında daha fazla bilgi için resmi Aspose.PDF for .NET belgelerine göz atmayı unutmayın.

### SSS'ler

#### S: Aspose.PDF for .NET kullanarak bir PDF'nin özelliklerini nasıl edinebilirim?

C: Aspose.PDF for .NET kullanarak bir PDF'nin özelliklerini almak için şu adımları takip edebilirsiniz:

1. Özelliklerini almak istediğiniz PDF dosyasının yolunu belirterek belge dizinini ayarlayın.
2.  PDF belgesini kullanarak açın.`Document` Aspose.PDF sınıfı, PDF dosyasının doğru yolunu sağlar.
3.  kullanarak belgenin sayfa koleksiyonuna erişin.`Pages` mülkiyeti`pdfDocument` nesne.
4. Koleksiyondaki sayfanın dizinini kullanarak belirli bir sayfaya atlayın (dizin oluşturma 1'den başlar).
5.  İlgili özellikleri kullanarak PDF sayfasının ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number ve Rotation gibi farklı özelliklerini elde edin.`pdfPage` nesne.

#### S: Aspose.PDF for .NET kullanarak alabileceğim bir PDF sayfasının farklı özellikleri nelerdir?

C: Aspose.PDF for .NET'i kullanarak bir PDF sayfasının çeşitli özelliklerini alabilirsiniz, örneğin:

- ArtBox: Sayfanın resminin boyutlarını temsil eder.
- BleedBox: Sayfanın taşma payının boyutlarını temsil eder.
- CropBox: Sayfanın kırpıldıktan sonra görünen içeriğinin boyutlarını temsil eder.
- MediaBox: Sayfanın fiziksel ortamının boyutlarını temsil eder.
- TrimBox: Sayfanın kırpılan içeriğinin boyutlarını temsil eder.
- Dikdörtgen: Sayfanın sınırlayıcı kutusunun boyutlarını temsil eder.
- Sayfa Numarası: Dokümandaki sayfa numarasını temsil eder.
- Döndür: Sayfanın dönme açısını temsil eder.

#### S: Özelliklerini almak için PDF belgesindeki belirli bir sayfaya nasıl erişirim?

 C: PDF belgesindeki belirli bir sayfaya erişmek ve özelliklerini almak için`Pages` mülkiyeti`pdfDocument` belgenin sayfa koleksiyonuna erişmek için nesne. Daha sonra istediğiniz sayfaya atlamak için koleksiyondaki sayfanın dizinini kullanabilirsiniz. Örneğin ikinci sayfaya erişmek için şunu kullanabilirsiniz:`pdfDocument.Pages[1]` (indeksleme 1'den başlar).

#### S: Alınan özellikler üzerinde sayfa kutularını değiştirmek veya yeniden boyutlandırmak gibi işlemler gerçekleştirebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak bir PDF sayfasının özelliklerini aldığınızda, bunlar üzerinde çeşitli işlemler gerçekleştirebilirsiniz. Örneğin, sayfa kutularının boyutlarını değiştirebilir, sayfayı döndürebilir veya alınan bilgileri PDF belgesinin özel işlenmesi ve işlenmesi için kullanabilirsiniz.

#### S: Aspose.PDF for .NET, şifrelenmiş veya parola korumalı PDF dosyalarından özellik çıkarmayı destekliyor mu?

C: Evet, Aspose.PDF for .NET, şifrelenmiş veya parola korumalı PDF dosyalarından özelliklerin çıkarılmasını destekler. PDF belgesini açmak için doğru parolayı sağladığınız sürece, eğitimde gösterilen yaklaşımın aynısını kullanarak belgenin özelliklerine erişebilir ve bunları alabilirsiniz.