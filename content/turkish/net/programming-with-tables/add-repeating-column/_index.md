---
title: PDF Belgesine Tekrarlayan Sütun Ekle
linktitle: PDF Belgesine Tekrarlayan Sütun Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgesine tekrarlayan sütun eklemeyi öğrenin.
type: docs
weight: 20
url: /tr/net/programming-with-tables/add-repeating-column/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF belgesine tekrarlayan bir sütun eklemeyi öğreneceğiz. Kaynak kodu adım adım C# dilinde açıklayacağız. Bu eğitimin sonunda, PDF belgesinde tekrarlayan bir sütuna sahip bir tablonun nasıl oluşturulacağını öğreneceksiniz. Başlayalım!

## Adım 1: Ortamı kurma
Öncelikle, C# geliştirme ortamınızı .NET için Aspose.PDF ile kurduğunuzdan emin olun. Referansı kütüphaneye ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: PDF belgesinin oluşturulması
Bu adımda yeni bir PDF belgesi oluşturuyoruz.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

İçerik ekleyebileceğimiz boş bir PDF belgesi oluşturduk.

## Adım 3: Tabloları oluşturma
Bu adımda ana tabloyu oluşturuyoruz (`outerTable`) ve iç içe geçmiş bir tablo (`mytable`) sütunda tekrarlanacaktır.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Sütun genişliği ve iç içe tablo kesme modu gibi tablo özelliklerini belirttik.

## Adım 4: Tabloları belgeye ekleme
Şimdi oluşturduğumuz tabloları PDF dokümanına ekleyelim.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

İlk önce ana tabloyu ekleyelim (`outerTable`) PDF belgesine. Sonra, iç içe geçmiş tabloyu (`mytable` ) ana tabloda bir hücrede bir paragraf olarak. Ayrıca, tekrarlanan sütunların sayısını da belirtiyoruz`mytable` (bu örnekte 5 sütun).

## Adım 5: Başlık ve satır ekleme
Şimdi tabloya başlıkları ve satırları ekleyelim.

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
     // Diğer sütunları buraya ekleyin
}
```

Öncelikle tablonun ilk satırına başlıkları ekleyelim (`headerRow`). Daha sonra bir döngüden veri satırlarını ekliyoruz. Bu örnekte 6 satır veri ekliyoruz.

## Adım 6: PDF belgesini kaydetme
Son olarak PDF dokümanını belirtilen dosyaya kaydediyoruz.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Çıktı PDF dosyasını kaydetmek için doğru dizini ve dosya adını belirttiğinizden emin olun.

### .NET için Aspose.PDF kullanarak tekrarlayan sütun eklemek için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Yeni bir belge oluştur
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Tüm sayfayı kaplayan bir dış tablo örneği oluşturun
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Aynı sayfanın içinde bölünecek olan outerTable'ın içine yerleştirilecek bir tablo nesnesi örneği oluşturun
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

// Başlık Satırı Ekle
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
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesine tekrarlayan bir sütun eklemeyi öğrendik. Kendi C# projelerinizde tekrarlayan sütunlara sahip tablolar oluşturmak için bu adım adım kılavuzu kullanabilirsiniz.

### PDF belgesine tekrar eden sütun eklemeyle ilgili SSS

#### S: İç içe geçmiş tabloda tekrarlanan sütunların sayısını özelleştirebilir miyim?

 A: Evet, iç içe geçmiş tabloda tekrarlanan sütunların sayısını özelleştirebilirsiniz. Sağlanan örnekte,`mytable.RepeatingColumnsCount = 5;`, yani 5 tekrarlanan sütun olacak. Bu değeri istediğiniz herhangi bir sayıyla değiştirebilirsiniz.

#### S: İç içe geçmiş tabloya dinamik olarak daha fazla satır eklemek mümkün müdür?

A: Evet, eğitimde gösterildiği gibi iç içe geçmiş tabloya dinamik olarak daha fazla satır ekleyebilirsiniz. Verilerinize göre satır eklemek için döngüler veya başka bir mantık kullanabilirsiniz.

#### S: Tabloya ve hücrelerine stil ve biçimlendirme uygulayabilir miyim?

A: Evet, .NET için Aspose.PDF kullanarak tabloya ve hücrelerine stiller ve biçimlendirme uygulayabilirsiniz. Kütüphane, tablonun ve içeriklerinin görünümünü özelleştirmek için çeşitli özellikler ve yöntemler sağlar.

#### S: Aspose.PDF for .NET, .NET Core ile uyumlu mudur?

A: Evet, Aspose.PDF for .NET, .NET Core ile uyumludur. Hem .NET Framework hem de .NET Core uygulamalarında kullanabilirsiniz.

#### S: Bu yaklaşımı mevcut bir PDF belgesine tekrarlayan sütunlar eklemek için kullanabilir miyim?

A: Evet, bu yaklaşımı mevcut bir PDF belgesine tekrarlayan sütunlar eklemek için kullanabilirsiniz. Mevcut belgeyi .NET için Aspose.PDF kullanarak yükleyin ve tekrarlayan sütunu oluşturmak ve eklemek için aynı adımları izleyin.