---
title: Tablo Öğesi Oluştur
linktitle: Tablo Öğesi Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir dizi öğesi oluşturmak için adım adım kılavuz. Tablolarla kolayca dinamik PDF'ler oluşturun.
type: docs
weight: 80
url: /tr/net/programming-with-tagged-pdf/create-table-element/
---
Bu adım adım kılavuzda, Aspose.PDF for .NET kullanarak bir dizi öğesi oluşturma sürecinde size yol göstereceğiz. Aspose.PDF, PDF belgelerini programlı olarak değiştirmenize izin veren güçlü bir kitaplıktır. Dinamik PDF'ler oluşturulurken bir dizi öğesi oluşturmak yaygın bir gerekliliktir ve Aspose.PDF bunu gerçekleştirmenin kolay ve verimli bir yolunu sunar.

Şimdi koda inelim ve Aspose.PDF for .NET kullanarak bir dizi öğesinin nasıl oluşturulacağını öğrenelim.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.PDF kitaplığı for .NET kurulu.
2. C# programlama dili hakkında temel bilgi.

## 1. Adım: Ortamı ayarlama

Başlamak için C# geliştirme ortamınızı açın ve yeni bir proje oluşturun. Projenizde .NET için Aspose.PDF kitaplığına bir referans eklediğinizden emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi oluşturma

 İlk adım, kullanarak yeni bir PDF belgesi oluşturmaktır.`Document` sınıf.

```csharp
// belgeyi oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Burada etiketlenen içeriğin başlığını ve dilini de ayarlıyoruz.

## 3. Adım: Dizi öğesini oluşturma

Ardından, dizi öğesini oluşturmamız ve onu belgeye eklememiz gerekiyor. Kök yapı elemanını alarak başlıyoruz, ardından kullanarak yeni bir tablo elemanı oluşturuyoruz.`CreateTableElement` yöntem.

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

### Aspose.PDF for .NET kullanarak Create Table Element için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Kök yapı öğesini al
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

// PDF/UA uyumluluğunu kontrol etme
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Aspose.PDF for .NET kullanarak bir dizi öğesinin nasıl oluşturulacağını öğrendiniz. Artık bu yöntemi kullanarak dinamik tablolarla PDF belgeleri oluşturabilirsiniz. Tam potansiyelini keşfetmek için Aspose.PDF'nin diğer özelliklerini keşfetmekten çekinmeyin.

### SSS

#### S: Bir PDF belgesindeki dizi öğesi nedir ve neden Aspose.PDF for .NET kullanarak bir tane oluşturmam gerekiyor?

Y: PDF belgesindeki bir dizi öğesi, genellikle tablolar veya ızgaralar oluşturmak için kullanılan yapılandırılmış bir veri koleksiyonunu temsil eder. Tablo bilgileri veya ızgaralar gibi yapılandırılmış veri sunumu gerektiren dinamik PDF'ler oluştururken Aspose.PDF for .NET kullanarak bir dizi öğesi oluşturmanız gerekebilir.

#### S: Aspose.PDF for .NET, bir dizi öğesi oluşturma sürecini nasıl kolaylaştırır?

Y: Aspose.PDF for .NET, bir PDF belgesinde dizi öğelerini (tablolar) programlı olarak oluşturmanıza, özelleştirmenize ve yönetmenize olanak tanıyan kapsamlı bir sınıflar ve yöntemler seti sağlar. Bu, manuel PDF düzenleme ihtiyacını ortadan kaldırır ve yapılandırılmış veri sunumlarının oluşturulmasını kolaylaştırır.

#### S: Aspose.PDF for .NET kullanarak bir dizi öğesi oluşturmanın temel adımları nelerdir?

C: Anahtar adımlar arasında ortamın ayarlanması, belgenin oluşturulması, kök yapı öğesinin elde edilmesi, bir tablo öğesinin oluşturulması, tablo içindeki satırların ve hücrelerin tanımlanması ve öğeler için biçimlendirme ve özelliklerin belirtilmesi yer alır. Sağlanan kod örneği, bu adımları gösterir.

####  S: Hangi rolü yapar?`taggedContent` object play in creating an array element?

 C:`taggedContent` belgeden elde edilen nesne`TaggedContent`özelliği, PDF belgesindeki etiketli içeriğin yapısını tanımlamanıza olanak tanır. Bu, dizi öğelerini ve bunların alt öğelerini hiyerarşik bir şekilde oluşturmayı ve düzenlemeyi içerir.

#### S: Kod, oluşturulan dizi öğesinin erişilebilirliğini ve anlamını nasıl sağlıyor?

 C: Kod, aşağıdaki gibi öznitelikleri ayarlar:`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , Ve`ColSpan` dizi öğesinin erişilebilirliğini ve anlamını geliştirmek için. Bu özellikler, verilerin iyi yapılandırılmış, bilgilendirici ve görsel olarak çekici bir temsiline katkıda bulunur.

