---
title: Alt Yer İşareti Ekle
linktitle: Alt Yer İşareti Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile daha düzenli tarama için PDF dosyalarınıza kolayca alt yer imi ekleyin.
type: docs
weight: 20
url: /tr/net/programming-with-bookmarks/add-child-bookmark/
---

Bir PDF belgesine alt yer imleri eklemek, daha yapılandırılmış bir organizasyona ve gezinmeye olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek kolayca bir alt yer imi ekleyebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, alt yer imi eklemek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi aşağıdaki kodu kullanarak alt yer imi eklemek istediğimiz PDF belgesini açacağız:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## 4. Adım: Üst yer imi nesnesi oluşturun

 Bu adımda, kullanarak bir üst yer imi nesnesi oluşturacağız.`OutlineItemCollection` class ve başlık, italik nitelik ve kalın nitelik gibi özelliklerini ayarlayın. İşte ilgili kod:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## 5. Adım: Alt Yer İşareti Nesnesi Oluşturun

Bu adımda, kullanarak tekrar bir alt yer işareti nesnesi oluşturacağız.`OutlineItemCollection` sınıf ve özelliklerini ayarlayın. İşte ilgili kod:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## 6. Adım: Alt yer imini üst yer imine ekleyin

 Son olarak, oluşturulan alt yer işaretini ana yer işaretinin alt yer işareti koleksiyonuna`Add` üst nesnenin yöntemi. İşte ilgili kod:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## 7. Adım: Ana yer imini belgenin yer imi koleksiyonuna ekleyin

 Son olarak, ana yer imini belgenin yer imi koleksiyonuna şunu kullanarak ekliyoruz:`Add` yöntemi`Outlines` mülk. İşte ilgili kod:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Aspose.PDF for .NET kullanarak Add Child Bookmark için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Bir üst yer imi nesnesi oluşturun
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Bir alt yer imi nesnesi oluşturun
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Üst yer imi koleksiyonuna alt yer imi ekle
pdfOutline.Add(pdfChildOutline);
// Belgenin anahat koleksiyonuna ana yer imi ekleyin.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile bir alt yer imi eklemek için adım adım bir kılavuzunuz var. PDF belgelerinizdeki yer imlerinizi düzenlemek ve yapılandırmak için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.