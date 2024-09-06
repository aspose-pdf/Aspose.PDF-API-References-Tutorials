---
title: PDF Dosyasında Görüntünün Etrafına Metin Yerleştirme
linktitle: PDF Dosyasında Görüntünün Etrafına Metin Yerleştirme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki bir resmin etrafına nasıl metin yerleştireceğinizi öğrenin.
type: docs
weight: 260
url: /tr/net/programming-with-text/placing-text-around-image/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF dosyasındaki bir resmin etrafına metnin nasıl yerleştirileceğini açıklayacağız. Sağlanan C# kaynak kodunu kullanarak bir tablo oluşturma, bir resim ekleme ve resmin etrafına metin yerleştirme adım adım sürecini ele alacağız.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temellerini anlamak.

## Adım 1: Belge Dizinini Ayarlayın

 Öncelikle, oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu ayarlamanız gerekir. Değiştir`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` İstediğiniz dizinin yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Bir Belge ve Sayfa Oluşturun

 Daha sonra bir tane oluşturuyoruz`Document` nesneyi seçin ve ona bir sayfa ekleyin`Pages.Add()` Yöntem.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Adım 3: Bir Tablo Oluşturun

 Aşağıdakileri kullanarak bir tablo oluşturuyoruz:`Table` sınıfını seçin ve sayfanın paragraf koleksiyonuna ekleyin.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Adım 4: Tablo Sütun Genişliklerini ve Kenar Boşluklarını Ayarlayın

 Tablonun sütun genişliklerini ayarlıyoruz ve bir`MarginInfo` kenar boşluklarını ayarlama nesnesi.

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

 Biz bir`Image` nesne, resim dosya yolunu belirtin ve resmin sabit yüksekliğini ve genişliğini ayarlayın. Sonra, resmi tablo hücresinin paragraphs koleksiyonuna ekleriz.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Adım 6: Resmin Etrafına Metin Ekleyin

 HTML biçimli metin içeren dize değişkenleri oluşturuyoruz ve bir`HtmlFragment`nesne. Daha sonra, HTML metnini resmi içeren tablo hücresine ekleriz.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Adım 7: Ek Metin Ekleyin

 Başka bir tane yaratıyoruz`HtmlFragment` Ek HTML biçimli metin içeren nesneyi seçin ve ayrı bir tablo hücresine ekleyin.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Adım 8: PDF Belgesini Kaydedin

Son olarak PDF dokümanını belirtilen çıktı dosyasına kaydediyoruz.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### .NET için Aspose.PDF kullanarak Resmin Etrafına Metin Yerleştirme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini örnekle
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Pdf'de bir sayfa oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();
// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// İstenilen bölümün paragraf koleksiyonuna tabloyu ekleyin
page.Paragraphs.Add(table1);
// Tablonun sütun genişlikleriyle ayarlayın
table1.ColumnWidths = "120 270";
// MarginInfo nesnesini oluşturun ve sol, alt, sağ ve üst kenar boşluklarını ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Varsayılan hücre dolgusunu MarginInfo nesnesine ayarlayın
table1.DefaultCellPadding = margin;
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Bir resim nesnesi oluşturun
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Görüntü dosya yolunu belirtin
logo.File = dataDir + "aspose-logo.jpg";
// Görüntü Sabit Yüksekliğini belirtin
logo.FixHeight = 120;
// Görüntü Sabit Genişliğini belirtin
logo.FixWidth = 110;
row1.Cells.Add();
// Resmi tablo hücresinin paragraf koleksiyonuna ekle
row1.Cells[0].Paragraphs.Add(logo);
// HTML etiketleri içeren metinle dize değişkenleri oluşturun
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Resmin sağına eklenecek bir metin nesnesi oluşturun
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// HTML metni içeren metin paragraflarını tablo hücresine ekleyin
row1.Cells[1].Paragraphs.Add(TitleText);
// Satır içeriklerinin dikey hizalamasını Üst olarak ayarlayın
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// İkinci satır için satır aralığı değerini 2 olarak ayarlayın
SecondRow.Cells[0].ColSpan = 2;
// İkinci satırın dikey hizalamasını Üst olarak ayarlayın
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// HTML metni içeren metin paragraflarını tablo hücresine ekleyin
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// PDF dosyasını kaydedin
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesinde bir resmin etrafına metin yerleştirmeyi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu çalıştırarak bir tablo oluşturabilir, bir resim ekleyebilir ve metni bir PDF belgesinde resmin etrafına yerleştirebilirsiniz.

