---
title: Tüm Yer İşaretlerini Sil
linktitle: Tüm Yer İşaretlerini Sil
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınızdaki tüm yer imlerini kolayca silin.
type: docs
weight: 30
url: /tr/net/programming-with-bookmarks/delete-all-bookmarks/
---

# Aspose.PDF for .NET ile tüm yer imlerini silin

Bir PDF belgesinden yer imlerinin silinmesi bazı durumlarda gerekli olabilir. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek tüm yer imlerini kolayca kaldırabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, yer imlerini kaldırmak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi yer imlerini kaldırmak istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## 4. Adım: Tüm yer imlerini silin

 Bu adımda, kullanarak belgedeki tüm yer imlerini siliyoruz.`Delete` yöntemi`Outlines` mülk. İşte ilgili kod:

```csharp
pdfDocument.Outlines.Delete();
```

## 5. Adım: Güncellenen dosyayı kaydedin

 Son olarak, güncellenmiş PDF dosyasını kullanarak kaydediyoruz.`Save` yöntemi`pdfDocument` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Tüm Yer İşaretlerini Sil için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Tüm yer imlerini sil
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Güncellenen dosyayı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile tüm yer imlerini kaldırmak için adım adım bir kılavuzunuz var. Mevcut tüm yer imlerini silerek PDF belgelerinizi temizlemek için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.