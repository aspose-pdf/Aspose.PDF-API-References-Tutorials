---
title: Stil Tablosu Satırı
linktitle: Stil Tablosu Satırı
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile tablo satırlarını nasıl özelleştireceğinizi öğrenin, adım adım satırları biçimlendirme ve biçimlendirme kılavuzu.
type: docs
weight: 180
url: /tr/net/programming-with-tagged-pdf/style-table-row/
---
Bu ayrıntılı öğreticide, tablo satırını Aspose.PDF for .NET kullanarak biçimlendirmek için sağlanan C# kaynak kodunda adım adım yol göstereceğiz. Tablo satırı stillerinin ve özelliklerinin nasıl özelleştirileceğini anlamak için aşağıdaki talimatları izleyin.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET kullanacak şekilde yapılandırdığınızdan emin olun. Bu, Aspose.PDF kitaplığının kurulmasını ve projenizin buna referans verecek şekilde yapılandırılmasını içerir.

## 2. Adım: Belge oluşturma

Bu adımda yeni bir belge nesnesi Aspose.PDF oluşturacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

Yeni bir belge oluşturduk ve belge başlığını ve dilini belirledik.

## Adım 3: Kök yapı elemanının elde edilmesi

Bu adımda, belgemiz için kök yapı öğesini alacağız.

```csharp
//Kök yapı öğesini elde edin
StructureElement rootElement = taggedContent.RootElement;
```

Dizi elemanı için bir kap görevi görecek olan kök yapı elemanına sahibiz.

## 4. Adım: Dizi yapısı öğesinin oluşturulması

Şimdi belgemiz için yeni bir tablo yapısı elemanı oluşturalım.

```csharp
// Dizi yapısı öğesini oluşturun
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Yeni bir dizi yapı elemanı oluşturduk ve onu kök yapı elemanına ekledik.

## 5. Adım: Tablo satırı stillerini ve özelliklerini özelleştirin

Bu adımda, tablo satırı stillerini ve özelliklerini özelleştireceğiz.

```csharp
// Tablo satırı stillerini ve özelliklerini özelleştirme
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Tablo gövdesinin satırlarını özelleştirme
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Tablonun altbilgi satırını oluşturun
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Arka plan rengi, kenarlıklar, satır yüksekliği, sayfalandırma, varsayılan hücre stili ve daha fazlası gibi tablo satırının çeşitli özelliklerini özelleştirdik.

## 6. Adım: Etiketli PDF belgesini kaydetme

Stil tablosu satırıyla belgemizi oluşturduğumuza göre, onu etiketli bir PDF belgesi olarak kaydedeceğiz.
```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StyleTableRow.pdf");
```

Etiketli PDF belgesini belirtilen dizine kaydettik.

## 7. Adım: PDF/UA uyumluluk doğrulaması

Ardından, belgemizin PDF/UA uygunluğunu doğrulayacağız.

