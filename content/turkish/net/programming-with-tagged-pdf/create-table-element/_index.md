---
title: Tablo Elemanı Oluştur
linktitle: Tablo Elemanı Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF ile dizi öğesi oluşturmaya yönelik adım adım kılavuz. Tablolar içeren dinamik PDF'leri kolayca oluşturun.
type: docs
weight: 80
url: /tr/net/programming-with-tagged-pdf/create-table-element/
---
Bu adım adım kılavuzda, .NET için Aspose.PDF kullanarak bir dizi öğesi oluşturma sürecinde size yol göstereceğiz. Aspose.PDF, PDF belgelerini programatik olarak düzenlemenize olanak tanıyan güçlü bir kütüphanedir. Dizi öğesi oluşturmak, dinamik PDF'ler oluştururken yaygın bir gerekliliktir ve Aspose.PDF bunu başarmak için kolay ve etkili bir yol sunar.

Gelin koda bir göz atalım ve Aspose.PDF for .NET kullanarak bir dizi öğesinin nasıl oluşturulacağını öğrenelim.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. .NET için Aspose.PDF kütüphanesi kuruldu.
2. C# programlama dilinin temel bilgisi.

## Adım 1: Ortamı kurma

Başlamak için C# geliştirme ortamınızı açın ve yeni bir proje oluşturun. Projenize .NET için Aspose.PDF kütüphanesine bir başvuru eklediğinizden emin olun.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgenin oluşturulması

 İlk adım, yeni bir PDF belgesi oluşturmaktır`Document` sınıf.

