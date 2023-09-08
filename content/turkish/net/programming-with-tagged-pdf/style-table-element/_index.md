---
title: Stil Tablosu Öğesi
linktitle: Stil Tablosu Öğesi
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile tablo öğesini nasıl formatlayacağınızı öğrenin. Stilleri ve özellikleri özelleştirmek için adım adım kılavuz.
type: docs
weight: 170
url: /tr/net/programming-with-tagged-pdf/style-table-element/
---
Bu ayrıntılı eğitimde, dizi öğesini Aspose.PDF for .NET kullanarak formatlamak için sağlanan C# kaynak kodunu adım adım anlatacağız. Dizi öğesinin stillerini ve özelliklerini nasıl özelleştireceğinizi anlamak için aşağıdaki talimatları izleyin.

## 1. Adım: Ortamı ayarlama

Başlamadan önce geliştirme ortamınızı Aspose.PDF for .NET'i kullanacak şekilde yapılandırdığınızdan emin olun. Buna Aspose.PDF kütüphanesinin kurulması ve projenizin buna referans verecek şekilde yapılandırılması da dahildir.

## 2. Adım: Belge oluşturma

Bu adımda yeni bir belge nesnesi Aspose.PDF oluşturacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Yeni bir belge oluşturduk ve belge başlığını ve dilini belirledik.

## Adım 3: Kök yapı öğesinin elde edilmesi

Bu adımda belgemiz için kök yapı elemanını alacağız.

```csharp
//Kök yapı öğesini edinin
StructureElement rootElement = taggedContent.RootElement;
```

Dizi elemanı için kap görevi görecek kök yapı elemanını elde ettik.

## Adım 4: Dizi yapısı öğesinin oluşturulması

Şimdi belgemiz için yeni bir tablo yapısı öğesi oluşturalım.

```csharp
// Dizi yapısı öğesini oluşturun
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Yeni bir dizi yapısı elemanı oluşturduk ve onu kök yapı elemanına ekledik.

## Adım 5: Dizi Öğesi Stillerini ve Özelliklerini Özelleştirme

Bu adımda dizi öğesinin stillerini ve özelliklerini özelleştireceğiz.

```csharp
// Dizi öğesinin stillerini ve özelliklerini özelleştirme
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Tekrarlanan çizgilerin stilini özelleştirin
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Tablo öğesini özelleştirmek için arka plan rengi, kenarlıklar, hizalama, varsayılan hücre stili, kenar boşlukları, sütun genişliği vb. gibi çeşitli özellikler kullandık.

## 6. Adım: Tablo üstbilgilerini, gövdesini ve altbilgisini ekleyin

Şimdi tablo elemanına tablo başlıklarını, gövdesini ve altbilgisini ekleyelim.
```csharp
// Tablo başlıkları ekleyin
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Tablodaki satır ve sütun sayısı
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Tablo başlığı satırını oluşturun
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Tablo gövdesinin satırlarını ekleyin
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Tablonun temel çizgisini ekleyin
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

İlgili öğeleri kullanarak üstbilgileri, gövde satırlarını ve altbilgi satırını tabloya ekledik.

## 7. Adım: Etiketli PDF belgesini kaydetme

Artık belgemizi stillendirilmiş tablo öğesiyle oluşturduğumuza göre, onu etiketli bir PDF belgesi olarak kaydedeceğiz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StyleTableElement.pdf");
```

Etiketli PDF belgesini belirtilen dizine kaydettik.

## 8. Adım: PDF/UA uyumluluk doğrulaması

Daha sonra belgemizin PDF/UA uygunluğunu doğrulayacağız.