```csharp
// PDF/UA uyumluluk kontrolü
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Etiketli PDF belgesini yükledik ve bir XML raporu oluşturarak PDF/UA uyumluluğunu doğruladık.


### Aspose.PDF for .NET kullanan Stil Tablosu Satırı için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Kök yapı öğesini al
StructureElement rootElement = taggedContent.RootElement;

// Tablo yapısı öğesi oluştur
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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

// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "StyleTableRow.pdf");

// PDF/UA uyumluluğunu kontrol etme
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde, tablo satırını Aspose.PDF for .NET ile nasıl biçimlendireceğimizi öğrendik. Tablo satırı stillerini ve özelliklerini özelleştirdik, üst bilgileri, gövde satırlarını ve alt bilgileri ekledik, etiketli PDF belgesini kaydettik ve PDF/UA uyumluluğunu doğruladık.

### SSS

#### S: Aspose.PDF for .NET kullanarak tablo satırlarını biçimlendirme konusundaki bu eğitimin amacı nedir?

Y: Bu eğitimin amacı, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tablo satırlarını biçimlendirme sürecinde size rehberlik etmektir. Tablo satırı stillerini ve özelliklerini özelleştirmenize yardımcı olmak için adım adım yönergeler ve C# kaynak kodu örnekleri sağlar.

#### S: Bu öğreticiyi takip etmek için ön koşullar nelerdir?

C: Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET'i kullanacak şekilde kurduğunuzdan emin olun. Bu, Aspose.PDF kitaplığının kurulmasını ve projenizin buna referans verecek şekilde yapılandırılmasını içerir.

#### S: Aspose.PDF for .NET kullanarak yeni bir PDF belgesini nasıl oluşturabilir, başlığını ve dilini nasıl ayarlayabilirim?

 Y: Yeni bir PDF belgesi oluşturmak için bir`Document` Aspose.PDF kitaplığından nesne. Öğreticinin sağladığı C# kaynak kodu, bir belgenin nasıl oluşturulacağını ve başlık ve dil özelliklerinin nasıl ayarlanacağını gösterir.

#### S: Bir PDF belgesindeki kök yapı öğesinin önemi nedir?

Y: Kök yapı öğesi, diğer yapı öğeleri için bir kap görevi görerek PDF belgesinin içeriğini düzenlemeye ve kategorilere ayırmaya yardımcı olur. Belgenin mantıksal yapısının oluşturulmasında çok önemli bir rol oynar.

#### S: Aspose.PDF for .NET kullanarak tablo satırlarını biçimlendirmek için bir tablo yapısı öğesini nasıl oluşturabilir ve özelleştirebilirim?

C: Öğretici, bir tablo yapısı öğesinin nasıl oluşturulacağını ve tablo satırlarını biçimlendirmek için özelliklerinin nasıl özelleştirileceğini açıklar. Arka plan rengi, kenarlıklar, satır yüksekliği, sayfalandırma, varsayılan hücre stili ve daha fazlası gibi özellikleri kapsar.

#### S: Bir tablo satırındaki tek tek hücrelerin stillerini ve özelliklerini özelleştirebilir miyim?

C: Evet, bir tablo satırındaki tek tek hücrelerin stillerini ve özelliklerini özelleştirebilirsiniz. Öğretici, biçimlendirilmiş tablo satırındaki tablo hücreleri için arka plan rengi, kenarlıklar, metin rengi, dolgu ve daha fazlası gibi özelliklerin nasıl ayarlanacağını gösterir.

#### S: Biçimlendirilmiş tablo satırına nasıl üst bilgiler, gövde satırları ve alt bilgi ekleyebilirim?

C: Öğretici, tablo yapısı öğesine başlıklar, gövde satırları ve altbilgi oluşturma ve ekleme örnekleri sağlar. Bu öğeler, öğreticide açıklanan özellikler kullanılarak daha da özelleştirilebilir.

#### S: PDF/UA uyumluluğu nedir ve etiketli PDF belgem için bunu nasıl doğrulayabilirim?

 Y: PDF/UA uyumluluğu, PDF belgesinin erişilebilirlik standartlarına uygun olmasını sağlayarak engelli kullanıcılar için daha erişilebilir olmasını sağlar. Öğretici, PDF/UA uyumluluğunun nasıl doğrulanacağını gösterir.`Validate()` yöntemini seçin ve bir XML uyumluluk raporu oluşturun.

#### S: Bu kavramları kendi .NET uygulamalarıma nasıl dahil edebilirim?

A: Sağlanan C# kaynak kodu örneklerini, kendi .NET uygulamalarınızda tablo satırı biçimlendirmesini uygulamak için bir kılavuz olarak kullanabilirsiniz. Kodu gereksinimlerinize uyacak şekilde değiştirin ve uyarlayın ve projelerinize entegre edin.

#### S: PDF belgelerinde tablo satırlarını biçimlendirmek için önerilen en iyi uygulamalar var mı?

C: Tablo satırlarını biçimlendirirken, içeriğin okunabilirliğini ve erişilebilirliğini göz önünde bulundurun. Renklerin yeterli kontrasta sahip olduğundan emin olun, net ve okunaklı yazı tipleri kullanın ve tutarlı bir düzen sağlayın. Erişilebilirlik standartlarının karşılandığından emin olmak için PDF/UA uyumluluğunu doğrulayın.

#### S: PDF belge özelleştirmesi için Aspose.PDF for .NET'in başka hangi özelliklerini keşfedebilirim?

Y: Aspose.PDF for .NET, PDF belgesi özelleştirme için metin işleme, görüntü ekleme, form alanı yönetimi, dijital imzalar, ek açıklamalar ve daha fazlasını içeren çok çeşitli özellikler sunar. Ek işlevleri keşfetmek için resmi belgelere ve kaynaklara başvurun.