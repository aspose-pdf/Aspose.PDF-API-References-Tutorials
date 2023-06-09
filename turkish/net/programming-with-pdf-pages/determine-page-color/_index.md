---
title: Sayfa Rengini Belirle
linktitle: Sayfa Rengini Belirle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF sayfa rengini belirlemek için adım adım kılavuz. Her sayfanın renk türünü analiz edin ve görüntüleyin. Uygulaması kolay.
type: docs
weight: 40
url: /tr/net/programming-with-pdf-pages/determine-page-color/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF'nin sayfa rengini belirleme sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak bir PDF'nin sayfa rengini nasıl belirleyeceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, PDF dosyanızın bulunduğu konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF dosyasını açın
 Ardından, kullanarak analiz etmek için PDF dosyasını açabilirsiniz.`Document` Aspose.PDF sınıfı. PDF dosyasının doğru yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## 3. Adım: Sayfaları analiz edin
 Artık bir PDF belgesinin tüm sayfaları arasında dolaşabilirsiniz.`for` döngü. Her sayfa için, sayfanın renk türünü kullanarak alabilirsiniz.`ColorType` mülkiyeti`Page` nesne ve konsolda görüntüleyin.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     ColorType pageColorType = pdfDocument.Pages[pageCount].ColorType;
     switch(pageColorType)
     {
         box ColorType.BlackAndWhite:
             Console.WriteLine("Page #" + pageCount + " is black and white.");
             break;
         ColorType.Grayscale box:
             Console.WriteLine("Page #" + pageCount + " is grayscale.");
             break;
         box ColorType.Rgb:
             Console.WriteLine("Page #" + pageCount + " is in RGB colors.");
             break;
         box ColorType.Undefined:
             Console.WriteLine("Page #" + pageCount + " has undefined color.");
             break;
     }
}
```

### Aspose.PDF for .NET kullanarak Sayfa Rengini Belirlemek için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Açık kaynaklı PDF dosyası
Document pdfDocument = new Document( dataDir + "input.pdf");
//PDF dosyasının tüm sayfasını yineleyin
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	// Belirli bir PDF sayfası için renk türü bilgilerini alın
	Aspose.Pdf.ColorType pageColorType = pdfDocument.Pages[pageCount].ColorType;
	switch (pageColorType)
	{
		case ColorType.BlackAndWhite:
			Console.WriteLine("Page # -" + pageCount + " is Black and white..");
			break;
		case ColorType.Grayscale:
			Console.WriteLine("Page # -" + pageCount + " is Gray Scale...");
			break;
		case ColorType.Rgb:
			Console.WriteLine("Page # -" + pageCount + " is RGB..", pageCount);
			break;
		case ColorType.Undefined:
			Console.WriteLine("Page # -" + pageCount + " Color is undefined..");
			break;
	}
}

```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF'nin sayfa renginin nasıl belirleneceğini öğrendik. Yukarıda özetlenen adımları izleyerek, bu işlevi kendi projelerinize kolayca uygulayabilirsiniz. PDF dosyalarıyla çalışmaya yönelik diğer yararlı özellikleri keşfetmek için Aspose.PDF belgelerini daha fazla keşfetmekten çekinmeyin.