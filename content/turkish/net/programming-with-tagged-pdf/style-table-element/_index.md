---
title: Stil Tablo Elemanı
linktitle: Stil Tablo Elemanı
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF ile tablo öğelerinin nasıl biçimlendirileceğini öğrenin. Stilleri ve özellikleri özelleştirmek için adım adım kılavuz.
type: docs
weight: 170
url: /tr/net/programming-with-tagged-pdf/style-table-element/
---
Bu ayrıntılı eğitimde, Aspose.PDF for .NET kullanarak dizi öğesini biçimlendirmek için sağlanan C# kaynak kodunu adım adım inceleyeceğiz. Dizi öğesinin stillerini ve özelliklerini nasıl özelleştireceğinizi anlamak için aşağıdaki talimatları izleyin.

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
taggedContent.SetTitle("Example of table formatting");
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

## Adım 5: Dizi Elemanı Stillerini ve Özelliklerini Özelleştirme

Bu adımda dizi elemanının stillerini ve özelliklerini özelleştireceğiz.

```csharp
// Dizi öğesinin stillerini ve özelliklerini özelleştirin
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

// Tekrarlanan satırların stilini özelleştirin
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Tablo öğesini özelleştirmek için arka plan rengi, kenarlıklar, hizalama, varsayılan hücre stili, kenar boşlukları, sütun genişliği vb. gibi çeşitli özellikler kullandık.

## Adım 6: Tablo başlıklarını, gövdeyi ve alt bilgiyi ekleyin

Şimdi tablo elemanına tablo başlıklarını, gövdesini ve altbilgisini ekleyelim.
```csharp
// Tablo başlıkları ekle
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

// Tablonun taban çizgisini ekleyin
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Tabloya başlık, gövde satırları ve alt bilgi satırını ilgili elemanları kullanarak ekledik.

## Adım 7: Etiketli PDF belgesini kaydetme

Artık biçimlendirilmiş tablo öğesiyle belgemizi oluşturduğumuza göre, bunu etiketli PDF belgesi olarak kaydedeceğiz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StyleTableElement.pdf");
```

Etiketli PDF dokümanını belirtilen dizine kaydettik.

## Adım 8: PDF/UA uyumluluğunun doğrulanması

Daha sonra dokümanımızın PDF/UA uygunluğunu doğrulayacağız.

```csharp
// PDF/UA uyumluluk kontrolü
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Etiketli PDF dokümanını yükledik ve bir XML raporu oluşturarak PDF/UA uyumluluğunu doğruladık.

### .NET için Aspose.PDF kullanılarak Stil Tablosu Öğesi için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Kök yapı elemanını al
StructureElement rootElement = taggedContent.RootElement;

// Tablo yapı öğesini oluştur
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

// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "StyleTableElement.pdf");

// PDF/UA uyumluluğunun kontrol edilmesi
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET ile dizi öğesinin nasıl biçimlendirileceğini öğrendik. Tablo öğesinin stillerini ve özelliklerini özelleştirdik, başlıklar, gövde satırları ve bir alt bilgi ekledik, etiketli PDF belgesini kaydettik ve PDF/UA uyumluluğunu doğruladık.

### SSS

#### S: Aspose.PDF for .NET kullanarak dizi öğelerini biçimlendirme hakkındaki bu eğitimin amacı nedir?

A: Bu eğitimin amacı, .NET için Aspose.PDF kullanarak bir PDF belgesindeki dizi öğesini biçimlendirme sürecinde size rehberlik etmektir. Dizi öğesinin stillerini ve özelliklerini özelleştirmenize yardımcı olmak için adım adım talimatlar ve C# kaynak kodu örnekleri sağlar.

#### S: Bu eğitimi takip etmek için ön koşullar nelerdir?

A: Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET kullanacak şekilde ayarladığınızdan emin olun. Bu, Aspose.PDF kitaplığını yüklemeyi ve projenizi buna başvuracak şekilde yapılandırmayı içerir.

