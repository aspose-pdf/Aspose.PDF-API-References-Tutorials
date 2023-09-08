---
title: Tabloyu PDF Belgesinde Oluştur
linktitle: Tabloyu PDF Belgesinde Oluştur
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF belgesinde bir tablonun nasıl görüntüleneceğini öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-tables/render-table/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF belgesinde bir tabloyu görüntülemek için size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve size nasıl uygulayacağınızı göstereceğiz.

## 1. Adım: Belgeyi oluşturma
İlk önce yeni bir PDF belgesi oluşturacağız:

```csharp
// Belgeler dizininin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir belge oluştur
Document doc = new Document();
```

## 2. Adım: Sayfa kenar boşluklarını ve yönünü yapılandırma
Daha sonra sayfa kenar boşluklarını yapılandıracağız ve yönlendirmeyi yatay moda ayarlayacağız:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## 3. Adım: Tabloyu ve sütunları oluşturma
Şimdi bir tablo oluşturalım ve sütun genişliklerini ayarlayalım:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## 4. Adım: Tabloya satır ve hücre ekleyin
Daha sonra bir döngü kullanarak tabloya satırlar ve hücreler ekleyeceğiz:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Adım 5: Tabloyu sayfaya ekleme
Şimdi tabloyu belge sayfasına ekleyelim:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Adım 6: Tablonun yeni bir sayfada görüntülenmesi
Daha sonra yeni bir tablo oluşturacağız ve tabloyu yeni bir sayfada görüntülemek için "IsInNewPage" özelliğini "true" olarak ayarlayacağız:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Adım 7: PDF'yi kaydedin
Son olarak PDF belgesini kaydediyoruz:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Aspose.PDF for .NET kullanan Tablo İşleme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Sayfa eklendi.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Tablo 1'i bir sonraki sayfaya taşımak istiyorum lütfen...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinde bir tablonun nasıl görüntüleneceğini öğrendiniz. Bu adım adım kılavuz size nasıl belge oluşturacağınızı, sayfa kenar boşluklarını ve yönünü nasıl yapılandıracağınızı, tablo ekleyeceğinizi ve tabloyu yeni bir sayfada nasıl görüntüleyeceğinizi gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF belgesindeki tablo oluşturmayla ilgili SSS

#### S: Hücre renklerini değiştirmek veya kenarlıklar eklemek gibi yöntemlerle tablonun görünümünü nasıl değiştirebilirim?

C: Tablonun görünümünü değiştirmek için tablonun çeşitli özelliklerini ayarlayabilirsiniz.`Aspose.Pdf.Table` ve hücreleri. Örneğin,`BackgroundColor` Hücrelerin arka plan rengini değiştirme özelliği. Ayrıca`Border` tablonun özelliği veya tek tek hücrelere kenarlık eklemek için. Ek olarak, tablo içeriğini değiştirerek yazı tipini, metin rengini ve hizalamasını özelleştirebilirsiniz.`TextState` arasında`TextFragment` Hücrelere eklenen nesneler.

#### S: Tabloya üstbilgi veya altbilgi ekleyebilir miyim?

C: Evet, tablonun başında veya sonunda ek satırlar oluşturarak ve hücrelerde uygun içeriği ayarlayarak tabloya üstbilgi veya altbilgi ekleyebilirsiniz. Bu belirli satırlara farklı stiller veya içerik ekleyerek üstbilgileri veya altbilgileri tablo içeriğinin geri kalanından bağımsız olarak özelleştirebilirsiniz.

#### S: Tablonun sayfadaki konumunu nasıl kontrol edebilirim?

 C: Tablonun sayfadaki konumunu kontrol etmek için`MarginInfo` arasında`PageInfo` nesne.`MarginInfo`tablo için kullanılabilir alanı etkileyen sayfanın sol, sağ, üst ve alt kenar boşluklarını ayarlamanıza olanak tanır. Ayrıca şunları da kullanabilirsiniz:`PositioningType` mülkiyeti`Aspose.Pdf.Table` sayfanın içerik alanı içindeki yatay ve dikey hizalamasını kontrol etmek için.

#### S: Tabloyu Excel veya CSV gibi farklı dosya formatlarına aktarabilir miyim?

C: Aspose.PDF for .NET öncelikle PDF belgeleriyle çalışmak üzere tasarlanmıştır. PDF belgesini görüntü veya XPS olarak dışa aktarabilse de tabloların Excel veya CSV gibi formatlara aktarılmasını doğrudan desteklemez. Tablo verilerini farklı dosya formatlarına aktarmak için PDF içeriğini istediğiniz formata dönüştürmek üzere ek kitaplıklar veya yöntemler kullanmanız gerekebilir.

#### S: Tablo hücrelerine nasıl köprü ekleyebilirim?

 C: Tablo hücrelerine köprüler eklemek için`Aspose.Pdf.WebHyperlink` sınıfa bir köprü oluşturmak ve ardından onu bağlantı noktası olarak eklemek için`TextFragment`hücrenin içinde. Bu, tıklanabilir köprüler oluşturarak bir URL'yi veya bağlantı hedefini hücre içindeki belirli metin veya içerikle ilişkilendirmenize olanak tanır.