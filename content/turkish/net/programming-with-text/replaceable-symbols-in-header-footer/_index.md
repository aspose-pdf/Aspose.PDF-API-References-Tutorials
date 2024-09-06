---
title: Başlık Altbilgisindeki Değiştirilebilir Semboller
linktitle: Başlık Altbilgisindeki Değiştirilebilir Semboller
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'i kullanarak bir PDF belgesinin üst bilgi ve alt bilgisinde değiştirilebilir sembollerin nasıl kullanılacağını öğrenin.
type: docs
weight: 320
url: /tr/net/programming-with-text/replaceable-symbols-in-header-footer/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesinin üstbilgi ve altbilgisinde değiştirilebilir sembollerin nasıl kullanılacağını açıklayacağız. PDF oluşturma, kenar boşluklarını ayarlama, değiştirilebilir sembollerle üstbilgi ve altbilgi ekleme ve sağlanan C# kaynak kodunu kullanarak PDF'yi kaydetme adım adım sürecini ele alacağız.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temellerini anlamak.

## Adım 1: Belge Dizinini Ayarlayın

 Öncelikle, oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu ayarlamanız gerekir. Değiştir`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` İstediğiniz dizinin yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Bir PDF Belgesi ve Sayfası Oluşturun

 Daha sonra yeni bir PDF belgesi oluşturup buna bir sayfa ekliyoruz.`Document` sınıf ve`Page` Aspose.PDF kütüphanesinden sınıf.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Adım 3: Kenar Boşluklarını Ayarlayın

