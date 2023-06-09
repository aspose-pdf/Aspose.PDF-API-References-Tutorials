---
title: İçindekiler Eklerken Sayfa Numaralarını Özelleştirin
linktitle: İçindekiler Eklerken Sayfa Numaralarını Özelleştirin
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ve kod örneği ile Aspose.PDF for .NET kullanarak bir içindekiler tablosu (TOC) eklerken sayfa numaralarını nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir içindekiler tablosu (TOC) eklerken sayfa numaralarının nasıl özelleştirileceğini keşfedeceğiz. Bunu başarmanıza yardımcı olmak için bir kod örneğiyle birlikte adım adım rehberlik sağlayacağız.

## 1. Adım: Mevcut bir PDF dosyasını yükleme

İlk olarak, mevcut bir PDF dosyasını yüklememiz gerekiyor. Bu eğitim için, "BELGE DİZİNİNİZ" dizininde bulunan "42824.pdf" dosyasını kullanacağız. Bu dizin yolunu, belge dizininizin gerçek yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## 2. Adım: İçindekiler sayfası ekleme

 Ardından, içindekiler sayfası olarak hizmet vermesi için belgenin başına yeni bir sayfa eklememiz gerekiyor. kullanarak bunu başarabiliriz.`Insert()` yöntemi`Pages` koleksiyonu`Document` nesne.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## 3. Adım: Bir TOC nesnesi oluşturma

 Bir TOC nesnesi oluşturmak için önce bir TOC nesnesi oluşturmamız gerekir.`TocInfo`nesne ve özelliklerini ayarlayın. Bu öğreticide, İçindekiler'in başlığını "İçindekiler Tablosu" ve sayfa numarası önekini "P" olarak ayarlayacağız.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## 4. Adım: İçindekiler girişlerini oluşturma

İçindekiler girdileri oluşturmak için içindekiler sayfası hariç belgenin tüm sayfalarını dolaşmalı ve her sayfa için bir başlık nesnesi oluşturmalıyız. Daha sonra başlık nesnesini İçindekiler sayfasına ekleyebilir ve hedef sayfasını belirtebiliriz.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Başlık nesnesi oluştur
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Başlık nesnesi için hedef sayfayı belirtin
    heading2.DestinationPage = doc.Pages[i + 1];
    // hedef sayfa
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // hedef koordinat
    segment2.Text = "Page " + i.ToString();
    //İçindekiler içeren sayfaya başlık ekle
    tocPage.Paragraphs.Add(heading2);
}
```

## 5. Adım: Güncellenen belgeyi kaydetme

 Son olarak, güncellenen belgeyi yeni bir dosyaya kaydetmemiz gerekiyor. kullanarak bunu başarabiliriz.`Save()` yöntemi`Document` nesne.

```csharp
doc.Save(outFile);
```

### Aspose.PDF for .NET kullanarak İçindekiler eklerken sayfa numaralarını özelleştirmek için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(inFile);
// PDF dosyasının ilk sayfasına erişin
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// İçindekiler bilgisini temsil edecek nesne oluştur
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// İçindekiler için başlığı ayarla
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Başlık nesnesi oluştur
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Başlık nesnesi için hedef sayfayı belirtin
	heading2.DestinationPage = doc.Pages[i + 1];
	// hedef sayfa
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// hedef koordinat
	segment2.Text = "Page " + i.ToString();
	//İçindekiler içeren sayfaya başlık ekle
	tocPage.Paragraphs.Add(heading2);
}

// Güncellenen belgeyi kaydedin
doc.Save(outFile);
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak içindekiler eklerken sayfa numaralarının nasıl özelleştirileceğine dair adım adım rehberlik sağladık. Bu özelliği uygulamanızda referans olarak kullanabileceğiniz bir kod örneği de sağladık.