#### S: Aspose.PDF for .NET kullanarak yeni bir PDF belgesi nasıl oluşturabilirim ve başlığını ve dilini nasıl ayarlayabilirim?

 A: Yeni bir PDF belgesi oluşturmak için bir`Document` Aspose.PDF kütüphanesinden nesne. Eğitimin sağladığı C# kaynak kodu, bir belgenin nasıl oluşturulacağını ve başlığının ve dil özelliklerinin nasıl ayarlanacağını gösterir.

#### S: Bir PDF belgesinde kök yapı öğesinin önemi nedir?

A: Kök yapı öğesi, diğer yapı öğeleri için bir kapsayıcı görevi görerek PDF belgesinin içeriğini düzenlemeye ve kategorilere ayırmaya yardımcı olur. Belgenin mantıksal yapısını oluşturmada önemli bir rol oynar.

#### S: Aspose.PDF for .NET kullanarak bir dizi yapı öğesini nasıl oluşturabilir ve özelleştirebilirim?

 A: Bir dizi yapı elemanını kullanarak oluşturabilirsiniz`CreateTableElement()` yöntem. Eğitimin kaynak kodu, arka plan rengi, kenarlıklar, hizalama, sütun genişliği ve daha fazlası gibi tablo öğesinin çeşitli özelliklerini özelleştirmeye yönelik örnekler sağlar.

#### S: Dizi öğesi içindeki tablo hücrelerinin stillerini ve özelliklerini özelleştirebilir miyim?

C: Evet, eğitim, başlıklar, gövde satırları ve altbilgi dahil olmak üzere tüm tablo öğesinin stillerinin ve özelliklerinin nasıl özelleştirileceğini kapsar. Ancak, tek tek tablo hücrelerinin özelleştirilmesini özel olarak ele almaz.

#### S: Tablo öğesine üstbilgi, gövde satırları ve altbilgi nasıl ekleyebilirim?

A: Bu eğitimde, Aspose.PDF for .NET tarafından sağlanan uygun yöntemler kullanılarak tablo öğesine üstbilgilerin, gövde satırlarının ve altbilginin nasıl oluşturulacağı ve ekleneceği açıklanmaktadır.

#### S: PDF/UA uyumluluğu nedir ve etiketli PDF belgem için bunu nasıl doğrulayabilirim?

 A: PDF/UA uyumluluğu, PDF belgesinin erişilebilirlik standartlarına uygun olmasını sağlayarak engelli kullanıcılar için daha erişilebilir hale getirir. Eğitim, PDF/UA uyumluluğunun nasıl doğrulanacağını gösterir`Validate()` yöntemini kullanın ve bir XML uyumluluk raporu oluşturun.

#### S: Bu kavramları kendi .NET uygulamalarıma nasıl dahil edebilirim?

A: Sağlanan C# kaynak kodu örneklerini kendi .NET uygulamalarınızda dizi öğesi biçimlendirmesini uygulamak için bir kılavuz olarak kullanabilirsiniz. Kodu gereksinimlerinize uyacak şekilde değiştirin ve uyarlayın ve projelerinize entegre edin.

#### S: PDF belgelerindeki dizi öğelerini biçimlendirmek için önerilen en iyi uygulamalar var mı?

A: Dizi öğelerini (tabloları) biçimlendirirken, içeriğin okunabilirliğini ve erişilebilirliğini göz önünde bulundurun. Net ve okunaklı yazı tipleri, uygun renkler kullanın ve tutarlı bir düzen koruyun. Erişilebilirlik standartlarının karşılandığından emin olmak için PDF/UA uyumluluğunu doğrulayın.

#### S: PDF belge özelleştirmesi için Aspose.PDF for .NET'in başka hangi özelliklerini keşfedebilirim?

A: Aspose.PDF for .NET, metin düzenleme, resim ekleme, form alanı yönetimi, dijital imzalar, açıklamalar ve daha fazlası dahil olmak üzere PDF belge özelleştirmesi için bir dizi özellik sunar. Ek işlevleri keşfetmek için resmi belgelere ve kaynaklara başvurun.