Sayfanın kenar boşluklarını şunu kullanarak ayarlıyoruz:`MarginInfo` sınıf. Marj değerlerini ihtiyaçlarınıza göre ayarlayın.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Adım 4: Değiştirilebilir Sembollerle Başlık Ekleme

 Biz bir tane yaratıyoruz`HeaderFooter` sayfa için nesne ve bir tane ekle`TextFragment` Değiştirilebilir sembollerle.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// İstenirse metin özelliklerini ayarlayın
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Daha fazla TextFragment ekleyin veya gerektiği gibi özelleştirin
```

## Adım 5: Değiştirilebilir Sembollerle Alt Bilgi Ekleme

 Benzer şekilde, bir tane yaratıyoruz`HeaderFooter` sayfa altbilgisi için nesne ve ekle`TextFragment` Değiştirilebilir sembollere sahip nesneler.

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

Son olarak PDF dokümanını belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### .NET için Aspose.PDF kullanarak Başlık Alt Bilgisinde Değiştirilebilir Semboller için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
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
// İçeriği başlık olarak gösterecek bir Metin paragrafı örneği oluşturun
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
// HeaderFooter nesnesini tek ve çift altbilgiye ayarlayın
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Toplam sayfa sayısının geçerli sayfa numarasını içeren bir metin paragrafı ekleyin
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Bir tablo nesnesi örneği oluşturun
Table tab2 = new Table();
// İstenilen bölümün paragraf koleksiyonuna tabloyu ekleyin
hfFoot.Paragraphs.Add(tab2);
// Tablonun sütun genişlikleriyle ayarlayın
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
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java, Aspose tarafından sunulan her Java bileşeninin bir derlemesidir. Her bir Java bileşenimizin en güncel sürümlerini içerdiğinden emin olmak için günlük olarak derlenir. #$NL " + "Aspose.Total for Java geliştiricileri geniş bir uygulama yelpazesi oluşturabilir. #$NL #$NL #$NP" + "Aspose.Total for Java, Aspose tarafından sunulan her Java bileşeninin bir derlemesidir. Her bir Java bileşenimizin en güncel sürümlerini içerdiğinden emin olmak için günlük olarak derlenir. #$NL " + "Aspose.Total for Java geliştiricileri geniş bir uygulama yelpazesi oluşturabilir. #$NL #$NL #$NP" + "Aspose.Total for Java, Aspose tarafından sunulan her Java bileşeninin bir derlemesidir. Her bir Java bileşenimizin en güncel sürümlerini içerdiğinden emin olmak için günlük olarak derlenir. Java bileşenlerimizin her birinin güncel sürümleri. #$NL " + "Java geliştiricileri için Aspose.Total'ı kullanarak çok çeşitli uygulamalar oluşturabilirsiniz. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// İstenilen bölümün paragraf koleksiyonuna tabloyu ekleyin
page.Paragraphs.Add(table);
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Başka bir özelleştirilmiş BorderInfo nesnesini kullanarak tablo kenarlığını ayarlayın
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

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesinin üstbilgi ve altbilgisinde değiştirilebilir sembollerin nasıl kullanılacağını öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan C# kodunu çalıştırarak bir PDF oluşturabilir, kenar boşluklarını ayarlayabilir, değiştirilebilir sembollerle üstbilgi ve altbilgi ekleyebilir ve PDF'yi kaydedebilirsiniz.

### SSS

#### S: "Üstbilgi ve Altbilgide Değiştirilebilir Semboller" eğitiminin amacı nedir?

A: "Başlık ve Altbilgide Değiştirilebilir Semboller" öğreticisi, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesinin başlığına ve altbilgisine değiştirilebilir semboller ekleme sürecinde size rehberlik etmeyi amaçlamaktadır. Değiştirilebilir semboller, PDF oluştururken belirli yer tutucuları gerçek değerlerle dinamik olarak değiştirmenize olanak tanır.

#### S: PDF üst bilgisi ve alt bilgisi bağlamında değiştirilebilir semboller nelerdir?

A: Değiştirilebilir semboller, bir PDF belgesinin üstbilgisine ve altbilgisine ekleyebileceğiniz yer tutuculardır. Bu semboller, sayfa numaraları, tarihler ve özel bilgiler gibi çalışma zamanında doldurulabilen değerler için dinamik yer tutucular olarak işlev görür.

#### S: PDF üst bilgi ve alt bilgisinde değiştirilebilir semboller kullanmak istememin nedeni nedir?

A: Sayfa numaraları, tarihler veya belge oluşturulduğunda değişebilecek diğer değişken veriler gibi PDF belgelerinize dinamik bilgiler eklemek istediğinizde, üst bilgi ve alt bilgideki değiştirilebilir simgeler yararlıdır.

#### S: PDF sayfasının kenar boşluklarını nasıl ayarlayabilirim?

 A: PDF sayfasının kenar boşluklarını,`MarginInfo` sınıfa atama ve onu atama`Margin` mülkiyeti`PageInfo` Sayfanın. Gerektiğinde kenar boşluğu değerlerini ayarlayın.

#### S: Üstbilgi ve altbilgiye değiştirilebilir semboller nasıl eklerim?

 A: Değiştirilebilir semboller ekleyerek bir`HeaderFooter` sayfanın üstbilgisi ve altbilgisi için nesne. Daha sonra, ekleyebilirsiniz`TextFragment`değiştirilebilir semboller de dahil olmak üzere istenilen metne sahip nesneleri`Paragraphs` koleksiyonu`HeaderFooter` nesne.

#### S: Değiştirilebilir sembollerin görünümünü özelleştirebilir miyim?

 A: Evet, değiştirilebilir sembollerin görünümünü, sembollerin özelliklerini değiştirerek özelleştirebilirsiniz.`TextFragment` sembolleri içeren nesneler. Yazı tipi, yazı tipi boyutu, renk, hizalama ve satır aralığı gibi özellikleri ayarlayabilirsiniz.

#### S: Hangi tür değiştirilebilir sembolleri kullanabilirim?

A: Çeşitli değiştirilebilir semboller kullanabilirsiniz, örneğin:

- `$p`: Mevcut sayfa numarası.
- `$P`: Toplam sayfa sayısı.
- `$d`: Güncel tarih.
- `$t`: Şu anki zaman.
- Sizin tanımladığınız özel yer tutucular.

#### S: Değiştirilebilir sembollerin etrafına başka metin ve biçimlendirme ekleyebilir miyim?

 A: Evet, değiştirilebilir sembollerin etrafına başka metinler ve biçimlendirmeler ekleyebilirsiniz.`TextFragment` Bu, dinamik ve statik içerikleri birleştiren daha karmaşık başlıklar ve altbilgiler oluşturmanıza olanak tanır.

#### S: Oluşturulan PDF belgesini nasıl kaydedebilirim?

 A: Oluşturulan PDF belgesini kaydetmek için şunu kullanabilirsiniz:`Save` yöntemi`Document`sınıf. İstenilen çıktı dosyası yolunu ve adını argüman olarak sağlayın.

#### S: Bu eğitim için geçerli bir Aspose Lisansı gerekli mi?

C: Evet, bu eğitimdeki kodu başarıyla yürütmek için geçerli bir Aspose Lisansı gereklidir. Aspose web sitesinden tam lisans veya 30 günlük geçici lisans alabilirsiniz.