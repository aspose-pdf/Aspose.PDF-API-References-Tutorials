---
title: PDF Dosyasında Görüntünün Çevresine Metin Yerleştirme
linktitle: PDF Dosyasında Görüntünün Çevresine Metin Yerleştirme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasındaki bir görüntünün çevresine nasıl metin yerleştireceğinizi öğrenin.
type: docs
weight: 260
url: /tr/net/programming-with-text/placing-text-around-image/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF dosyasındaki bir görüntünün çevresine nasıl metin yerleştireceğimizi açıklayacağız. Sağlanan C# kaynak kodunu kullanarak tablo oluşturma, resim ekleme ve resmin etrafına metin yerleştirme işlemlerini adım adım gerçekleştireceğiz.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temel anlayışı.

## 1. Adım: Belge Dizinini Ayarlayın

 Öncelikle oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir`İstediğiniz dizinin yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir Belge ve Sayfa Oluşturun

 Daha sonra bir tane oluşturuyoruz`Document` nesneyi kullanın ve ona bir sayfa ekleyin.`Pages.Add()` yöntem.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 3. Adım: Tablo Oluşturun

 kullanarak bir tablo oluşturuyoruz.`Table` sınıfını seçin ve sayfanın paragraf koleksiyonuna ekleyin.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Adım 4: Tablo Sütunu Genişliklerini ve Kenar Boşluklarını Ayarlayın

 Tablonun sütun genişliklerini ayarlayıp bir tablo oluşturuyoruz.`MarginInfo` Kenar boşluklarını ayarlama nesnesi.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Adım 5: Tabloya Bir Resim Ekleme

 Biz bir yaratıyoruz`Image` nesneyi seçin, görüntü dosyası yolunu belirtin ve görüntünün sabit yüksekliğini ve genişliğini ayarlayın. Daha sonra görüntüyü tablo hücresinin paragraf koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Adım 6: Resmin Çevresine Metin Ekleyin

 HTML biçimli metin içeren dize değişkenleri oluştururuz ve`HtmlFragment`nesne. Daha sonra HTML metnini görselin bulunduğu tablo hücresine ekliyoruz.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Adım 7: Ek Metin Ekleyin

 Başka bir tane yaratıyoruz`HtmlFragment` ek HTML biçimli metin içeren nesneyi seçin ve bunu ayrı bir tablo hücresine ekleyin.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Adım 8: PDF Belgesini Kaydedin

Son olarak PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Aspose.PDF for .NET kullanarak Görüntünün Etrafına Metin Yerleştirmek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini somutlaştır
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Pdf'de bir sayfa oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();
// Bir tablo nesnesinin örneğini oluşturma
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(table1);
// Tablonun sütun genişliklerine göre ayarlama
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
// Resmin Sabit Genişliğini Belirleyin
logo.FixWidth = 110;
row1.Cells.Add();
// Görüntüyü tablo hücresinin paragraf koleksiyonuna ekleyin
row1.Cells[0].Paragraphs.Add(logo);
// Html etiketleri içeren metinlerle dize değişkenleri oluşturun
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Resmin sağına eklenecek bir metin nesnesi oluşturun
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// HTML metnini içeren metin paragraflarını tablo hücresine ekleme
row1.Cells[1].Paragraphs.Add(TitleText);
// Satır içeriklerinin dikey hizalamasını Üst olarak ayarlayın
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// İkinci satırın satır aralığı değerini 2 olarak ayarlayın
SecondRow.Cells[0].ColSpan = 2;
// İkinci satırın dikey hizalamasını Üst olarak ayarlayın
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// HTML metnini içeren metin paragraflarını tablo hücresine ekleme
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Pdf dosyasını kaydedin
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesindeki bir görüntünün çevresine nasıl metin yerleştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu çalıştırarak bir tablo oluşturabilir, bir görüntü ekleyebilir ve bir PDF belgesinde metni görüntünün etrafına konumlandırabilirsiniz.

### SSS'ler

#### S: "PDF Dosyasındaki Görüntünün Çevresine Metin Yerleştirme" eğitiminin amacı nedir?

C: "PDF Dosyasındaki Görüntünün Çevresine Metin Yerleştirme" eğitimi, bir PDF belgesindeki bir görüntünün çevresine metin yerleştirmek için .NET için Aspose.PDF kütüphanesinin nasıl kullanılacağını gösterir. Öğreticide, tablo oluşturmanıza, görüntü eklemenize ve metni görüntünün çevresine konumlandırmanıza yardımcı olacak adım adım kılavuz ve C# kaynak kodu sağlanır.

#### S: Neden bir PDF belgesindeki bir görüntünün çevresine metin yerleştirmek isteyeyim?

C: Bir görüntünün etrafına metin yerleştirmek, PDF belgelerinizin görsel sunumunu geliştirerek onları daha ilgi çekici ve bilgilendirici hale getirir. Bu teknik genellikle görselleri ve metni estetik açıdan hoş bir şekilde birleştirmek istediğiniz belgelerde, broşürlerde, raporlarda ve diğer materyallerde kullanılır.

#### S: Belge dizinini nasıl ayarlarım?

C: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu içeren değişken.

#### S: Bir tabloyu nasıl oluşturup ona resim eklerim?

 C: Eğitim, aşağıdakileri kullanarak bir tablo oluşturma sürecinde size rehberlik eder:`Table` sınıfını kullanarak tabloya bir resim eklemek`Image` sınıf. Görüntü dosyasının yolunu, yüksekliğini ve genişliğini tablo hücresine eklemeden önce belirteceksiniz.

#### S: Metni görüntünün etrafına nasıl yerleştiririm?

 C: Metni görüntünün çevresine konumlandırmak için HTML biçimli metin oluşturacaksınız.`HtmlFragment` sınıf. Bu metin hem başlık hem de gövde metnini içerecektir. Daha sonra bu HTML metnini resim hücresine bitişik bir tablo hücresine ekleyeceksiniz.

#### S: Metnin ve görselin görünümünü özelleştirebilir miyim?

C: Evet, HTML etiketlerini ve özelliklerini kullanarak metnin ve görselin görünümünü özelleştirebilirsiniz. Örneğin metnin yazı tipi boyutlarını, renklerini, stillerini ve hizalamasını ayarlayabilirsiniz. Ayrıca görüntünün boyutunu ve boyutlarını da ayarlayabilirsiniz.

#### S: PDF belgesini nasıl kaydederim?

 C: Görüntüyü ve metni tabloya ekledikten sonra, PDF belgesini`Save` yöntemi`Document` sınıf. Argüman olarak istenen çıktı dosyası yolunu sağlayın.`Save` yöntem.

#### S: Bu eğitimin beklenen çıktısı nedir?

C: Öğreticiyi takip ederek ve verilen C# kodunu çalıştırarak, metnin bir görüntünün etrafına nasıl yerleştirileceğini gösteren bir PDF belgesi oluşturacaksınız. Çıktı belgesi, etrafına resim ve metin yerleştirilmiş bir tablo içerecektir.

#### S: JPG dışında farklı resim formatlarını kullanabilir miyim?

 C: Evet, Aspose.PDF kütüphanesi tarafından desteklenen PNG, BMP, GIF ve daha fazlası gibi farklı görüntü formatlarını kullanabilirsiniz. oluştururken`Image` nesneyi istediğiniz görüntü formatının dosya yolunu belirtin.

#### S: Bu eğitim için geçerli bir Aspose Lisansı gerekli mi?

C: Evet, bu eğitimin düzgün çalışması için geçerli bir Aspose Lisansı gereklidir. Aspose web sitesinden tam lisans satın alabilir veya 30 günlük geçici lisans alabilirsiniz.