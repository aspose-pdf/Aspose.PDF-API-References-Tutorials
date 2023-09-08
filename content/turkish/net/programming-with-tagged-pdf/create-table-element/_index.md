---
title: Tablo Öğesi Oluştur
linktitle: Tablo Öğesi Oluştur
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile dizi öğesi oluşturmak için adım adım kılavuz. Tablolarla kolayca dinamik PDF'ler oluşturun.
type: docs
weight: 80
url: /tr/net/programming-with-tagged-pdf/create-table-element/
---
Bu adım adım kılavuzda, Aspose.PDF for .NET'i kullanarak bir dizi öğesi oluşturma sürecinde size yol göstereceğiz. Aspose.PDF, PDF belgelerini programlı olarak değiştirmenizi sağlayan güçlü bir kütüphanedir. Dinamik PDF'ler oluştururken bir dizi öğesi oluşturmak yaygın bir gereksinimdir ve Aspose.PDF bunu başarmanın kolay ve etkili bir yolunu sunar.

Hadi kodun derinliklerine inelim ve Aspose.PDF for .NET kullanarak bir dizi öğesinin nasıl oluşturulacağını öğrenelim.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. .NET için Aspose.PDF kütüphanesi kuruldu.
2. C# programlama dili hakkında temel bilgi.

## 1. Adım: Ortamı ayarlama

Başlamak için C# geliştirme ortamınızı açın ve yeni bir proje oluşturun. Projenize .NET için Aspose.PDF kütüphanesine bir referans eklediğinizden emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi oluşturma

 İlk adım, kullanarak yeni bir PDF belgesi oluşturmaktır.`Document` sınıf.

```csharp
// Belgeyi oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Burada etiketlenen içeriğin başlığını ve dilini de ayarlıyoruz.

## 3. Adım: Dizi öğesini oluşturma

Daha sonra dizi elemanını oluşturup belgeye eklememiz gerekiyor. Kök yapı elemanını alarak başlıyoruz, ardından aşağıdaki komutu kullanarak yeni bir tablo elemanı oluşturuyoruz.`CreateTableElement` yöntem.

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

### Aspose.PDF for .NET kullanarak Tablo Öğesi Oluşturma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Doküman oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

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

// Etiketli Pdf Belgesini Kaydet
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA uyumluluğunu kontrol etme
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Aspose.PDF for .NET'i kullanarak bir dizi öğesinin nasıl oluşturulacağını öğrendiniz. Artık bu yöntemi kullanarak dinamik tablolara sahip PDF belgeleri oluşturabilirsiniz. Aspose.PDF'in tüm potansiyelini keşfetmek için daha fazla özelliğini keşfetmekten çekinmeyin.

### SSS'ler

#### S: PDF belgesindeki dizi öğesi nedir ve neden Aspose.PDF for .NET kullanarak bir dizi öğesi oluşturmam gerekiyor?

C: Bir PDF belgesindeki dizi öğesi, genellikle tablolar veya ızgaralar oluşturmak için kullanılan, yapılandırılmış bir veri koleksiyonunu temsil eder. Tablo bilgileri veya ızgaralar gibi yapılandırılmış veri sunumu gerektiren dinamik PDF'ler oluştururken Aspose.PDF for .NET'i kullanarak bir dizi öğesi oluşturmanız gerekebilir.

#### S: Aspose.PDF for .NET bir dizi öğesi oluşturma sürecini nasıl basitleştirir?

C: Aspose.PDF for .NET, bir PDF belgesindeki dizi öğelerini (tabloları) programlı olarak oluşturmanıza, özelleştirmenize ve yönetmenize olanak tanıyan kapsamlı bir sınıf ve yöntemler seti sağlar. Bu, manuel PDF manipülasyonu ihtiyacını ortadan kaldırır ve yapılandırılmış veri temsillerinin oluşturulmasını kolaylaştırır.

#### S: Aspose.PDF for .NET kullanarak bir dizi öğesi oluşturmanın temel adımları nelerdir?

C: Temel adımlar arasında ortamın kurulması, belgenin oluşturulması, kök yapı öğesinin elde edilmesi, bir tablo öğesi oluşturulması, tablo içindeki satırların ve hücrelerin tanımlanması ve öğeler için biçimlendirmenin ve özelliklerin belirtilmesi yer alır. Sağlanan kod örneği bu adımları göstermektedir.

####  S: Hangi rol`taggedContent` object play in creating an array element?

 C:`taggedContent` belgeden elde edilen nesne`TaggedContent`özelliği, PDF belgesindeki etiketli içeriğin yapısını tanımlamanıza olanak tanır. Bu, dizi öğelerini ve bunların alt öğelerini hiyerarşik bir şekilde oluşturmayı ve düzenlemeyi içerir.

#### S: Kod, oluşturulan dizi öğesinin erişilebilirliğini ve anlambilimini nasıl sağlıyor?

 C: Kod, aşağıdaki gibi nitelikleri ayarlar:`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , Ve`ColSpan` dizi öğesinin erişilebilirliğini ve anlambilimini geliştirmek için. Bu nitelikler, verilerin iyi yapılandırılmış, bilgilendirici ve görsel olarak çekici bir temsiline katkıda bulunur.

