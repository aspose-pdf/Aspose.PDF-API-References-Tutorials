---
title: Stil Tablo Hücresi
linktitle: Stil Tablo Hücresi
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF ile tablo hücrelerini nasıl biçimlendireceğinizi öğrenin. Tabloları oluşturma ve özelleştirmeye yönelik adım adım kılavuz.
type: docs
weight: 160
url: /tr/net/programming-with-tagged-pdf/style-table-cell/
---
.NET için Aspose.PDF kullanarak tablo hücrelerini biçimlendirmeyle ilgili bu ayrıntılı eğitime hoş geldiniz. Bu kılavuzda, tablo hücrelerini nasıl biçimlendireceğinizi anlamanıza yardımcı olmak için sağlanan C# kaynak kodunun her adımını ayrıntılı olarak açıklayacağız. Başlamadan önce .NET için Aspose.PDF'yi yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Yeni bir belge oluşturduk ve belge başlığını ve dilini ayarladık.

## Adım 3: Kök yapı elemanının elde edilmesi

Bu adımda belgemiz için kök yapı elemanını elde edeceğiz.

```csharp
// Kök yapı elemanını elde edin
StructureElement rootElement = taggedContent.RootElement;
```

Dizi elemanlarını barındıracak olan kök yapı elemanını elde ettik.

## Adım 4: Dizi yapı öğesini oluşturma

Şimdi belgemiz için yeni bir tablo yapı elemanı oluşturalım.

```csharp
// Dizi yapı öğesini oluşturun
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Yeni bir dizi yapı öğesi oluşturduk ve bunu kök yapı öğesine ekledik. Ayrıca tablo başlığı, gövdesi ve altbilgi öğelerini de oluşturduk.

## Adım 5: Tablo başlıklarını ekleme

Bu adımda tablomuza tablo başlıklarını ekleyeceğiz.

```csharp
// Tablodaki satır ve sütun sayısı
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Tablo başlığı satırını oluşturun
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Tablomuz için bir başlık satırı oluşturduk ve arka plan rengi, kenarlıklar, kenar boşlukları ve hizalama gibi biçimlendirme özelliklerine sahip başlık hücreleri ekledik.

## Adım 6: Tablo gövde satırlarını ekleme

Şimdi tablo gövde satırlarını tablomuza ekleyelim.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

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
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
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
```

Her tablo hücresi üzerinde yineleme yapmak için döngüler kullanarak tablonun gövdesine satırlar ekledik. Her hücre için arka plan rengi, kenarlıklar, kenar boşlukları, metin hizalaması vb. gibi biçimlendirme özellikleri ayarladık.

## Adım 7: Altbilgiyi ekleme

Son olarak tablomuza tablo alt bilgisini ekleyeceğiz.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Tablomuza bir alt bilgi oluşturduk ve metin içeren alt bilgi hücreleri ekledik.



## Adım 8: Etiketli PDF belgesini kaydetme

Artık biçimlendirilmiş tablomuzu içeren belgemizi oluşturduğumuza göre, bunu etiketli PDF belgesi olarak kaydedeceğiz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StyleTableCell.pdf");
```

Etiketli PDF dokümanını belirtilen dizine kaydettik.

## Adım 9: PDF/UA uyumluluğunun doğrulanması

Daha sonra dokümanımızın PDF/UA uygunluğunu doğrulayacağız.

