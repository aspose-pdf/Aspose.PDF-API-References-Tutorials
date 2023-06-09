---
title: İmi eklemek
linktitle: İmi eklemek
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile gelişmiş gezinme için PDF dosyalarınıza kolayca yer imleri ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/add-bookmark/
---

Bir PDF belgesine yer imleri eklemek, kolay ve hızlı gezinme sağlar. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek kolayca bir yer imi ekleyebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, yer imi eklemek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi yer imi eklemek istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## 4. Adım: Yer imi nesnesi oluşturun

 Bu adımda, kullanarak bir yer imi nesnesi oluşturacağız.`OutlineItemCollection` sınıfını seçin ve başlık, italik nitelik, kalın nitelik ve tıklandığında gerçekleştirilecek eylem gibi özelliklerini ayarlayın. İşte ilgili kod:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## 5. Adım: Belgeye yer imi ekleyin

 Son olarak, oluşturulan yer imini kullanarak belgenin yer imi koleksiyonuna ekliyoruz.`Add` yöntemi`Outlines` mülk. İşte ilgili kod:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Aspose.PDF for .NET kullanarak Add Bookmark için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Bir yer imi nesnesi oluşturun
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Hedef sayfa numarasını ayarlayın
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Belgenin anahat koleksiyonuna yer imi ekleyin.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir yer imi eklemek için adım adım bir kılavuzunuz var. Bu kodu, özel yer imleri ekleyerek PDF belgelerinizde gezinmeyi iyileştirmek için kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.