#### S: Dizi öğeleri oluşturma bağlamında PDF/UA uyumluluğunun önemi nedir?

 C: PDF/UA (Evrensel Erişilebilirlik) uyumluluğu, oluşturulan PDF belgelerinin engelli kullanıcılar tarafından erişilebilir olmasını ve belirli erişilebilirlik standartlarını karşılamasını sağlar. Kod örneği, PDF/UA uyumluluğunu aşağıdaki komutu kullanarak kontrol eder:`Validate` kapsayıcı ve erişilebilir belgeler oluşturmanıza yardımcı olan yöntem.

#### S: Dizi öğelerinin biçimlendirmesini ve görünümünü daha da özelleştirebilir miyim?

C: Evet, arka plan rengi, kenarlık stili, yazı tipi boyutu ve hizalama gibi nitelikleri ayarlayarak dizi öğelerinin biçimlendirmesini ve görünümünü özelleştirebilirsiniz. Aspose.PDF for .NET, görsel sunumu ihtiyaçlarınıza göre uyarlamak için geniş bir özellik yelpazesi sunar.

#### S: Bu bilgiyi daha karmaşık tablo yapıları oluşturacak veya dizi öğelerini daha büyük PDF belgelerine dahil edecek şekilde nasıl genişletebilirim?

C: Aspose.PDF for .NET'in birden fazla dizi öğesini birleştirmek, iç içe geçmiş tablolar oluşturmak, üstbilgi ve altbilgiler eklemek ve dizi öğelerini daha büyük PDF düzenlerine entegre etmek gibi ek özelliklerini keşfederek bu bilgiyi genişletebilirsiniz. Kitaplığın belgeleri ve örnekleri bu gelişmiş senaryolar için rehberlik sağlar.

#### S: Dizi öğelerini doldurmak için veritabanları veya elektronik tablolar gibi harici kaynaklardan veri almak mümkün müdür?

C: Evet, dizi öğelerini doldurmak için harici kaynaklardan verileri içe aktarabilirsiniz. Veritabanlarından, elektronik tablolardan veya diğer kaynaklardan veri almak ve ardından dizi öğelerini buna göre doldurmak için C#'taki veri alma ve dönüştürme tekniklerini kullanabilirsiniz.

#### S: Programlı olarak oluşturduğum PDF belgelerinin kalitesini ve kullanılabilirliğini geliştirmek için bu eğitimden edindiğim bilgileri nasıl kullanabilirim?

C: Bu eğitimden edinilen bilgiler, PDF belgelerinde yapılandırılmış ve görsel olarak çekici dizi öğeleri (tablolar) oluşturmanıza olanak tanır. Bu teknikleri birleştirerek, dinamik olarak oluşturulan PDF'lerin okunabilirliğini, erişilebilirliğini ve kullanıcı deneyimini iyileştirerek onları daha bilgilendirici ve kullanıcı dostu hale getirebilirsiniz.