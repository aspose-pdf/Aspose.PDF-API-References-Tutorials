---
title: Stil Tablo Hücresi
linktitle: Stil Tablo Hücresi
second_title: Aspose.PDF for .NET API Referansı
description: Bu detaylı eğitimle .NET için Aspose.PDF kullanarak bir PDF'deki tablo hücrelerini nasıl biçimlendireceğinizi öğrenin. Güzel PDF tabloları oluşturmak ve biçimlendirmek için talimatları izleyin.
type: docs
weight: 160
url: /tr/net/programming-with-tagged-pdf/style-table-cell/
---
## giriiş

Profesyonel görünümlü PDF tabloları oluşturmak zor olabilir, ancak Aspose.PDF for .NET ile şaşırtıcı derecede basittir! İster başlıkları, ister altbilgileri veya belirli tablo hücrelerini biçimlendiriyor olun, bu güçlü kitaplık size güzel biçimlendirilmiş PDF belgeleri oluşturmak için ihtiyacınız olan tüm araçları sağlar. Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tablo hücrelerini nasıl biçimlendireceğinizi ele alacağız. Endişelenmeyin—her şeyi takip etmesi kolay adımlara ayıracağız.

## Ön koşullar

Koda dalmadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. .NET için Aspose.PDF: Aspose.PDF'nin en son sürümünü indirin ve yükleyin[Burada](https://releases.aspose.com/pdf/net/).
2. IDE (Visual Studio gibi): .NET geliştirme ortamı kurun.
3. Temel C# programlama bilgisi: C# ile ilgili biraz bilgi sahibi olmak gerekir.
4.  Aspose.PDF Lisansı: Kütüphanenin tüm özelliklerinin kilidini açmak için geçici veya tam lisans edinin. Ücretsiz deneme alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

## Paketleri İçe Aktar

Başlamadan önce, gerekli ad alanlarını içe aktardığınızdan emin olun. Projenizde şunlara ihtiyacınız olacak:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Artık her şey ayarlandığına göre adım adım kılavuza geçebiliriz!

Bir PDF belgesinde bir tablo oluşturacağız ve hücrelerini biçimlendireceğiz. Her adım süreci ayrıntılı olarak açıklayacaktır.

## Adım 1: Yeni bir PDF Belgesi Oluşturun

 İlk adım yeni bir PDF belgesi oluşturmaktır. Aspose.PDF'de yeni bir PDF belgesi başlatabilirsiniz.`Document` PDF dosyanızı temsil eden nesne.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir PDF belgesi oluşturun
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Burada bir PDF belgesi başlatıyoruz ve başlığını ve dilini ayarlıyoruz. Bu, belgenize PDF/UA uyumluluğu için önemli olan uygun bir yapı kazandırır.

## Adım 2: Tablo Yapısını Ayarlayın

PDF'lerdeki tablolar yapı elemanları içerisinde tanımlanır. Tabloyu oluşturalım ve tablonun satır ve sütunlarını tanımlayalım.

```csharp
// Kök yapı öğesini alın
StructureElement rootElement = taggedContent.RootElement;

// Bir tablo yapı öğesi oluşturun
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Artık tablonun başını tanımladık (`TableTHeadElement`), vücut (`TableTBodyElement`), ve ayak (`TableTFootElement`) bölümleri. Bunları tablonuzun iskeleti olarak düşünebilirsiniz.

## Adım 3: Başlık Hücrelerini Biçimlendirin

Başlık hücrelerini biçimlendirmek onları öne çıkarır. Burada, arka plan renkleri, kenarlıklar ve metin hizalaması uygularız.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

Bu adımda, her başlık hücresinde dolaşarak ona yeşil-sarı bir arka plan, gri bir kenarlık ve sağa hizalanmış bir metin veriyoruz. Bu özellikleri istediğiniz tasarıma uyacak şekilde ayarlayabilirsiniz.

## Adım 4: Tablo Gövdesini Doldurun ve Biçimlendirin

Tablo gövdesi gerçek verileri içerir. Her hücreyi belirli kenar boşlukları, sınırlar ve metin ayarlarıyla nasıl biçimlendirebileceğiniz aşağıda açıklanmıştır.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 Bu adımda, tablo gövdesini dört satırla dolduruyoruz ve her hücreyi sarı arka planlar ve ortalanmış, kalın mavi metinle biçimlendiriyoruz. Ayrıca,`MarginInfo`metnin etrafındaki dolguyu tanımlayan sınıf.

## Adım 5: Altbilgiyi Biçimlendirin

Tabloya eksiksiz bir yapı kazandırmak için, tıpkı başlıkta yaptığımız gibi, altbilgi hücrelerini de ekleyip biçimlendiriyoruz.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

Altbilgi bölümü, okuyucuların tablonun yapısını takip etmesini kolaylaştırmak için üstbilgiye benzer şekilde tasarlanmıştır.

## Adım 6: PDF Belgesini Kaydedin ve Doğrulayın

Son olarak PDF dokümanını kaydedip PDF/UA uyumlu olup olmadığını kontrol ediyoruz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA uyumluluğunun kontrol edilmesi
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 PDF'yi kaydediyoruz ve kullanıyoruz`Validate` Erişilebilirlik standartlarını karşıladığından emin olmak için bir yöntem (PDF/UA uyumluluğu).

## Çözüm

.NET için Aspose.PDF kullanarak bir PDF'deki tabloları biçimlendirmek hem güçlü hem de esnektir. Birkaç satır kodla, PDF belgelerinizin öne çıkmasını sağlayacak özel tablo tasarımları oluşturabilirsiniz. Hücre kenarlıklarını ve arka planlarını özelleştirmekten erişilebilirlik uyumluluğunu sağlamaya kadar, Aspose.PDF cilalı PDF dosyaları oluşturmayı kolaylaştırır.

## SSS

### Her bir tablo hücresine farklı stiller uygulayabilir miyim?  
Evet, özelleştirerek tek tek hücrelere stil verebilirsiniz.`TableTDElement` özellikler.

### Tablo hücrelerini nasıl birleştirebilirim?  
 Kullanabilirsiniz`ColSpan` Ve`RowSpan` Bir tabloda hücreleri birleştirme özellikleri.

### PDF/UA uyumlu bir tablo oluşturmak mümkün müdür?  
 Evet, bu kılavuzda gösterildiği gibi, belgenizi kullanarak PDF/UA uyumluluğunu doğrulayabilirsiniz.`Validate` Yöntem.

### Tablo hücrelerinde farklı yazı tipleri kullanabilir miyim?  
 Kesinlikle! Farklı yazı tiplerini kullanarak belirtebilirsiniz.`TextState` Her hücre için nesne.

### Aspose.PDF for .NET'i nasıl indirebilirim?  
 Bunu şuradan indirebilirsiniz:[sürüm sayfası](https://releases.aspose.com/pdf/net/).