---
title: Stil Tablo Satırı
linktitle: Stil Tablo Satırı
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile tablo satırlarını nasıl özelleştireceğinizi öğrenin, satırları biçimlendirme ve şekillendirmeye yönelik adım adım kılavuz.
type: docs
weight: 180
url: /tr/net/programming-with-tagged-pdf/style-table-row/
---
Bu detaylı eğitimde, .NET için Aspose.PDF kullanarak tablo satırını biçimlendirmek için sağlanan C# kaynak kodunu adım adım inceleyeceğiz. Tablo satır stilleri ve özelliklerini nasıl özelleştireceğinizi anlamak için aşağıdaki talimatları izleyin.

## Adım 1: Ortamı kurma

Başlamadan önce, geliştirme ortamınızı .NET için Aspose.PDF kullanacak şekilde yapılandırdığınızdan emin olun. Bu, Aspose.PDF kitaplığını yüklemeyi ve projenizi buna başvuracak şekilde yapılandırmayı içerir.

## Adım 2: Bir belge oluşturma

Bu adımda Aspose.PDF adında yeni bir belge nesnesi oluşturacağız.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

Yeni bir belge oluşturduk ve belge başlığını ve dilini ayarladık.

## Adım 3: Kök yapı elemanının elde edilmesi

Bu adımda belgemiz için kök yapı elemanını elde edeceğiz.

```csharp
//Kök yapı elemanını elde edin
StructureElement rootElement = taggedContent.RootElement;
```

Dizi elemanı için bir konteyner görevi görecek olan kök yapı elemanını elde ettik.

## Adım 4: Dizi yapı öğesini oluşturma

Şimdi belgemiz için yeni bir tablo yapı elemanı oluşturalım.

```csharp
// Dizi yapı öğesini oluşturun
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Yeni bir dizi yapı elemanı oluşturduk ve bunu kök yapı elemanına ekledik.

## Adım 5: Tablo satır stillerini ve özelliklerini özelleştirin

Bu adımda tablo satır stillerini ve özelliklerini özelleştireceğiz.

```csharp
// Tablo satır stillerini ve özelliklerini özelleştirin
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

// Tablonun gövdesinin satırlarını özelleştirin
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

Tablo satırının arka plan rengi, kenarlıklar, satır yüksekliği, sayfalandırma, varsayılan hücre stili gibi çeşitli yönlerini özelleştirdik.

## Adım 6: Etiketli PDF belgesini kaydetme

Artık biçimlendirilmiş tablo satırıyla belgemizi oluşturduğumuza göre, bunu etiketli PDF belgesi olarak kaydedeceğiz.
```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StyleTableRow.pdf");
```

Etiketli PDF dokümanını belirtilen dizine kaydettik.

## Adım 7: PDF/UA uyumluluğunun doğrulanması

Daha sonra dokümanımızın PDF/UA uygunluğunu doğrulayacağız.

