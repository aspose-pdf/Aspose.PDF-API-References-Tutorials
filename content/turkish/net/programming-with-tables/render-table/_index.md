---
title: Tabloyu PDF Belgesinde Oluştur
linktitle: Tabloyu PDF Belgesinde Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgesinde bir tablonun nasıl görüntüleneceğini öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-tables/render-table/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF belgesinde bir tabloyu adım adım görüntülemenize yardımcı olacağız. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## Adım 1: Belgenin oluşturulması
Öncelikle yeni bir PDF belgesi oluşturacağız:

```csharp
// Belgeler dizinine giden yol
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir belge oluştur
Document doc = new Document();
```

## Adım 2: Sayfa kenar boşluklarını ve yönlendirmeyi yapılandırma
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

## Adım 3: Tablo ve sütunları oluşturma
Şimdi bir tablo oluşturalım ve sütun genişliklerini ayarlayalım:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Adım 4: Tabloya satırlar ve hücreler ekleyin
Daha sonra, bir döngü kullanarak tabloya satırlar ve hücreler ekleyeceğiz:

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

## Adım 6: Tabloyu yeni bir sayfada görüntüleme
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
Son olarak PDF dokümanını kaydediyoruz:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### .NET için Aspose.PDF kullanılarak Render Tablosu için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
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
// 1. tabloyu bir sonraki sayfada tutmak istiyorum lütfen...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinde tablonun nasıl görüntüleneceğini öğrendiniz. Bu adım adım kılavuz size bir belgenin nasıl oluşturulacağını, sayfa kenar boşluklarının ve yönlendirmesinin nasıl yapılandırılacağını, bir tablonun nasıl ekleneceğini ve yeni bir sayfada bir tablonun nasıl görüntüleneceğini gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF belgesinde render tablosu için SSS

#### S: Tablonun görünümünü nasıl değiştirebilirim? Örneğin hücre renklerini değiştirebilir veya kenarlık ekleyebilirim?

A: Tablonun görünümünü değiştirmek için çeşitli özellikleri ayarlayabilirsiniz.`Aspose.Pdf.Table` ve hücreleri. Örneğin, şunu ayarlayabilirsiniz:`BackgroundColor` Hücrelerin arka plan rengini değiştirme özelliği. Ayrıca,`Border` tablonun veya tek tek hücrelerin kenarlık eklemek için özelliğini özelleştirebilirsiniz. Ayrıca, tablo içeriğinin yazı tipini, metin rengini ve hizalamasını,`TextState` of'un`TextFragment` hücrelere eklenen nesneler.

#### S: Tabloya üstbilgi veya altbilgi ekleyebilir miyim?

A: Evet, tablonun başında veya sonunda ek satırlar oluşturarak ve hücrelerde uygun içeriği ayarlayarak tabloya başlıklar veya altbilgiler ekleyebilirsiniz. Bu belirli satırlara farklı stiller veya içerik ekleyerek başlıkları veya altbilgileri tablonun geri kalanından bağımsız olarak özelleştirebilirsiniz.

#### S: Tablonun sayfadaki konumunu nasıl kontrol edebilirim?

 A: Tablonun sayfadaki konumunu kontrol etmek için,`MarginInfo` of'un`PageInfo` nesne.`MarginInfo`sayfanın sol, sağ, üst ve alt kenar boşluklarını ayarlamanıza olanak tanır; bu da tablo için kullanılabilir alanı etkiler. Ayrıca şunu da kullanabilirsiniz:`PositioningType` mülkiyeti`Aspose.Pdf.Table` Sayfanın içerik alanı içerisinde yatay ve dikey hizalamasını kontrol etmek için.

#### S: Tabloyu Excel veya CSV gibi farklı dosya biçimlerine aktarabilir miyim?

A: Aspose.PDF for .NET, öncelikle PDF belgeleriyle çalışmak için tasarlanmıştır. PDF belgesini bir görüntü veya XPS olarak dışa aktarabilirken, tabloları Excel veya CSV gibi biçimlere doğrudan aktarmayı desteklemez. Tablo verilerini farklı dosya biçimlerine dışa aktarmak için, PDF içeriğini istenen biçime dönüştürmek için ek kitaplıklar veya yöntemler kullanmanız gerekebilir.

#### S: Tablo hücrelerine nasıl köprü ekleyebilirim?

 A: Tablo hücrelerine köprü eklemek için şunu kullanabilirsiniz:`Aspose.Pdf.WebHyperlink` bir köprü metni oluşturmak ve ardından bunu bir bağlantı noktası olarak eklemek için sınıf`TextFragment`hücrenin içinde. Bu, bir URL veya bağlantı hedefini hücre içindeki belirli bir metin veya içerikle ilişkilendirmenize ve tıklanabilir köprüler oluşturmanıza olanak tanır.