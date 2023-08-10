---
title: Üstbilgi Altbilgideki Değiştirilebilir Semboller
linktitle: Üstbilgi Altbilgideki Değiştirilebilir Semboller
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinin üstbilgisinde ve altbilgisinde değiştirilebilir sembollerin nasıl kullanılacağını öğrenin.
type: docs
weight: 320
url: /tr/net/programming-with-text/replaceable-symbols-in-header-footer/
---

Bu öğreticide, Aspose.PDF kitaplığı .NET kullanılarak bir PDF belgesinin üstbilgisinde ve altbilgisinde değiştirilebilir sembollerin nasıl kullanılacağını açıklayacağız. PDF oluşturma, kenar boşluklarını ayarlama, değiştirilebilir sembollerle üstbilgi ve altbilgi ekleme ve sağlanan C# kaynak kodunu kullanarak PDF'yi kaydetme sürecini adım adım inceleyeceğiz.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Temel bir C# programlama anlayışı.

## 1. Adım: Belge Dizinini kurun

 Öncelikle, oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu belirlemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` istediğiniz dizinin yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir PDF Belgesi ve Sayfası Oluşturun

 Ardından, yeni bir PDF belgesi oluşturuyoruz ve bunu kullanarak ona bir sayfa ekliyoruz.`Document` sınıf ve`Page` Aspose.PDF kitaplığından sınıf.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3. Adım: Kenar Boşluklarını Ayarlayın

 kullanarak sayfanın kenar boşluklarını ayarlıyoruz.`MarginInfo` sınıf. Kenar boşluğu değerlerini gereksinimlerinize göre ayarlayın.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## 4. Adım: Değiştirilebilir Sembollerle Başlık Ekleyin

 biz bir yaratırız`HeaderFooter` sayfa için bir nesne ekleyin ve bir`TextFragment` değiştirilebilir sembollerle.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// İsterseniz metin özelliklerini ayarlayın
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Daha fazla TextFragment ekleyin veya gerektiği gibi özelleştirin
```

## Adım 5: Değiştirilebilir Sembollerle Alt Bilgi Ekleyin

 Benzer şekilde, bir`HeaderFooter` sayfa altbilgisi için nesne ve ekle`TextFragment` değiştirilebilir sembollere sahip nesneler.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Daha fazla TextFragment ekleyin veya gerektiği gibi özelleştirin

hfFoot.Paragraphs.Add(tab2);
```

## Adım 6: PDF Belgesini Kaydedin

Son olarak, PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Üstbilgi Altbilgideki Değiştirilebilir Semboller için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// marginInfo örneğini sec1.PageInfo'nun Margin özelliğine atayın
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// İçeriği başlık olarak gösterecek şekilde saklayacak bir Metin paragrafı örneği oluşturun
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Bölüm için bir HeaderFooter nesnesi oluşturun
HeaderFooter hfFoot = new HeaderFooter();
// HeaderFooter nesnesini tek ve çift alt bilgiye ayarlayın
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Toplam sayfa sayısının geçerli sayfa numarasını içeren bir metin paragrafı ekleyin
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Bir tablo nesnesini somutlaştırın
Table tab2 = new Table();
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
hfFoot.Paragraphs.Add(tab2);
// Tablonun sütun genişlikleriyle ayarla
tab2.ColumnWidths = "165 172 165";
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Metnin dikey hizalamasını ortaya hizalanmış olarak ayarla
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java, Aspose tarafından sunulan her Java bileşeninin bir derlemesidir. Her birinin en güncel sürümlerini içermesini sağlamak için #$NL" + "günlük olarak derlenir. #$NL " + "Aspose.Total for Java kullanan geliştiriciler çok çeşitli uygulamalar oluşturabilir. #$NL #$NL #$NP" + "Aspose.Total for Java, her Java bileşeninin bir derlemesidir Aspose tarafından sunulmaktadır. Java bileşenlerimizin her birinin en güncel sürümlerini içerdiğinden emin olmak için #$NL" + "günlük olarak derlenmektedir. #$NL " + "Aspose.Total for Java kullanan geliştiriciler geniş bir #$NL #$NL #$NP" + "Aspose.Total for Java, Aspose tarafından sunulan her Java bileşeninin bir derlemesidir. En çok içeriği içerdiğinden emin olmak için #$NL" + "günlük olarak derlenir. Java bileşenlerimizin her birinin güncel sürümleri. #$NL " + "Aspose.Total for Java kullanarak geliştiriciler çok çeşitli uygulamalar oluşturabilir. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(table);
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Başka bir özelleştirilmiş BorderInfo nesnesi kullanarak tablo kenarlığını ayarlayın
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Çözüm

Bu öğreticide, .NET için Aspose.PDF kitaplığını kullanarak bir PDF belgesinin üstbilgisinde ve altbilgisinde değiştirilebilir sembollerin nasıl kullanılacağını öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu yürüterek bir PDF oluşturabilir, kenar boşluklarını ayarlayabilir, değiştirilebilir sembollerle üstbilgi ve altbilgi ekleyebilir ve PDF'yi kaydedebilirsiniz.