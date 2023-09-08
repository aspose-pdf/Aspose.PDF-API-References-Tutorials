---
title: Üstbilgi Altbilgisindeki Değiştirilebilir Semboller
linktitle: Üstbilgi Altbilgisindeki Değiştirilebilir Semboller
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir PDF belgesinin üstbilgisinde ve altbilgisinde değiştirilebilir sembollerin nasıl kullanılacağını öğrenin.
type: docs
weight: 320
url: /tr/net/programming-with-text/replaceable-symbols-in-header-footer/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesinin üstbilgisinde ve altbilgisinde değiştirilebilir sembollerin nasıl kullanılacağını açıklayacağız. PDF oluşturma, kenar boşluklarını ayarlama, değiştirilebilir sembollerle üstbilgi ve altbilgi ekleme ve sağlanan C# kaynak kodunu kullanarak PDF'yi kaydetme işlemlerini adım adım gerçekleştireceğiz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temel anlayışı.

## 1. Adım: Belge Dizinini Ayarlayın

 Öncelikle oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir`İstediğiniz dizinin yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesi ve Sayfası Oluşturun

 Daha sonra, yeni bir PDF belgesi oluşturup ona bir sayfa ekliyoruz.`Document` sınıf ve`Page` Aspose.PDF kütüphanesinden sınıf.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3. Adım: Kenar Boşluklarını Ayarlayın

 Sayfanın kenar boşluklarını kullanarak ayarlıyoruz.`MarginInfo`sınıf. Marj değerlerini gereksinimlerinize göre ayarlayın.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Adım 4: Değiştirilebilir Sembollerle Başlık Ekleme

 Biz bir yaratıyoruz`HeaderFooter` sayfa için nesne ve bir tane ekleyin`TextFragment` değiştirilebilir sembollerle birlikte.

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

// Daha fazla TextFragments ekleyin veya gerektiği gibi özelleştirin
```

## Adım 5: Değiştirilebilir Sembollerle Alt Bilgi Ekleme

 Benzer şekilde, bir`HeaderFooter` sayfa altbilgisi için nesne ve ekleme`TextFragment` Değiştirilebilir sembollere sahip nesneler.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Daha fazla TextFragments ekleyin veya gerektiği gibi özelleştirin

