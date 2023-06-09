---
title: Yer İşaretlerini Güncelle
linktitle: Yer İşaretlerini Güncelle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınızdaki yer imlerini kolayca güncelleyin.
type: docs
weight: 100
url: /tr/net/programming-with-bookmarks/update-bookmarks/
---

Belgenin yapısındaki veya içeriğindeki değişiklikleri veya güncellemeleri yansıtmak için bir PDF belgesindeki yer imlerini güncellemek genellikle gereklidir. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek yer imlerini kolayca güncelleyebilirsiniz:

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
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
```

## 4. Adım: Yer imi nesnesini alın

Bu adımda, güncellemek istediğimiz belirli yer imi nesnesini alacağız. Aşağıdaki örnekte, dizin 1'deki yer işaretini alıyoruz (yer işaretleri koleksiyonundaki ikinci yer işareti). Endeksi ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## 5. Adım: Yer imi özelliklerini güncelleyin

Şimdi başlık, italik stil ve kalın stil gibi yer imi özelliklerini güncelleyelim. Bu özellikleri ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

```csharp
pdfOutline.Title = "Updated Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## 6. Adım: Güncellenen dosyayı kaydedin

Şimdi güncellenmiş PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`pdfDocument` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "UpdateBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Yer İmlerini Güncellemek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
// Bir yer imi nesnesi al
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
pdfOutline.Title = "Updated Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
dataDir = dataDir + "UpdateBookmarks_out.pdf";
// Çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık yer imlerini Aspose.PDF for .NET ile güncellemek için adım adım bir kılavuza sahipsiniz. PDF belgelerinizdeki yer imlerinin başlıklarını ve stillerini değiştirmek için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.