```csharp
// Belgeyi oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Burada ayrıca etiketli içerik için başlığı ve dili de belirliyoruz.

## Adım 3: Dizi öğesini oluşturma

Sonra, dizi öğesini oluşturmamız ve belgeye eklememiz gerekiyor. Kök yapı öğesini alarak başlıyoruz, sonra kullanarak yeni bir tablo öğesi oluşturuyoruz`CreateTableElement` Yöntem.

```csharp
// Kök yapı öğesini alın
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
TableTRElement trElement = tableTBodyElement.CreateTR();
trElement.AlternativeText = String.Format("Row {0}", rowIndex);
for (colIndex = 0; colIndex < colCount; colIndex++)
{
int colSpan = 1;
int rowSpan = 1;
if (colIndex == 1 && rowIndex == 1)
{
colSpan = 2;
rowSpan = 2;
}
else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
{
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
tdElement.BackgroundColor = Color.Yellow;
tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
tdElement.IsNoBorder = false;
tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
tdElement.Alignment = HorizontalAlignment.Center;
TextState cellTextState = new TextState();
cellTextState.ForegroundColor = Color.DarkBlue;
cellTextState.FontSize = 7.5F;
cellTextState.FontStyle = FontStyles.Bold;
cellTextState.Font = FontRepository.FindFont("Arial");
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA uyumluluk kontrolü
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### .NET için Aspose.PDF kullanarak Tablo Elemanı Oluşturma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Kök yapı elemanını al
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA uyumluluğunun kontrol edilmesi
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

.NET için Aspose.PDF kullanarak bir dizi öğesinin nasıl oluşturulacağını öğrendiniz. Artık bu yöntemi kullanarak dinamik tablolar içeren PDF belgeleri oluşturabilirsiniz. Aspose.PDF'nin tüm potansiyelini keşfetmek için daha fazla özelliğini keşfetmekten çekinmeyin.

### SSS

#### S: PDF belgesinde dizi öğesi nedir ve .NET için Aspose.PDF kullanarak neden bir tane oluşturmam gerekir?

A: PDF belgesindeki bir dizi öğesi, genellikle tablolar veya ızgaralar oluşturmak için kullanılan yapılandırılmış bir veri koleksiyonunu temsil eder. Tablo bilgileri veya ızgaralar gibi yapılandırılmış veri sunumu gerektiren dinamik PDF'ler oluştururken .NET için Aspose.PDF kullanarak bir dizi öğesi oluşturmanız gerekebilir.

#### S: Aspose.PDF for .NET bir dizi öğesi oluşturma sürecini nasıl basitleştirir?

A: Aspose.PDF for .NET, bir PDF belgesinde dizi öğelerini (tabloları) programatik olarak oluşturmanıza, özelleştirmenize ve yönetmenize olanak tanıyan kapsamlı bir sınıf ve yöntem kümesi sağlar. Bu, manuel PDF düzenleme ihtiyacını ortadan kaldırır ve yapılandırılmış veri gösterimlerinin oluşturulmasını kolaylaştırır.

#### S: Aspose.PDF for .NET kullanarak bir dizi öğesi oluşturmanın temel adımları nelerdir?

A: Temel adımlar arasında ortamın kurulması, belgenin oluşturulması, kök yapı öğesinin edinilmesi, bir tablo öğesinin oluşturulması, tablo içindeki satırların ve hücrelerin tanımlanması ve öğeler için biçimlendirme ve özelliklerin belirtilmesi yer alır. Sağlanan kod örneği bu adımları göstermektedir.

####  S: Rolü nedir?`taggedContent` object play in creating an array element?

 A:`taggedContent` nesne, belgenin kendisinden elde edilen`TaggedContent`özellik, PDF belgesindeki etiketli içeriğin yapısını tanımlamanıza olanak tanır. Bu, dizi öğelerini ve bunların alt öğelerini hiyerarşik bir şekilde oluşturmayı ve düzenlemeyi içerir.

#### S: Kod, oluşturulan dizi öğesinin erişilebilirliğini ve semantiğini nasıl sağlar?

 A: Kod şu gibi nitelikleri ayarlar:`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , Ve`ColSpan` Dizi öğesinin erişilebilirliğini ve semantiğini geliştirmek için. Bu nitelikler, verilerin iyi yapılandırılmış, bilgilendirici ve görsel olarak çekici bir temsiline katkıda bulunur.

#### S: Dizi elemanlarının oluşturulması bağlamında PDF/UA uyumluluğunun önemi nedir?

 A: PDF/UA (Evrensel Erişilebilirlik) uyumluluğu, oluşturulan PDF belgelerinin engelli kullanıcılar tarafından erişilebilir olmasını ve belirli erişilebilirlik standartlarını karşılamasını sağlar. Kod örneği, PDF/UA uyumluluğunu şu şekilde kontrol eder:`Validate` kapsayıcı ve erişilebilir belgeler oluşturmanıza yardımcı olan bir yöntemdir.

#### S: Dizi elemanlarının biçimlendirmesini ve görünümünü daha fazla özelleştirebilir miyim?

A: Evet, arka plan rengi, kenarlık stili, yazı tipi boyutu ve hizalama gibi nitelikleri ayarlayarak dizi öğelerinin biçimlendirmesini ve görünümünü özelleştirebilirsiniz. Aspose.PDF for .NET, görsel sunumu gereksinimlerinize göre uyarlamak için çok çeşitli özellikler sunar.

#### S: Bu bilgiyi daha karmaşık tablo yapıları oluşturmak veya dizi elemanlarını daha büyük PDF belgelerine dahil etmek için nasıl genişletebilirim?

A: Birden fazla dizi öğesini birleştirme, iç içe tablolar oluşturma, başlıklar ve altbilgiler ekleme ve dizi öğelerini daha büyük PDF düzenlerine entegre etme gibi .NET için Aspose.PDF'nin ek özelliklerini keşfederek bu bilgiyi genişletebilirsiniz. Kütüphanenin belgeleri ve örnekleri bu gelişmiş senaryolar için rehberlik sağlar.

#### S: Dizi elemanlarını doldurmak için veritabanları veya elektronik tablolar gibi harici kaynaklardan veri içe aktarmak mümkün müdür?

A: Evet, dizi öğelerini doldurmak için harici kaynaklardan veri içe aktarabilirsiniz. Veritabanlarından, elektronik tablolardan veya diğer kaynaklardan veri almak ve ardından dizi öğelerini buna göre doldurmak için C# dilindeki veri alma ve dönüştürme tekniklerini kullanabilirsiniz.

#### S: Bu eğitimden edindiğim bilgileri, programatik olarak oluşturduğum PDF belgelerinin kalitesini ve kullanılabilirliğini artırmak için nasıl kullanabilirim?

A: Bu eğitimden edinilen bilgi, PDF belgelerinde yapılandırılmış ve görsel olarak çekici dizi öğeleri (tablolar) oluşturmanıza olanak tanır. Bu teknikleri dahil ederek, dinamik olarak oluşturulan PDF'lerin okunabilirliğini, erişilebilirliğini ve kullanıcı deneyimini iyileştirebilir, bunları daha bilgilendirici ve kullanıcı dostu hale getirebilirsiniz.