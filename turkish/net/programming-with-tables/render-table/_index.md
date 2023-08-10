---
title: Tabloyu PDF Belgesinde İşle
linktitle: Tabloyu PDF Belgesinde İşle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir tabloyu PDF belgesinde nasıl görüntüleyeceğinizi öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-tables/render-table/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF belgesinde bir tablo görüntülemek için adım adım size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## 1. Adım: Belgeyi oluşturma
İlk olarak, yeni bir PDF belgesi oluşturacağız:

```csharp
// Belgeler dizinine giden yol
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir belge oluştur
Document doc = new Document();
```

## 2. Adım: Sayfa kenar boşluklarını ve yönünü yapılandırma
Ardından, sayfa kenar boşluklarını yapılandıracağız ve yönlendirmeyi yatay moda ayarlayacağız:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## 3. Adım: Tablo ve sütunları oluşturma
Şimdi bir tablo oluşturalım ve sütun genişliklerini ayarlayalım:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## 4. Adım: Tabloya satır ve hücre ekleyin
Ardından, bir döngü kullanarak tabloya satırlar ve hücreler ekleyeceğiz:

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
Ardından, yeni bir tablo oluşturacağız ve tabloyu yeni bir sayfada görüntülemek için "IsInNewPage" özelliğini "true" olarak ayarlayacağız:

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

## 7. Adım: PDF'yi kaydedin
Son olarak, PDF belgesini kaydediyoruz:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Aspose.PDF for .NET kullanan Render Table için örnek kaynak kodu

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
// Tablo 1'i bir sonraki sayfada tutmak istiyorum lütfen...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinde bir tabloyu nasıl görüntüleyeceğinizi öğrendiniz. Bu adım adım kılavuz size belge oluşturmayı, sayfa kenar boşluklarını ve yönlendirmeyi yapılandırmayı, tablo eklemeyi ve yeni bir sayfada tabloyu nasıl görüntüleyeceğinizi gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF belgesinde tablo oluşturma hakkında SSS

#### S: Hücre renklerini değiştirme veya kenarlık ekleme gibi tablonun görünümünü nasıl değiştirebilirim?

C: Tablonun görünümünü değiştirmek için tablonun çeşitli özelliklerini ayarlayabilirsiniz.`Aspose.Pdf.Table` ve hücreleri. Örneğin,`BackgroundColor` hücrelerin arka plan rengini değiştirme özelliği. Ayrıca ayarlayabilirsiniz`Border` tablonun özelliği veya tek tek hücrelere kenarlık ekleyin. Ek olarak, tablo içeriğini değiştirerek yazı tipini, metin rengini ve hizalamayı özelleştirebilirsiniz.`TextState` arasında`TextFragment` hücrelere eklenen nesneler.

#### S: Tabloya üst bilgi veya alt bilgi ekleyebilir miyim?

C: Evet, tablonun başında veya sonunda ek satırlar oluşturarak ve hücrelerde uygun içeriği ayarlayarak tabloya üst bilgiler veya alt bilgiler ekleyebilirsiniz. Bu belirli satırlara farklı stiller veya içerikler ekleyerek üst bilgileri veya alt bilgileri tablo içeriğinin geri kalanından bağımsız olarak özelleştirebilirsiniz.

#### S: Tablonun sayfadaki konumunu nasıl kontrol edebilirim?

 C: Tablonun sayfadaki konumunu kontrol etmek için`MarginInfo` arasında`PageInfo` nesne. bu`MarginInfo`tablo için kullanılabilir alanı etkileyen sayfanın sol, sağ, üst ve alt kenar boşluklarını ayarlamanıza olanak tanır. Şunu da kullanabilirsiniz:`PositioningType` mülkiyeti`Aspose.Pdf.Table` sayfanın içerik alanı içinde yatay ve dikey hizalamasını kontrol etmek için.

#### S: Tabloyu Excel veya CSV gibi farklı dosya biçimlerine aktarabilir miyim?

Y: Aspose.PDF for .NET, öncelikle PDF belgeleriyle çalışmak için tasarlanmıştır. PDF belgesini bir görüntü veya XPS olarak dışa aktarabilse de, tabloların Excel veya CSV gibi formatlara dışa aktarılmasını doğrudan desteklemez. Tablo verilerini farklı dosya biçimlerine dışa aktarmak için, PDF içeriğini istenen biçime dönüştürmek için ek kitaplıklar veya yöntemler kullanmanız gerekebilir.

#### S: Tablo hücrelerine köprüleri nasıl ekleyebilirim?

 C: Tablo hücrelerine köprüler eklemek için`Aspose.Pdf.WebHyperlink` bir köprü oluşturmak ve ardından onu bir bağlantı olarak eklemek için sınıf`TextFragment`hücre içinde. Bu, bir URL'yi veya bağlantı hedefini hücre içindeki belirli metin veya içerikle ilişkilendirerek tıklanabilir köprüler oluşturmanıza olanak tanır.