hfFoot.Paragraphs.Add(tab2);
```

## Adım 6: PDF Belgesini Kaydedin

Son olarak PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Üst Bilgi Alt Bilgisindeki Değiştirilebilir Semboller için örnek kaynak kodu 
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
// MarginInfo örneğini sec1.PageInfo'nun Margin özelliğine atayın
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Başlık olarak gösterilecek içeriği saklayacak bir Metin paragrafı örneği oluşturun
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
// HeaderFooter nesnesini tek ve çift altbilgi olarak ayarlayın
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Toplam sayfa sayısının geçerli sayfa numarasını içeren bir metin paragrafı ekleyin
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Bir tablo nesnesinin örneğini oluşturma
Table tab2 = new Table();
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
hfFoot.Paragraphs.Add(tab2);
// Tablonun sütun genişliklerine göre ayarlama
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
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java, Aspose tarafından sunulan tüm Java bileşenlerinin bir derlemesidir. Her birinin en güncel sürümlerini içerdiğinden emin olmak için #$NL" + "günlük olarak derlenir. #$NL " + "Aspose.Total for Java'yı kullanarak geliştiriciler çok çeşitli uygulamalar oluşturabilirler. #$NL #$NL #$NP" + "Aspose.Total for Java, her Java bileşeninin bir derlemesidir Aspose tarafından sunulmaktadır. Java bileşenlerimizin her birinin en güncel sürümlerini içerdiğinden emin olmak için #$NL" + "günlük olarak derlenir. #$NL " + "Java geliştiricileri için Aspose.Total'ı kullanarak geniş bir içerik oluşturabilirsiniz. #$NL #$NL #$NP" + "Aspose.Total for Java, Aspose tarafından sunulan her Java bileşeninin bir derlemesidir. En fazla içeriği içerdiğinden emin olmak için #$NL" + "günlük olarak derlenir. Java bileşenlerimizin her birinin güncel sürümleri. #$NL " + "Java geliştiricileri Aspose.Total'ı kullanarak çok çeşitli uygulamalar oluşturabilir. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(table);
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlama
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

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesinin üstbilgisinde ve altbilgisinde değiştirilebilir sembollerin nasıl kullanılacağını öğrendiniz. Adım adım kılavuzu izleyerek ve verilen C# kodunu çalıştırarak bir PDF oluşturabilir, kenar boşluklarını ayarlayabilir, değiştirilebilir sembollerle üst bilgi ve alt bilgi ekleyebilir ve PDF'yi kaydedebilirsiniz.

### SSS'ler

#### S: "Üst Bilgi Alt Bilgideki Değiştirilebilir Semboller" eğitiminin amacı nedir?

C: "Üst Bilgi Alt Bilgisindeki Değiştirilebilir Semboller" eğitimi, bir PDF belgesinin üst bilgi ve alt bilgisine değiştirilebilir semboller eklemek için .NET için Aspose.PDF kütüphanesini kullanma sürecinde size rehberlik etmeyi amaçlamaktadır. Değiştirilebilir semboller, PDF'yi oluştururken belirli yer tutucuları dinamik olarak gerçek değerlerle değiştirmenize olanak tanır.

#### S: PDF üstbilgisi ve altbilgisi bağlamında değiştirilebilir simgeler nelerdir?

C: Değiştirilebilir semboller, bir PDF belgesinin üstbilgisine ve altbilgisine ekleyebileceğiniz yer tutuculardır. Bu semboller, sayfa numaraları, tarihler ve özel bilgiler gibi çalışma zamanında doldurulabilecek değerler için dinamik yer tutucular görevi görür.

#### S: PDF üstbilgisinde ve altbilgisinde neden değiştirilebilir semboller kullanmak isteyeyim?

C: Üstbilgi ve altbilgideki değiştirilebilir semboller, PDF belgelerinize sayfa numaraları, tarihler veya belge oluşturulduğunda değişebilecek diğer değişken veriler gibi dinamik bilgiler eklemek istediğinizde kullanışlıdır.

#### S: PDF sayfasının kenar boşluklarını nasıl ayarlayabilirim?

 C: PDF sayfasının kenar boşluklarını aşağıdaki düğmeyi kullanarak ayarlayabilirsiniz:`MarginInfo` sınıfa atamak ve`Margin` mülkiyeti`PageInfo` sayfanın. Kenar boşluğu değerlerini gerektiği gibi ayarlayın.

#### S: Değiştirilebilir sembolleri üstbilgi ve altbilgiye nasıl eklerim?

 C: Değiştirilebilir sembolleri bir`HeaderFooter` sayfanın üstbilgisi ve altbilgisi için nesne. Daha sonra ekleyebilirsiniz`TextFragment`Değiştirilebilir semboller de dahil olmak üzere istenen metni içeren nesneleri`Paragraphs` koleksiyonu`HeaderFooter` nesne.

#### S: Değiştirilebilir simgelerin görünümünü özelleştirebilir miyim?

 C: Evet, değiştirilebilir sembollerin özelliklerini değiştirerek, değiştirilebilir sembollerin görünümünü özelleştirebilirsiniz.`TextFragment` sembolleri içeren nesneler. Yazı tipi, yazı tipi boyutu, renk, hizalama ve satır aralığı gibi özellikleri ayarlayabilirsiniz.

#### S: Ne tür değiştirilebilir semboller kullanabilirim?

C: Aşağıdakiler gibi çeşitli değiştirilebilir semboller kullanabilirsiniz:

- `$p`: Geçerli sayfa numarası.
- `$P`: Toplam sayfa sayısı.
- `$d`: Geçerli tarih.
- `$t`: Şimdiki zaman.
- Tanımladığınız özel yer tutucular.

#### S: Değiştirilebilir simgelerin çevresine başka metin ve biçimlendirme ekleyebilir miyim?

 C: Evet, değiştirilebilir simgelerin çevresine başka metin ve biçimlendirmeler ekleyebilirsiniz.`TextFragment` nesneler. Bu, dinamik ve statik içerik içeren daha karmaşık üstbilgiler ve altbilgiler oluşturmanıza olanak tanır.

#### S: Oluşturulan PDF belgesini nasıl kaydedebilirim?

 C: Oluşturulan PDF belgesini kaydetmek için`Save` yöntemi`Document`sınıf. İstenilen çıktı dosyası yolunu ve adını bağımsız değişken olarak sağlayın.

#### S: Bu eğitim için geçerli bir Aspose Lisansı gerekli mi?

C: Evet, bu eğitimde kodu başarıyla yürütmek için geçerli bir Aspose Lisansı gereklidir. Aspose web sitesinden tam lisans veya 30 günlük geçici lisans alabilirsiniz.