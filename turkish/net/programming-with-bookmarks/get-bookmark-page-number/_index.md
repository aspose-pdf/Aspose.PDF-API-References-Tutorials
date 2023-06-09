---
title: Yer İşareti Sayfa Numarasını Alın
linktitle: Yer İşareti Sayfa Numarasını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınızdan yer imi sayfa numaralarını kolayca alın.
type: docs
weight: 60
url: /tr/net/programming-with-bookmarks/get-bookmark-page-number/
---

Bir PDF belgesindeki yer imleriyle ilişkili sayfa numaralarını almak, gezinme için yararlı olabilir. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek yer imlerinin sayfa numarasını kolayca alabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf.Facades;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, yer imi sayfa numaralarını çıkarmak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: Yer imi düzenleyicisini oluşturun

 Şimdi bir oluşturacağız`PdfBookmarkEditor` belgenin yer imlerini değiştirmek için nesne. Aşağıdaki kodu kullanın:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Adım 4: PDF Dosyasını Açın

 Bu adımda, PDF dosyasını kullanarak açıyoruz.`BindPdf` yer imi düzenleyicisinin yöntemi. İşte ilgili kod:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## 5. Adım: Yer işaretlerini çıkarın

 Şimdi, yer imlerini kullanarak belgeden çıkaracağız.`ExtractBookmarks` yer imi düzenleyicisinin yöntemi. İşte ilgili kod:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## 6. Adım: Yer imlerine göz atın ve sayfa numaralarını alın

 Son olarak, ayıklanan yer imleri arasında dolaşıyoruz ve her bir yer imi ile ilişkili sayfa numaralarını bir`foreach` döngü. İşte ilgili kod:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Aspose.PDF for .NET kullanarak Yer İşareti Sayfa Numarası Al için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PdfBookmarkEditor'u oluşturun
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// PDF dosyasını aç
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Yer imlerini ayıklayın
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile yer imi sayfa numaralarını almak için adım adım bir kılavuzunuz var. Bu kodu, PDF belgelerinizdeki her bir yer imi ile ilişkili gezinme bilgilerini almak için kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.