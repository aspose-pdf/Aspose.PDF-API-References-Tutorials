---
title: Yer İşaretlerini Genişlet
linktitle: Yer İşaretlerini Genişlet
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile daha iyi gezinme için PDF dosyalarınızın yer imlerini kolayca genişletin.
type: docs
weight: 50
url: /tr/net/programming-with-bookmarks/expand-bookmarks/
---

Bir PDF belgesindeki yer imlerini genişletmek, varsayılan olarak tüm açık yer imlerini görüntüler. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek yer imlerini kolayca genişletebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, yer imlerini genişletmek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi yer imlerini genişletmek istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4. Adım: Sayfa Görüntüleme Modunu Ayarlayın

 Bu adımda, sayfa görüntüleme modunu varsayılan olarak yer imlerini gösterecek şekilde ayarlayacağız. biz kullanıyoruz`PageMode` mülkiyeti`doc`İstenen sayfa modunu ayarlamak için nesne. İşte ilgili kod:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## 5. Adım: Yer imlerine göz atın ve genişletin

 Şimdi, belgenin yer işaretleri koleksiyonundaki her bir yer işareti öğesi arasında dolaşacağız ve her öğenin açık durumunu şu şekilde ayarlayacağız:`true` varsayılan olarak genişletmek için. İşte ilgili kod:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## 6. Adım: Güncellenen dosyayı kaydedin

 Son olarak, güncellenmiş PDF dosyasını kullanarak kaydediyoruz.`Save` yöntemi`doc` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Expand Bookmarks için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");
// Sayfa görüntüleme modunu ayarlayın, yani küçük resimleri göster, tam ekran, ek panelini göster
doc.PageMode = PageMode.UseOutlines;
// PDF dosyasının ana hatlar koleksiyonundaki her bir Ouline öğesinde gezinin
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Anahat öğesi için açık durumu ayarla
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Çıktıyı kaydet
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile yer imleri geliştirmek için adım adım bir kılavuza sahipsiniz. PDF belgelerinizdeki tüm varsayılan yer imlerini göstermek için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.