```csharp
// PDF/UA uyumluluk kontrolü
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Etiketli PDF dokümanını yükledik ve bir XML raporu oluşturarak PDF/UA uyumluluğunu doğruladık.


### .NET için Aspose.PDF kullanılarak Stil Tablosu Satırı için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Kök yapı elemanını al
StructureElement rootElement = taggedContent.RootElement;

// Tablo yapı öğesini oluştur
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

// PDF/UA uyumluluğunun kontrol edilmesi
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF ile tablo satırını nasıl biçimlendireceğimizi öğrendik. Tablo satır stillerini ve özelliklerini özelleştirdik, başlıkları, gövde satırlarını ve alt bilgiyi ekledik, etiketli PDF belgesini kaydettik ve PDF/UA uyumluluğunu doğruladık.

### SSS

#### S: Aspose.PDF for .NET kullanarak tablo satırlarını biçimlendirme hakkındaki bu eğitimin amacı nedir?

A: Bu eğitimin amacı, .NET için Aspose.PDF kullanarak bir PDF belgesindeki tablo satırlarını biçimlendirme sürecinde size rehberlik etmektir. Tablo satır stillerini ve özelliklerini özelleştirmenize yardımcı olmak için adım adım talimatlar ve C# kaynak kodu örnekleri sağlar.

#### S: Bu eğitimi takip etmek için ön koşullar nelerdir?

A: Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET kullanacak şekilde ayarladığınızdan emin olun. Bu, Aspose.PDF kitaplığını yüklemeyi ve projenizi buna başvuracak şekilde yapılandırmayı içerir.

#### S: Aspose.PDF for .NET kullanarak yeni bir PDF belgesi nasıl oluşturabilirim ve başlığını ve dilini nasıl ayarlayabilirim?

 A: Yeni bir PDF belgesi oluşturmak için bir`Document` Aspose.PDF kütüphanesinden nesne. Eğitimin sağladığı C# kaynak kodu, bir belgenin nasıl oluşturulacağını ve başlığının ve dil özelliklerinin nasıl ayarlanacağını gösterir.

#### S: Bir PDF belgesinde kök yapı öğesinin önemi nedir?

A: Kök yapı öğesi, diğer yapı öğeleri için bir kapsayıcı görevi görerek PDF belgesinin içeriğini düzenlemeye ve kategorilere ayırmaya yardımcı olur. Belgenin mantıksal yapısını oluşturmada önemli bir rol oynar.

#### S: Aspose.PDF for .NET kullanarak tablo satırlarını biçimlendirmek için bir tablo yapısı öğesini nasıl oluşturabilir ve özelleştirebilirim?

A: Eğitim, bir tablo yapı öğesinin nasıl oluşturulacağını ve tablo satırlarını biçimlendirmek için özelliklerinin nasıl özelleştirileceğini açıklar. Arka plan rengi, kenarlıklar, satır yüksekliği, sayfalandırma, varsayılan hücre stili ve daha fazlası gibi yönleri kapsar.

#### S: Bir tablo satırındaki her bir hücrenin stillerini ve özelliklerini özelleştirebilir miyim?

A: Evet, bir tablo satırındaki tek tek hücrelerin stillerini ve özelliklerini özelleştirebilirsiniz. Eğitim, biçimlendirilmiş tablo satırındaki tablo hücreleri için arka plan rengi, kenarlıklar, metin rengi, dolgu ve daha fazlası gibi özelliklerin nasıl ayarlanacağını gösterir.

#### S: Biçimlendirilmiş tablo satırına üstbilgi, gövde satırları ve altbilgi nasıl ekleyebilirim?

A: Eğitimde, tablo yapısı öğesine başlıklar, gövde satırları ve bir alt bilgi oluşturma ve ekleme örnekleri sağlanır. Bu öğeler, eğitimde açıklanan özellikler kullanılarak daha da özelleştirilebilir.

#### S: PDF/UA uyumluluğu nedir ve etiketli PDF belgem için bunu nasıl doğrulayabilirim?

 A: PDF/UA uyumluluğu, PDF belgesinin erişilebilirlik standartlarına uygun olmasını sağlayarak engelli kullanıcılar için daha erişilebilir hale getirir. Eğitim, PDF/UA uyumluluğunun nasıl doğrulanacağını gösterir`Validate()` yöntemini kullanın ve bir XML uyumluluk raporu oluşturun.

#### S: Bu kavramları kendi .NET uygulamalarıma nasıl dahil edebilirim?

A: Sağlanan C# kaynak kodu örneklerini kendi .NET uygulamalarınızda tablo satır biçimlendirmesini uygulamak için bir kılavuz olarak kullanabilirsiniz. Kodu gereksinimlerinize uyacak şekilde değiştirin ve uyarlayın ve projelerinize entegre edin.

#### S: PDF belgelerindeki tablo satırlarını biçimlendirmek için önerilen en iyi uygulamalar var mı?

A: Tablo satırlarını biçimlendirirken, içeriğin okunabilirliğini ve erişilebilirliğini göz önünde bulundurun. Renklerin yeterli kontrasta sahip olduğundan, net ve okunaklı yazı tipleri kullandığından ve tutarlı bir düzen sağladığından emin olun. Erişilebilirlik standartlarının karşılandığından emin olmak için PDF/UA uyumluluğunu doğrulayın.

#### S: PDF belge özelleştirmesi için Aspose.PDF for .NET'in başka hangi özelliklerini keşfedebilirim?

A: Aspose.PDF for .NET, metin düzenleme, resim ekleme, form alanı yönetimi, dijital imzalar, açıklamalar ve daha fazlası dahil olmak üzere PDF belge özelleştirmesi için çok çeşitli özellikler sunar. Ek işlevleri keşfetmek için resmi belgelere ve kaynaklara başvurun.