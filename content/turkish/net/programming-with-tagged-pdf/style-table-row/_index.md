---
title: Stil Tablosu Satırı
linktitle: Stil Tablosu Satırı
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile tablo satırlarını nasıl özelleştireceğinizi adım adım satır şekillendirme ve formatlama kılavuzuyla öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-tagged-pdf/style-table-row/
---
Bu ayrıntılı eğitimde, Aspose.PDF for .NET'i kullanarak tablo satırını biçimlendirmek için sağlanan C# kaynak kodunu size adım adım anlatacağız. Tablo satır stillerinin ve özelliklerinin nasıl özelleştirileceğini anlamak için aşağıdaki talimatları izleyin.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## 5. Adım: Tablo satırı stillerini ve özelliklerini özelleştirin

Bu adımda tablo satır stillerini ve özelliklerini özelleştireceğiz.

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

Tablo satırının arka plan rengi, kenarlıklar, satır yüksekliği, sayfalandırma, varsayılan hücre stili ve daha fazlası gibi çeşitli yönlerini özelleştirdik.

## Adım 6: Etiketli PDF belgesini kaydetme

Artık belgemizi stillendirilmiş tablo satırıyla oluşturduğumuza göre, onu etiketli bir PDF belgesi olarak kaydedeceğiz.
```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StyleTableRow.pdf");
```

Etiketli PDF belgesini belirtilen dizine kaydettik.

## 7. Adım: PDF/UA uyumluluk doğrulaması

Daha sonra belgemizin PDF/UA uygunluğunu doğrulayacağız.

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

// Doküman oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Kök yapı öğesini alın
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

// Etiketli Pdf Belgesini Kaydet
document.Save(dataDir + "StyleTableRow.pdf");

// PDF/UA uyumluluğunu kontrol etme
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET ile tablo satırlarının nasıl formatlanacağını öğrendik. Tablo satırı stillerini ve özelliklerini özelleştirdik, üstbilgileri, gövde satırlarını ve altbilgiyi ekledik, etiketli PDF belgesini kaydettik ve PDF/UA uyumluluğunu doğruladık.

### SSS'ler

#### S: Tablo satırlarını Aspose.PDF for .NET kullanarak biçimlendirmeye yönelik bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tablo satırlarını biçimlendirme sürecinde size rehberlik etmektir. Tablo satırı stillerini ve özelliklerini özelleştirmenize yardımcı olmak için adım adım talimatlar ve C# kaynak kodu örnekleri sağlar.

#### S: Bu eğitimi takip etmenin önkoşulları nelerdir?

C: Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET'i kullanacak şekilde ayarladığınızdan emin olun. Bu, Aspose.PDF kütüphanesinin kurulmasını ve projenizin buna referans verecek şekilde yapılandırılmasını içerir.

#### S: Aspose.PDF for .NET'i kullanarak yeni bir PDF belgesini nasıl oluşturabilir ve başlığını ve dilini nasıl ayarlayabilirim?

 C: Yeni bir PDF belgesi oluşturmak için bir`Document` Aspose.PDF kütüphanesinden nesne. Eğitimde sağlanan C# kaynak kodu, bir belgenin nasıl oluşturulacağını ve başlık ve dil özelliklerinin nasıl ayarlanacağını gösterir.

#### S: Bir PDF belgesindeki kök yapı öğesinin önemi nedir?

C: Kök yapı öğesi, diğer yapı öğeleri için bir kap görevi görerek PDF belgesinin içeriğinin düzenlenmesine ve kategorize edilmesine yardımcı olur. Belgenin mantıksal yapısının oluşturulmasında çok önemli bir rol oynar.

#### S: Aspose.PDF for .NET'i kullanarak tablo satırlarını formatlamak için bir tablo yapısı öğesini nasıl oluşturup özelleştirebilirim?

C: Eğitimde bir tablo yapısı öğesinin nasıl oluşturulacağı ve tablo satırlarını biçimlendirmek için özelliklerinin nasıl özelleştirileceği açıklanmaktadır. Arka plan rengi, kenarlıklar, satır yüksekliği, sayfalandırma, varsayılan hücre stili ve daha fazlası gibi hususları kapsar.

#### S: Bir tablo satırındaki tek tek hücrelerin stillerini ve özelliklerini özelleştirebilir miyim?

C: Evet, bir tablo satırındaki tek tek hücrelerin stillerini ve özelliklerini özelleştirebilirsiniz. Öğretici, biçimlendirilmiş tablo satırındaki tablo hücreleri için arka plan rengi, kenarlıklar, metin rengi, dolgu ve daha fazlası gibi özelliklerin nasıl ayarlanacağını gösterir.

#### S: Biçimlendirilmiş tablo satırına üstbilgileri, gövde satırlarını ve altbilgiyi nasıl ekleyebilirim?

C: Öğreticide, tablo yapısı öğesine başlıklar, gövde satırları ve alt bilgi oluşturma ve ekleme örnekleri verilmektedir. Bu öğeler, eğitimde açıklanan özellikler kullanılarak daha da özelleştirilebilir.

#### S: PDF/UA uyumluluğu nedir ve bunu etiketli PDF belgem için nasıl doğrulayabilirim?

 C: PDF/UA uyumluluğu, PDF belgesinin erişilebilirlik standartlarına uygun olmasını sağlayarak onu engelli kullanıcılar için daha erişilebilir hale getirir. Eğitimde PDF/UA uyumluluğunun nasıl doğrulanacağı gösterilmektedir.`Validate()` yöntemini kullanın ve bir XML uyumluluk raporu oluşturun.

#### S: Bu kavramları kendi .NET uygulamalarıma nasıl dahil edebilirim?

C: Sağlanan C# kaynak kodu örneklerini, kendi .NET uygulamalarınızda tablo satırı biçimlendirmesini uygulamaya yönelik bir kılavuz olarak kullanabilirsiniz. Kodu gereksinimlerinize uyacak şekilde değiştirin ve uyarlayın ve projelerinize entegre edin.

#### S: PDF belgelerindeki tablo satırlarını biçimlendirmek için önerilen en iyi uygulamalar var mı?

C: Tablo satırlarını biçimlendirirken içeriğin okunabilirliğini ve erişilebilirliğini göz önünde bulundurun. Renklerin yeterli kontrasta sahip olduğundan emin olun, net ve okunaklı yazı tipleri kullanın ve tutarlı bir düzen sağlayın. Erişilebilirlik standartlarının karşılandığından emin olmak için PDF/UA uyumluluğunu doğrulayın.

#### S: PDF belge özelleştirmesi için Aspose.PDF for .NET'in başka hangi özelliklerini keşfedebilirim?

C: Aspose.PDF for .NET, PDF belgesi özelleştirmesi için metin işleme, görüntü ekleme, form alanı yönetimi, dijital imzalar, açıklamalar ve daha fazlasını içeren çok çeşitli özellikler sunar. Ek işlevleri keşfetmek için resmi belgelere ve kaynaklara bakın.