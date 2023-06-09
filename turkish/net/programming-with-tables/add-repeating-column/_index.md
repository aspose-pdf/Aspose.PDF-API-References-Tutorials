---
title: Yinelenen Sütun Ekle
linktitle: Yinelenen Sütun Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine yinelenen sütun eklemeyi öğrenin.
type: docs
weight: 20
url: /tr/net/programming-with-tables/add-repeating-column/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine yinelenen sütun eklemeyi öğreneceğiz. C#'ta kaynak kodunu adım adım anlatacağız. Bu eğitimin sonunda, bir PDF belgesinde yinelenen sütunlu tablo oluşturmayı öğreneceksiniz. Hadi başlayalım!

## 1. Adım: Ortamı ayarlama
Öncelikle Aspose.PDF for .NET ile C# geliştirme ortamınızı kurduğunuzdan emin olun. Referansı kitaplığa ekleyin ve gerekli ad alanlarını içe aktarın.

## 2. Adım: PDF belgesini oluşturma
Bu adımda yeni bir PDF belgesi oluşturuyoruz.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

İçerik ekleyebileceğimiz boş bir PDF belgesi oluşturduk.

## 3. Adım: Tabloları oluşturma
Bu adımda bir ana tablo oluşturuyoruz (`outerTable`) ve iç içe bir tablo (`mytable`) sütununda tekrarlanacak.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Sütun genişliği ve iç içe tablo kesme modu gibi tablo özelliklerini belirledik.

## Adım 4: Tabloları belgeye ekleme
Şimdi oluşturulan tabloları PDF belgesine ekliyoruz.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Önce ana tabloyu ekliyoruz (`outerTable`) PDF belgesine. Ardından, iç içe tabloyu ekliyoruz (`mytable` ) ana tablodaki bir hücrede paragraf olarak. için tekrarlanan sütunların sayısını da belirtiyoruz.`mytable` (bu örnekte 5 sütun).

## 5. Adım: Başlık ve satır ekleme
Şimdi başlıkları ve satırları tabloya ekliyoruz.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Diğer başlıkları buraya ekleyin

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     //Diğer sütunları buraya ekleyin
}
```

İlk önce başlıkları tablonun ilk satırına ekliyoruz (`headerRow`). Sonra bir döngüden veri satırlarını ekliyoruz. Bu örnekte 6 satır veri ekliyoruz.

## 6. Adım: PDF belgesini kaydetme
Son olarak PDF belgesini belirtilen dosyaya kaydediyoruz.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Çıktı PDF dosyasını kaydetmek için doğru dizini ve dosya adını belirttiğinizden emin olun.

### Aspose.PDF for .NET kullanarak yinelenen sütun eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Yeni bir belge oluştur
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Tüm sayfayı kaplayan bir dış tablo oluşturun
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

// Aynı sayfanın içinde kırılacak olan outerTable'ın içine yuvalanacak bir tablo nesnesi oluşturun
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// outerTable'ı sayfa paragraflarına ekleyin
// mytable'ı outerTable'a ekle
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Başlık satırı ekle
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine yinelenen sütun eklemeyi öğrendik. Kendi C# projelerinizde yinelenen sütunlara sahip tablolar oluşturmak için bu adım adım kılavuzu kullanabilirsiniz.