```csharp
// PDF/UA uyumluluk kontrolü
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Etiketli PDF dokümanını yükledik ve bir XML raporu oluşturarak PDF/UA uyumluluğunu doğruladık.

### .NET için Aspose.PDF kullanılarak Stil Tablo Hücresi için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Kök yapı elemanını al
StructureElement rootElement = taggedContent.RootElement;

// Tablo yapı öğesini oluştur
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
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
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA uyumluluğunun kontrol edilmesi
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak tablo hücrelerini nasıl biçimlendireceğimizi öğrendik. Bir belgenin nasıl oluşturulacağını, başlıklar, gövde satırları ve altbilgi içeren bir tablonun nasıl ekleneceğini ve hücre stillerinin nasıl özelleştirileceğini gördük. Son olarak, etiketli PDF belgesini kaydettik ve PDF/UA uyumluluğunu doğruladık. Artık .NET uygulamalarınızda tablolar oluşturmak ve biçimlendirmek için .NET için Aspose.PDF'yi kullanabilirsiniz.

### SSS

#### S: Aspose.PDF for .NET kullanarak tablo hücrelerini biçimlendirme hakkındaki bu eğitimin amacı nedir?

A: Bu eğitim, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesindeki tablo hücrelerinin nasıl biçimlendirileceğine dair kapsamlı bir kılavuz sağlamayı amaçlamaktadır. Tablo hücresi biçimlendirmesini anlamanıza ve uygulamanıza yardımcı olmak için adım adım talimatlar ve C# kaynak kodu örnekleri içerir.

#### S: Bu eğitimi takip etmek için ön koşullar nelerdir?

A: Başlamadan önce, .NET için Aspose.PDF'yi yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Bu, projenizi Aspose.PDF kitaplığına başvuracak şekilde yapılandırmayı içerir.

#### S: Aspose.PDF for .NET kullanarak yeni bir PDF belgesi nasıl oluşturabilirim?

 A: Yeni bir PDF belgesi oluşturmak için bir örnek oluşturmanız gerekir`Document` Aspose.PDF kütüphanesinden nesne. Sağlanan C# kaynak kodu bir belgenin nasıl oluşturulacağını ve başlığının ve dilinin nasıl ayarlanacağını gösterir.

#### S: Bir PDF belgesinde kök yapı öğesinin önemi nedir?

A: Kök yapı öğesi, diğer yapı öğeleri için bir kapsayıcı görevi görerek PDF belgesinin içeriğini düzenlemeye ve kategorilere ayırmaya yardımcı olur. Belgenin mantıksal yapısını oluşturmada önemli bir rol oynar.

#### S: Aspose.PDF for .NET kullanarak bir tablo yapı öğesi nasıl oluşturabilir ve görünümünü nasıl özelleştirebilirim?

 A: Aşağıdakileri kullanarak bir tablo yapı öğesi oluşturabilirsiniz:`CreateTableElement()` yöntem. Sağlanan kaynak kodu, arka plan rengi, kenarlıklar, kenar boşlukları ve hizalama gibi özellikleri ayarlayarak tablonun üstbilgisi, gövdesi ve altbilgisi dahil görünümünün nasıl özelleştirileceğini gösterir.

#### S: Tablo gövdesine birden fazla satır ve sütun ekleyebilir ve bunların biçimlendirmesini özelleştirebilir miyim?

C: Evet, öğretici döngüler kullanılarak tablo gövdesine birden fazla satır ve sütunun nasıl ekleneceğini gösterir. Ayrıca arka plan rengi, kenarlıklar, metin hizalaması, yazı tipi stili ve daha fazlası gibi hücre biçimlendirmesini özelleştirmeye ilişkin örnekler de sağlar.

#### S: PDF/UA uyumluluğunun doğrulanmasının amacı nedir ve bu doğrulamayı nasıl gerçekleştirebilirim?

 A: PDF/UA uyumluluğunu doğrulamak, PDF belgesinin erişilebilirlik standartlarına uymasını sağlayarak engelli kullanıcılar için daha erişilebilir hale getirir. Eğitim, PDF/UA uyumluluğunun nasıl doğrulanacağını gösterir`Validate()` yöntemini kullanın ve bir XML raporu oluşturun.

#### S: Bu kavramları kendi .NET uygulamalarıma nasıl uygulayabilirim?

A: Sağlanan C# kaynak kodu örneklerini kendi .NET uygulamalarınızda tablo hücresi biçimlendirmesini uygulamak için bir kılavuz olarak kullanabilirsiniz. Kodu gereksinimlerinize uyacak şekilde özelleştirin ve projelerinize entegre edin.

#### S: PDF belgelerinde tablo hücrelerinin stili için önerilen en iyi uygulamalar var mı?

A: Tablo hücrelerini biçimlendirirken, erişilebilirlik gereksinimleri de dahil olmak üzere hedef kitlenizin ihtiyaçlarını göz önünde bulundurun. Okunabilirliği artırmak için zıt renkler, uygun yazı tipleri ve net hücre hizalaması kullanın. Ayrıca, erişilebilirlik standartlarının karşılandığından emin olmak için PDF/UA uyumluluğunu doğrulayın.

#### S: PDF belge düzenleme için Aspose.PDF for .NET'in başka hangi özelliklerini keşfedebilirim?

A: Aspose.PDF for .NET, metin çıkarma, resim ekleme, form alanı yönetimi, dijital imzalar ve daha fazlası dahil olmak üzere PDF belge düzenleme için geniş bir özellik yelpazesi sunar. Ek işlevler hakkında bilgi edinmek için resmi belgeleri ve kaynakları inceleyin.
