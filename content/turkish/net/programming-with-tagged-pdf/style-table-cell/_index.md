---
title: Stil Tablosu Hücresi
linktitle: Stil Tablosu Hücresi
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile tablo hücrelerine nasıl stil uygulayacağınızı öğrenin. Tabloları oluşturmaya ve özelleştirmeye yönelik adım adım kılavuz.
type: docs
weight: 160
url: /tr/net/programming-with-tagged-pdf/style-table-cell/
---
Aspose.PDF for .NET kullanarak tablo hücrelerini biçimlendirmeye ilişkin bu ayrıntılı eğitime hoş geldiniz. Bu kılavuzda, tablo hücrelerine nasıl stil uygulayacağınızı anlamanıza yardımcı olmak için sağlanan C# kaynak kodunun her adımını ayrıntılı olarak açıklayacağız. Başlamadan önce Aspose.PDF for .NET'i yüklediğinizden ve geliştirme ortamınızı kurduğunuzdan emin olun.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Yeni bir belge oluşturduk ve belge başlığını ve dilini belirledik.

## Adım 3: Kök yapı öğesinin elde edilmesi

Bu adımda belgemiz için kök yapı elemanını alacağız.

```csharp
//Kök yapı öğesini edinin
StructureElement rootElement = taggedContent.RootElement;
```

Dizi elemanları için kap görevi görecek kök yapı elemanını elde ettik.

## Adım 4: Dizi yapısı öğesinin oluşturulması

Şimdi belgemiz için yeni bir tablo yapısı öğesi oluşturalım.

```csharp
// Dizi yapısı öğesini oluşturun
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Yeni bir dizi yapısı elemanı oluşturduk ve onu kök yapı elemanına ekledik. Ayrıca tablo üstbilgisi, gövdesi ve altbilgi öğelerini de oluşturduk.

## 5. Adım: Tablo üstbilgilerini ekleme

Bu adımda tablo başlıklarını tablomuza ekleyeceğiz.

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

## Adım 6: Tablo gövdesi satırlarını ekleme

Şimdi tablo gövdesi satırlarını tablomuza ekleyelim.
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

Her tablo hücresi üzerinde yineleme yapmak için döngüler kullanarak tablonun gövdesine satırlar ekledik. Her hücre için arka plan rengi, kenarlıklar, kenar boşlukları, metin hizalaması vb. gibi biçimlendirme özelliklerini ayarlarız.

## Adım 7: Altbilgiyi ekleme

Son olarak tablo altbilgisini tablomuza ekleyeceğiz.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Tablomuz için bir alt bilgi oluşturduk ve metin içeren alt bilgi hücreleri ekledik.



## Adım 8: Etiketli PDF belgesini kaydetme

Artık belgemizi stil tablosuyla oluşturduğumuza göre, onu etiketli bir PDF belgesi olarak kaydedeceğiz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StyleTableCell.pdf");
```

Etiketli PDF belgesini belirtilen dizine kaydettik.

## 9. Adım: PDF/UA uyumluluk doğrulaması

Daha sonra belgemizin PDF/UA uygunluğunu doğrulayacağız.

