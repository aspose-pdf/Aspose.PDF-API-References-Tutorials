---
title: PDF Dosyasında Yer İşareti Sayfa Numarasını Al
linktitle: PDF Dosyasında Yer İşareti Sayfa Numarasını Al
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasındaki yer imi sayfa numarasını kolayca alın.
type: docs
weight: 60
url: /tr/net/programming-with-bookmarks/get-bookmark-page-number/
---
PDF dosyasındaki yer imleriyle ilişkili sayfa numaralarının alınması, gezinme açısından yararlı olabilir. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek yer imlerinin sayfa numarasını kolayca alabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. Gerekli ithalat direktifi aşağıdadır:

```csharp
using Aspose.Pdf.Facades;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, yer imi sayfa numaralarını çıkarmak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: Yer imi düzenleyicisini oluşturun

 Şimdi bir oluşturacağız`PdfBookmarkEditor` Belgenin yer imlerini değiştirmek için nesne. Aşağıdaki kodu kullanın:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Adım 4: PDF Dosyasını Açın

 Bu adımda PDF dosyasını kullanarak açıyoruz.`BindPdf` yer imi düzenleyicisinin yöntemi. İşte ilgili kod:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## 5. Adım: Yer işaretlerini çıkarın

 Şimdi yer imlerini belgeden çıkaracağız.`ExtractBookmarks` yer imi düzenleyicisinin yöntemi. İşte ilgili kod:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## 6. Adım: Yer işaretlerine göz atın ve sayfa numaralarını alın

 Son olarak, çıkartılan yer imleri arasında dolaşıyoruz ve her bir yer imiyle ilişkili sayfa numaralarını bir`foreach` döngü. İşte ilgili kod:

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

### Aspose.PDF for .NET kullanarak Yer İşareti Sayfa Numarasını Al için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PdfYer İşareti Düzenleyicisi Oluştur
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// PDF dosyasını aç
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Yer imlerini çıkart
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

Tebrikler! Artık Aspose.PDF for .NET ile yer imi sayfa numaralarını almak için adım adım bir kılavuza sahipsiniz. PDF belgelerinizdeki her yer işaretiyle ilişkili gezinme bilgilerini almak için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### PDF dosyasındaki yer imi sayfa numarasını almak için SSS

#### S: PDF dosyasındaki yer işaretleri nedir?

C: Bir PDF dosyasındaki yer imleri, kullanıcıların belge içindeki belirli bölümlere veya sayfalara hızlı bir şekilde atlamasına olanak tanıyan gezinme yardımcılarıdır. İlgili içeriğe kısayollar sağlayarak kullanıcı deneyimini geliştirirler.

#### S: Neden bir PDF dosyasından yer imi sayfa numaralarını almak isteyeyim?

C: Yer imi sayfa numaralarının alınması, kullanıcıların bir belgede daha etkili bir şekilde gezinmesine yardımcı olur ve her bir yer iminin nereye gittiğine dair net bir gösterge sağlar. Bu, özellikle birden fazla bölümü olan daha uzun belgeler için kullanışlıdır.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarabilirim?

C: C# projeniz için gerekli kitaplığı içe aktarmak için aşağıdaki içe aktarma yönergesini kullanın:

```csharp
using Aspose.Pdf.Facades;
```

Bu yönerge Aspose.PDF for .NET tarafından sağlanan sınıfları ve yöntemleri kullanmanızı sağlar.

#### S: Belgeler klasörünün yolunu nasıl belirlerim?

 C: Sağlanan kaynak kodunda değiştirin`"YOUR DOCUMENT DIRECTORY"`yer imi sayfa numaralarını çıkarmak istediğiniz PDF dosyasını içeren klasörün gerçek yolunu belirtin. Bu, kodun hedef PDF dosyasını bulabilmesini sağlar.

#### S: Yer imi düzenleyicisini nasıl oluşturabilirim?

C: Bir yer imi düzenleyicisi oluşturmak için aşağıdaki kodu kullanın:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### S: Yer imlerini değiştirmek için bir PDF dosyasını nasıl açarım?

C: Yer imi bilgilerini çıkarmak amacıyla bir PDF dosyası açmak için aşağıdaki kodu kullanın:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Yer değiştirmek`"GetBookmarks.pdf"` gerçek dosya adı ile.

#### S: Yer işaretlerini PDF dosyasından nasıl çıkarabilirim?

 C: PDF dosyasından yer imlerini çıkarmak için`ExtractBookmarks` yer imi düzenleyicisinin yöntemi:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### S: Yer imi sayfa numaralarını nasıl alırım ve görüntülerim?

 C: Çıkarılan yer imleri arasında bir`foreach` döngüye girin ve erişin`PageNumber` İlgili sayfa numarasını almak ve görüntülemek için her yer iminin özelliği:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### S: Bu yaklaşımı kullanarak yer imi özelliklerini değiştirebilir miyim?

 C: Bu eğitim, yer imi sayfa numaralarını almaya odaklansa da, aynı yöntemi kullanarak diğer yer imi özelliklerini de değiştirebilirsiniz.`Bookmark`nesne ve ilgili özellikler.

#### S: Yer imi bilgilerini çıkardıktan sonra güncellenen PDF dosyasını nasıl kaydedebilirim?

C: Yer imini çıkarma orijinal PDF dosyasını değiştirmez. Herhangi bir değişikliği kaydetmek istiyorsanız bunu Aspose.PDF for .NET tarafından sağlanan diğer yöntemleri kullanarak yapabilirsiniz.