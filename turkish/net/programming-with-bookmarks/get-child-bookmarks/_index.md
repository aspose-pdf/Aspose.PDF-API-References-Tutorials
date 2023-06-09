---
title: Alt Yer İşaretlerini Alın
linktitle: Alt Yer İşaretlerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınızın alt yer imlerini kolayca alın.
type: docs
weight: 80
url: /tr/net/programming-with-bookmarks/get-child-bookmarks/
---

Alt yer imlerini bir PDF belgesinden almak, yer imlerinin hiyerarşik yapısını keşfetmek için yararlı olabilir. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek alt yer imlerini kolayca alabilirsiniz:

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
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## 4. Adım: Yer imlerine ve alt yer imlerine göz atın

Bu adımda, belgedeki tüm yer imlerini bir aparat kullanarak yineleyeceğiz.`foreach`döngü. Her yer imi için başlık, italik stil, kalın stil ve renk gibi bilgileri göstereceğiz. Yer iminde alt yer imleri varsa bunları da gösteririz. İşte ilgili kod:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // Alt yer imlerine de göz atın
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### Aspose.PDF for .NET kullanarak Alt Yer İmlerini Getir için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// Tüm yer imleri arasında dolaş
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// Alt yer imleri var, sonra bunun içinden de geç
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile alt yer imlerini almak için adım adım bir kılavuzunuz var. Bu kodu, yer imlerinin hiyerarşik yapısını keşfetmek ve PDF belgelerinizdeki her bir yer imi ve onun alt yer imi hakkında ayrıntılı bilgi almak için kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.