### SSS

#### S: "PDF Dosyasında Resmin Etrafına Metin Yerleştirme" eğitiminin amacı nedir?

A: "PDF Dosyasında Görüntünün Etrafına Metin Yerleştirme" öğreticisi, .NET için Aspose.PDF kütüphanesinin PDF belgesinde bir görüntünün etrafına metin yerleştirmek için nasıl kullanılacağını gösterir. Öğretici, bir tablo oluşturmanıza, bir görüntü eklemenize ve metni görüntünün etrafına yerleştirmenize yardımcı olmak için adım adım bir kılavuz ve C# kaynak kodu sağlar.

#### S: PDF belgesinde bir resmin etrafına neden metin yerleştirmek isteyeyim?

A: Bir görselin etrafına metin yerleştirmek, PDF belgelerinizin görsel sunumunu geliştirerek onları daha ilgi çekici ve bilgilendirici hale getirir. Bu teknik genellikle görselleri ve metni estetik açıdan hoş bir şekilde birleştirmek istediğiniz belgelerde, broşürlerde, raporlarda ve diğer materyallerde kullanılır.

#### S: Belge dizinini nasıl ayarlarım?

A: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` Oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu içeren değişken.

#### S: Bir tablo nasıl oluşturabilirim ve içine nasıl resim ekleyebilirim?

 A: Eğitim, bir tablo oluşturma sürecinde size rehberlik eder.`Table` sınıf ve tabloya bir resim ekleme`Image` sınıf. Bir tablo hücresine eklemeden önce görüntü dosya yolunu, yüksekliğini ve genişliğini belirteceksiniz.

#### S: Metni görselin etrafına nasıl yerleştiririm?

 A: Metni resmin etrafına yerleştirmek için, HTML biçimli metin oluşturacaksınız`HtmlFragment` sınıf. Bu metin hem bir başlık hem de gövde metni içerecektir. Daha sonra bu HTML metnini resim hücresine bitişik bir tablo hücresine ekleyeceksiniz.

#### S: Metnin ve görselin görünümünü özelleştirebilir miyim?

C: Evet, HTML etiketleri ve özelliklerini kullanarak metnin ve resmin görünümünü özelleştirebilirsiniz. Örneğin, metin için yazı tipi boyutlarını, renkleri, stilleri ve hizalamayı ayarlayabilirsiniz. Ek olarak, resmin boyutunu ve ebatlarını ayarlayabilirsiniz.

#### S: PDF belgesini nasıl kaydedebilirim?

 A: Tabloya resim ve metin ekledikten sonra PDF belgesini şu şekilde kaydedebilirsiniz:`Save` yöntemi`Document` sınıf. İstenen çıktı dosyası yolunu argüman olarak sağlayın`Save` Yöntem.

#### S: Bu eğitimin beklenen çıktısı nedir?

A: Öğreticiyi takip ederek ve sağlanan C# kodunu çalıştırarak, bir görüntünün etrafına metin yerleştirmeyi gösteren bir PDF belgesi oluşturacaksınız. Çıktı belgesi, etrafında konumlandırılmış bir görüntü ve metin içeren bir tablo içerecektir.

#### S: JPG dışında farklı resim formatları kullanabilir miyim?

 A: Evet, PNG, BMP, GIF ve daha fazlası gibi Aspose.PDF kitaplığı tarafından desteklenen farklı görüntü biçimlerini kullanabilirsiniz.`Image` nesne, istenilen görüntü formatının dosya yolunu belirtin.

#### S: Bu eğitim için geçerli bir Aspose Lisansı gerekli mi?

C: Evet, bu eğitimin doğru çalışması için geçerli bir Aspose Lisansı gereklidir. Aspose web sitesinden tam lisans satın alabilir veya 30 günlük geçici lisans edinebilirsiniz.