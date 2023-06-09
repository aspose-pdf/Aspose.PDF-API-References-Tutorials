---
title: Resmin Çevresine Metin Yerleştirme
linktitle: Resmin Çevresine Metin Yerleştirme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir görüntünün etrafına nasıl metin yerleştireceğinizi öğrenin.
type: docs
weight: 260
url: /tr/net/programming-with-text/placing-text-around-image/
---

Bu eğitimde, Aspose.PDF kütüphanesini kullanarak bir PDF belgesindeki bir görüntünün etrafına nasıl metin yerleştireceğimizi açıklayacağız. Sağlanan C# kaynak kodunu kullanarak tablo oluşturma, görüntü ekleme ve metni görüntünün etrafına konumlandırma sürecini adım adım inceleyeceğiz.

## Gereksinimler

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Temel bir C# programlama anlayışı.

## 1. Adım: Belge Dizinini kurun

 Öncelikle, oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu belirlemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` istediğiniz dizinin yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir Belge ve Sayfa Oluşturun

 Sonra, bir`Document` kullanarak bir sayfa ekleyin ve ona bir sayfa ekleyin.`Pages.Add()` yöntem.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 3. Adım: Bir Tablo Oluşturun

 kullanarak bir tablo oluşturuyoruz.`Table` sınıflandırın ve sayfanın paragraf koleksiyonuna ekleyin.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## 4. Adım: Tablo Sütun Genişliklerini ve Kenar Boşluklarını Ayarlayın

 Tablonun sütun genişliklerini ayarlıyoruz ve bir tablo oluşturuyoruz.`MarginInfo` Kenar boşluklarını ayarlamak için nesne.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Adım 5: Tabloya Bir Resim Ekleyin

 biz bir yaratırız`Image` nesne, görüntü dosyası yolunu belirtin ve görüntünün sabit yüksekliğini ve genişliğini ayarlayın. Ardından görüntüyü tablo hücresinin paragraflar koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## 6. Adım: Resmin Etrafına Metin Ekleyin

 HTML biçimli metin içeren dize değişkenleri oluşturuyoruz ve`HtmlFragment` nesne. Ardından, HTML metnini görüntüyü içeren tablo hücresine ekliyoruz.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## 7. Adım: Ek Metin Ekleyin

 Başka bir tane yaratıyoruz`HtmlFragment` ek HTML biçimli metin içeren bir nesne ve onu ayrı bir tablo hücresine ekleyin.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## 8. Adım: PDF Belgesini Kaydedin

Son olarak, PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Aspose.PDF for .NET kullanarak Görüntünün Etrafına Metin Yerleştirme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini somutlaştır
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Pdf'te bir sayfa oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();
// Bir tablo nesnesini somutlaştırın
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
//Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(table1);
// Tablonun sütun genişlikleriyle ayarla
table1.ColumnWidths = "120 270";
// MarginInfo nesnesi oluşturun ve sol, alt, sağ ve üst kenar boşluklarını ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Varsayılan hücre dolgusunu MarginInfo nesnesine ayarlayın
table1.DefaultCellPadding = margin;
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Bir görüntü nesnesi oluşturun
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Görüntü dosyası yolunu belirtin
logo.File = dataDir + "aspose-logo.jpg";
// Görüntünün Sabit Yüksekliğini belirtin
logo.FixHeight = 120;
// Resmi Sabit Genişlik olarak belirtin
logo.FixWidth = 110;
row1.Cells.Add();
// Görüntüyü tablo hücresinin paragraflar koleksiyonuna ekleyin
row1.Cells[0].Paragraphs.Add(logo);
// Html etiketleri içeren metinle dize değişkenleri oluşturun
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
// Resmin sağına eklenecek bir metin nesnesi oluşturun
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// HTML metni içeren metin paragraflarını tablo hücresine ekleyin
row1.Cells[1].Paragraphs.Add(TitleText);
// Satır içeriğinin dikey hizalamasını Üst olarak ayarlayın
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// İkinci satır için satır yayılma değerini 2 olarak ayarlayın
SecondRow.Cells[0].ColSpan = 2;
// İkinci satırın dikey hizalamasını Üst olarak ayarlayın
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// HTML metni içeren metin paragraflarını tablo hücresine ekleyin
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Pdf dosyasını kaydedin
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Çözüm

Bu öğreticide, Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesindeki bir görüntünün etrafına nasıl metin yerleştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu çalıştırarak bir tablo oluşturabilir, görüntü ekleyebilir ve bir PDF belgesinde metni görüntünün etrafına konumlandırabilirsiniz.