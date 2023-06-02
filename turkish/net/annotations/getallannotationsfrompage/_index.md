---
title: Sayfadan Tüm Ek Açıklamaları Alın
linktitle: Sayfadan Tüm Ek Açıklamaları Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile bir PDF sayfasından tüm açıklamaları almak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 70
url: /tr/net/annotations/getallannotationsfrompage/
---
Bu makale, Aspose.PDF for .NET kullanarak bir PDF sayfasından tüm ek açıklamaları çıkarma sürecinde size rehberlik edecektir. Aspose.PDF for .NET, geliştiricilerin PDF belgeleri oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan bir kitaplıktır. Bu kılavuzun yardımıyla, sağlanan C# kaynak kodunu kullanarak belirli bir PDF sayfasından tüm ek açıklamaları alabileceksiniz.

Aspose.PDF for .NET kullanarak bir PDF sayfası için tüm Ek Açıklamaları almak için aşağıdaki adımları izleyin:

## 1. Adım: Belgeler Dizinine Giden Yol

Aspose.PDF for .NET kullanarak bir PDF sayfasından tüm açıklamaları almanın ilk adımı, PDF dosyalarınızın saklandığı belgeler dizinine giden yolu ayarlamaktır. Aşağıdaki kod satırını değiştirerek bunu yapabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## 2. Adım: PDF dosyalarınız saklanır

"BELGE DİZİNİNİZ"i, PDF dosyalarınızın saklandığı klasörün yolu ile değiştirin. Örneğin:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## 3. Adım: Belgeyi Açın

Bir sonraki adım, çıkartmak istediğiniz ek açıklamaları içeren PDF belgesini açmaktır. Bunu aşağıdaki kodu ekleyerek yapabilirsiniz:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

Bu kod satırı Document sınıfının yeni bir örneğini başlatır ve "GetAllAnnotationsFromPage.pdf" PDF belgesini yükler. Bu dosya adını PDF dosyanızın adıyla değiştirin.

## 4. Adım: Tüm Ek Açıklamalar arasında geçiş yapın

PDF belgesini açtıktan sonra, belirli bir sayfadaki tüm ek açıklamalar arasında geçiş yapabilirsiniz. Örneğin, PDF belgesinin ilk sayfasındaki tüm açıklamalar arasında geçiş yapmak için aşağıdaki kodu ekleyin:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Kod buraya gelecek
}
```

Bu kod, PDF belgesinin ilk sayfasındaki tüm açıklamalar arasında dolaşır ve her açıklamayı "açıklama" değişkenine atar.

## Adım 5: Ek Açıklama Özelliklerini Alın

Her ek açıklamanın özelliklerini ayıklamak için foreach döngüsünün içine aşağıdaki kodu ekleyebilirsiniz:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

Bu kod, konsola her açıklamanın Başlığını, Konusunu ve İçeriğini yazar.

### Aspose.PDF for .NET kullanarak Sayfadan Tüm Açıklamaları Al için Örnek Kaynak Kodu

Aspose.PDF for .NET kullanarak bir PDF sayfasından tüm açıklamaları almak için eksiksiz kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// Tüm ek açıklamalar arasında dolaşın
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// Ek açıklama özelliklerini al
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```