#### S: Dizi öğeleri oluşturma bağlamında PDF/UA uyumluluğunun önemi nedir?

 Y: PDF/UA (Evrensel Erişilebilirlik) uyumluluğu, oluşturulan PDF belgelerinin engelli kullanıcılar tarafından erişilebilir olmasını ve belirli erişilebilirlik standartlarını karşılamasını sağlar. Kod örneği, şunu kullanarak PDF/UA uyumluluğunu kontrol eder:`Validate` yöntem, kapsayıcı ve erişilebilir belgeler oluşturmanıza yardımcı olur.

#### S: Dizi öğelerinin biçimlendirmesini ve görünümünü daha da özelleştirebilir miyim?

C: Evet, arka plan rengi, kenarlık stili, yazı tipi boyutu ve hizalama gibi nitelikleri ayarlayarak dizi öğelerinin biçimlendirmesini ve görünümünü özelleştirebilirsiniz. Aspose.PDF for .NET, görsel sunumu gereksinimlerinize göre uyarlamak için çok çeşitli özellikler sunar.

#### S: Bu bilgiyi daha karmaşık tablo yapıları oluşturmak veya dizi öğelerini daha büyük PDF belgelerine dahil etmek için nasıl genişletebilirim?

C: Aspose.PDF for .NET'in çoklu dizi öğelerini birleştirme, iç içe tablolar oluşturma, üstbilgiler ve altbilgiler ekleme ve dizi öğelerini daha büyük PDF mizanpajlarına entegre etme gibi ek özelliklerini keşfederek bu bilgiyi genişletebilirsiniz. Kitaplığın belgeleri ve örnekleri, bu gelişmiş senaryolar için rehberlik sağlar.

#### S: Dizi öğelerini doldurmak için veritabanları veya elektronik tablolar gibi harici kaynaklardan veri almak mümkün müdür?

C: Evet, dizi öğelerini doldurmak için harici kaynaklardan veri alabilirsiniz. Veritabanlarından, elektronik tablolardan veya diğer kaynaklardan veri almak ve ardından dizi öğelerini buna göre doldurmak için C# dilinde veri alma ve dönüştürme tekniklerini kullanabilirsiniz.

#### S: Programlı olarak oluşturduğum PDF belgelerinin kalitesini ve kullanılabilirliğini artırmak için bu eğitimden edindiğim bilgileri nasıl kullanabilirim?

C: Bu eğitimden elde edilen bilgiler, PDF belgelerinde yapılandırılmış ve görsel olarak çekici dizi öğeleri (tablolar) oluşturmanıza olanak tanır. Bu teknikleri dahil ederek, dinamik olarak oluşturulmuş PDF'lerin okunabilirliğini, erişilebilirliğini ve kullanıcı deneyimini iyileştirerek onları daha bilgilendirici ve kullanıcı dostu hale getirebilirsiniz.