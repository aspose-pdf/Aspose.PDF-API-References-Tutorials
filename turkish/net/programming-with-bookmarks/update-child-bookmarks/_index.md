---
title: Alt Yer İşaretlerini Güncelle
linktitle: Alt Yer İşaretlerini Güncelle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınızdaki alt yer imlerini kolayca güncelleyin.
type: docs
weight: 110
url: /tr/net/programming-with-bookmarks/update-child-bookmarks/
---

Bir PDF belgesindeki alt yer imlerini güncellemek, bir üst yer imindeki belirli yer imlerinin özelliklerini değiştirmenize olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek alt yer imlerini kolayca güncelleyebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, güncellemek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi güncellemek istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## 4. Adım: Üst yer imi nesnesini alın

Bu adımda, alt yer imlerini güncellemek istediğimiz belirli üst yer imi nesnesini alacağız. Aşağıdaki örnekte, dizin 1'deki (yer işaretleri koleksiyonundaki ikinci yer işareti) üst yer işaretini alıyoruz. Endeksi ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## 5. Adım: Alt Yer İşareti Nesnesini Alın

Şimdi güncellemek istediğimiz belirli alt yer imi nesnesini alalım. Aşağıdaki örnekte, dizin 1'deki alt yer imini alıyoruz (üst yer iminin alt yer imleri koleksiyonundaki ikinci alt yer imi). Endeksi ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

## 6. Adım: Alt yer imi özelliklerini güncelleyin

Şimdi başlık, italik stil ve kalın stil gibi alt yer imi özelliklerini güncelleyelim. Bu özellikleri ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

```csharp
childOutline.Title = "Updated Outline";
childOutline. Italic = true;
childOutline. Bold = true;
```

## 7. Adım: Güncellenen dosyayı kaydedin

Şimdi güncellenmiş PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`pdfDocument` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Alt Yer İmlerini Güncellemek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Bir yer imi nesnesi al
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
// Alt yer imi nesnesini al
OutlineItemCollection childOutline = pdfOutline[1];
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
// Çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık alt yer imlerini Aspose.PDF for .NET ile güncellemek için adım adım bir kılavuza sahipsiniz. Bu kodu, PDF belgelerinizdeki alt yer imlerinin özelliklerini değiştirmek için kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.