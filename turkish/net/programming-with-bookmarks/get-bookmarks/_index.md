---
title: Yer İşaretlerini Alın
linktitle: Yer İşaretlerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınıza kolayca yer işareti koyun.
type: docs
weight: 70
url: /tr/net/programming-with-bookmarks/get-bookmarks/
---

Bir PDF belgesinden yer imlerini almak, belgenin yapısını ve gezinme bilgilerini analiz etmek için yararlı olabilir. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek yer imlerini kolayca alabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, yer imlerini çıkarmak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi yer imlerini çıkarmak istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
```

## 4. Adım: Yer İmlerine Göz Atın

Bu adımda, belgedeki tüm yer imlerini bir aparat kullanarak yineleyeceğiz.`foreach` döngü. Her yer imi için başlık, italik stil, kalın stil ve renk gibi bilgileri göstereceğiz. İşte ilgili kod:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
}
```

### Aspose.PDF for .NET kullanarak Get Bookmarks için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
// Tüm yer imleri arasında dolaş
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
}
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile yer imlerini almak için adım adım bir kılavuzunuz var. Bu kodu, yer imlerini ayrıştırmak ve PDF belgelerinizdeki her bir yer imi ile ilişkili bilgileri çıkarmak için kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.