```csharp
// PDF/UA uyumluluk kontrolü
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Etiketli PDF belgesini yükledik ve bir XML raporu oluşturarak PDF/UA uyumluluğunu doğruladık.

### Aspose.PDF for .NET kullanan Stil Tablosu Hücresi için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Doküman oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Kök yapı öğesini alın
StructureElement rootElement = taggedContent.RootElement;

// Tablo yapısı öğesi oluştur
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

// Etiketli Pdf Belgesini Kaydet
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA uyumluluğunu kontrol etme
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak tablo hücrelerine nasıl stil uygulayacağımızı öğrendik. Bir belgenin nasıl oluşturulacağını, üstbilgiler, gövde satırları ve altbilgi içeren bir tablonun nasıl ekleneceğini ve hücre stillerinin nasıl özelleştirileceğini gördük. Son olarak etiketli PDF belgesini kaydettik ve PDF/UA uyumluluğunu doğruladık. Artık .NET uygulamalarınızda tablolar oluşturmak ve stil vermek için Aspose.PDF for .NET'i kullanabilirsiniz.

### SSS'ler

#### S: Tablo hücrelerini Aspose.PDF for .NET kullanarak biçimlendirmeye yönelik bu eğitimin amacı nedir?

C: Bu eğitimin amacı, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesindeki tablo hücrelerine nasıl stil uygulanacağı konusunda kapsamlı bir kılavuz sağlamaktır. Tablo hücresi biçimlendirmesini anlamanıza ve uygulamanıza yardımcı olacak adım adım talimatları ve C# kaynak kodu örneklerini kapsar.

#### S: Bu eğitimi takip etmenin önkoşulları nelerdir?

C: Başlamadan önce Aspose.PDF for .NET'i yüklediğinizden ve geliştirme ortamınızı kurduğunuzdan emin olun. Buna projenizi Aspose.PDF kütüphanesine referans verecek şekilde yapılandırmak da dahildir.

#### S: Aspose.PDF for .NET'i kullanarak nasıl yeni bir PDF belgesi oluşturabilirim?

C: Yeni bir PDF belgesi oluşturmak için bir örnek oluşturmanız gerekir.`Document` Aspose.PDF kütüphanesinden nesne. Sağlanan C# kaynak kodu, bir belgenin nasıl oluşturulacağını ve başlığının ve dilinin nasıl ayarlanacağını gösterir.

#### S: Bir PDF belgesindeki kök yapı öğesinin önemi nedir?

C: Kök yapı öğesi, diğer yapı öğeleri için bir kap görevi görerek PDF belgesinin içeriğinin düzenlenmesine ve kategorize edilmesine yardımcı olur. Belgenin mantıksal yapısının oluşturulmasında çok önemli bir rol oynar.

#### S: Aspose.PDF for .NET'i kullanarak bir tablo yapısı öğesini nasıl oluşturabilir ve görünümünü nasıl özelleştirebilirim?

 C: Aşağıdakileri kullanarak bir tablo yapısı öğesi oluşturabilirsiniz:`CreateTableElement()` yöntem. Sağlanan kaynak kodu, arka plan rengi, kenarlıklar, kenar boşlukları ve hizalama gibi özellikleri ayarlayarak tablonun üstbilgisi, gövdesi ve altbilgisi dahil görünümünün nasıl özelleştirileceğini gösterir.

#### S: Tablo gövdesine birden çok satır ve sütun ekleyip bunların biçimlendirmesini özelleştirebilir miyim?

C: Evet, eğitimde döngüler kullanılarak tablo gövdesine birden fazla satır ve sütunun nasıl ekleneceği gösterilmektedir. Ayrıca arka plan rengi, kenarlıklar, metin hizalaması, yazı tipi stili ve daha fazlası gibi hücre biçimlendirmesinin özelleştirilmesine ilişkin örnekler de sağlar.

#### S: PDF/UA uyumluluğunu doğrulamanın amacı nedir ve bu doğrulamayı nasıl gerçekleştirebilirim?

 C: PDF/UA uyumluluğunun doğrulanması, PDF belgesinin erişilebilirlik standartlarına uygun olmasını sağlayarak onu engelli kullanıcılar için daha erişilebilir hale getirir. Eğitimde PDF/UA uyumluluğunun nasıl doğrulanacağı gösterilmektedir.`Validate()` yöntemini kullanın ve bir XML raporu oluşturun.

#### S: Bu kavramları kendi .NET uygulamalarıma nasıl uygulayabilirim?

C: Sağlanan C# kaynak kodu örneklerini, tablo hücresi biçimlendirmesini kendi .NET uygulamalarınızda uygulamaya yönelik bir kılavuz olarak kullanabilirsiniz. Kodu gereksinimlerinize uyacak şekilde özelleştirin ve projelerinize entegre edin.

#### S: PDF belgelerinde tablo hücrelerini şekillendirmek için önerilen en iyi uygulamalar var mı?

C: Tablo hücrelerini şekillendirirken erişilebilirlik gereksinimleri de dahil olmak üzere hedef kitlenizin ihtiyaçlarını göz önünde bulundurun. Okunabilirliği artırmak için kontrast renkler, uygun yazı tipleri ve net hücre hizalaması kullanın. Ayrıca erişilebilirlik standartlarının karşılandığından emin olmak için PDF/UA uyumluluğunu doğrulayın.

#### S: Aspose.PDF for .NET'in diğer hangi özelliklerini PDF belgesi manipülasyonu için keşfedebilirim?

C: Aspose.PDF for .NET, PDF belge işleme için metin çıkarma, görüntü ekleme, form alanı yönetimi, dijital imzalar ve daha fazlasını içeren çok çeşitli özellikler sunar. Ek işlevler hakkında bilgi edinmek için resmi belgeleri ve kaynakları keşfedin.