```csharp
// PDF/UA uyumluluk kontrolü
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Etiketli PDF belgesini yükledik ve bir XML raporu oluşturarak PDF/UA uyumluluğunu doğruladık.

### Aspose.PDF for .NET kullanan Stil Tablosu Öğesi için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Doküman oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Kök yapı öğesini alın
StructureElement rootElement = taggedContent.RootElement;

// Tablo yapısı öğesi oluştur
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Etiketli Pdf Belgesini Kaydet
document.Save(dataDir + "StyleTableElement.pdf");

// PDF/UA uyumluluğunu kontrol etme
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde dizi öğesini Aspose.PDF for .NET ile nasıl formatlayacağımızı öğrendik. Tablo öğesinin stillerini ve özelliklerini özelleştirdik, üstbilgiler, gövde satırları ve altbilgi ekledik, etiketli PDF belgesini kaydettik ve PDF/UA uyumluluğunu doğruladık.

### SSS'ler

#### S: Dizi öğesini Aspose.PDF for .NET kullanarak biçimlendirmeye yönelik bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET kullanarak bir PDF belgesindeki dizi öğesini formatlama sürecinde size rehberlik etmektir. Dizi öğesinin stillerini ve özelliklerini özelleştirmenize yardımcı olmak için adım adım talimatlar ve C# kaynak kodu örnekleri sağlar.

#### S: Bu eğitimi takip etmenin önkoşulları nelerdir?

C: Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET'i kullanacak şekilde ayarladığınızdan emin olun. Bu, Aspose.PDF kütüphanesinin kurulmasını ve projenizin buna referans verecek şekilde yapılandırılmasını içerir.

#### S: Aspose.PDF for .NET'i kullanarak yeni bir PDF belgesini nasıl oluşturabilir ve başlığını ve dilini nasıl ayarlayabilirim?

 C: Yeni bir PDF belgesi oluşturmak için bir`Document` Aspose.PDF kütüphanesinden nesne. Eğitimde sağlanan C# kaynak kodu, bir belgenin nasıl oluşturulacağını ve başlık ve dil özelliklerinin nasıl ayarlanacağını gösterir.

#### S: Bir PDF belgesindeki kök yapı öğesinin önemi nedir?

C: Kök yapı öğesi, diğer yapı öğeleri için bir kap görevi görerek PDF belgesinin içeriğinin düzenlenmesine ve kategorize edilmesine yardımcı olur. Belgenin mantıksal yapısının oluşturulmasında çok önemli bir rol oynar.

#### S: Aspose.PDF for .NET'i kullanarak bir dizi yapısı öğesini nasıl oluşturup özelleştirebilirim?

 C: Aşağıdakileri kullanarak bir dizi yapısı öğesi oluşturabilirsiniz:`CreateTableElement()` yöntem. Eğitimin kaynak kodu, tablo öğesinin arka plan rengi, kenarlıklar, hizalama, sütun genişliği ve daha fazlası gibi çeşitli özelliklerinin özelleştirilmesine ilişkin örnekler sağlar.

#### S: Dizi öğesi içindeki tablo hücrelerinin stillerini ve özelliklerini özelleştirebilir miyim?

C: Evet, eğitimde üstbilgiler, gövde satırları ve altbilgi dahil olmak üzere tüm tablo öğesinin stillerinin ve özelliklerinin nasıl özelleştirileceği anlatılmaktadır. Ancak, ayrı ayrı tablo hücrelerinin özelleştirilmesine özel olarak değinmez.

#### S: Tablo öğesine nasıl üst bilgi, gövde satırları ve alt bilgi ekleyebilirim?

C: Bu eğitimde Aspose.PDF for .NET tarafından sağlanan uygun yöntemleri kullanarak başlıkların, gövde satırlarının ve alt bilginin nasıl oluşturulacağı ve tablo öğesine nasıl ekleneceği açıklanmaktadır.

#### S: PDF/UA uyumluluğu nedir ve bunu etiketli PDF belgem için nasıl doğrulayabilirim?

 C: PDF/UA uyumluluğu, PDF belgesinin erişilebilirlik standartlarına uygun olmasını sağlayarak onu engelli kullanıcılar için daha erişilebilir hale getirir. Eğitimde PDF/UA uyumluluğunun nasıl doğrulanacağı gösterilmektedir.`Validate()` yöntemini kullanın ve bir XML uyumluluk raporu oluşturun.

#### S: Bu kavramları kendi .NET uygulamalarıma nasıl dahil edebilirim?

C: Sağlanan C# kaynak kodu örneklerini, dizi öğesi biçimlendirmesini kendi .NET uygulamalarınızda uygulamaya yönelik bir kılavuz olarak kullanabilirsiniz. Kodu gereksinimlerinize uyacak şekilde değiştirin ve uyarlayın ve projelerinize entegre edin.

#### S: PDF belgelerindeki dizi öğelerini biçimlendirmek için önerilen en iyi uygulamalar var mı?

C: Dizi öğelerini (tabloları) biçimlendirirken içeriğin okunabilirliğini ve erişilebilirliğini göz önünde bulundurun. Açık ve okunaklı yazı tipleri, uygun renkler kullanın ve tutarlı bir düzen sağlayın. Erişilebilirlik standartlarının karşılandığından emin olmak için PDF/UA uyumluluğunu doğrulayın.

#### S: PDF belge özelleştirmesi için Aspose.PDF for .NET'in başka hangi özelliklerini keşfedebilirim?

C: Aspose.PDF for .NET, PDF belgesi özelleştirmesi için metin işleme, görüntü ekleme, form alanı yönetimi, dijital imzalar, açıklamalar ve daha fazlasını içeren bir dizi özellik sunar. Ek işlevleri keşfetmek için resmi belgelere ve kaynaklara bakın.