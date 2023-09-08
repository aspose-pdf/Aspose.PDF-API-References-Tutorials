---
title: PDF Belgesine Yinelenen Sütun Ekleme
linktitle: PDF Belgesine Yinelenen Sütun Ekleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF belgesine nasıl yinelenen sütun ekleyeceğinizi öğrenin.
type: docs
weight: 20
url: /tr/net/programming-with-tables/add-repeating-column/
---
Bu eğitimde Aspose.PDF for .NET kullanarak PDF belgesine tekrar eden bir sütunun nasıl ekleneceğini öğreneceğiz. C#'ta kaynak kodunu adım adım anlatacağız. Bu eğitimin sonunda, bir PDF belgesinde yinelenen sütunlu bir tablonun nasıl oluşturulacağını öğreneceksiniz. Hadi başlayalım!

## 1. Adım: Ortamı ayarlama
Öncelikle Aspose.PDF for .NET ile C# geliştirme ortamınızı kurduğunuzdan emin olun. Referansı kitaplığa ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: PDF belgesini oluşturma
Bu adımda yeni bir PDF belgesi oluşturuyoruz.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

İçerik ekleyebileceğimiz boş bir PDF belgesi oluşturduk.

## 3. Adım: Tabloları oluşturma
Bu adımda bir ana tablo oluşturuyoruz (`outerTable`) ve iç içe geçmiş bir tablo (`mytable`) sütunda tekrarlanacaktır.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Sütun genişliği ve iç içe tablo sonu modu gibi tablo özelliklerini belirledik.

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

İlk önce ana tabloyu ekliyoruz (`outerTable`) PDF belgesine. Daha sonra iç içe geçmiş tabloyu ekliyoruz (`mytable` ) ana tablodaki bir hücrede paragraf olarak. Ayrıca tekrarlanan sütunların sayısını da belirtiyoruz.`mytable` (bu örnekte 5 sütun).

## 5. Adım: Başlıkları ve satırları ekleme
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
     // Diğer sütunları buraya ekleyin
}
```

İlk önce başlıkları tablonun ilk satırına ekliyoruz (`headerRow`). Daha sonra bir döngüden veri satırlarını ekliyoruz. Bu örnekte 6 satır veri ekliyoruz.

## Adım 6: PDF belgesini kaydetme
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

// Sayfanın tamamını kaplayan bir dış tabloyu örnekleyin
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Aynı sayfanın içinde bölünecek,outerTable'ın içine yerleştirilecek bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// OuterTable'ı sayfa paragraflarına ekleyin
// Mytable'ı OuterTable'a ekle
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Başlık Satırı ekle
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
Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesine yinelenen sütunun nasıl ekleneceğini öğrendik. Kendi C# projelerinizde yinelenen sütunlara sahip tablolar oluşturmak için bu adım adım kılavuzu kullanabilirsiniz.

### PDF belgesine yinelenen sütun eklemeyle ilgili SSS'ler

#### S: İç içe geçmiş tabloda yinelenen sütunların sayısını özelleştirebilir miyim?

 C: Evet, iç içe geçmiş tabloda yinelenen sütunların sayısını özelleştirebilirsiniz. Verilen örnekte,`mytable.RepeatingColumnsCount = 5;`Bu, tekrarlanan 5 sütun olacağı anlamına gelir. Bu değeri istediğiniz herhangi bir sayıyla değiştirebilirsiniz.

#### S: İç içe geçmiş tabloya dinamik olarak daha fazla satır eklemek mümkün müdür?

C: Evet, öğreticide gösterildiği gibi iç içe geçmiş tabloya dinamik olarak daha fazla satır ekleyebilirsiniz. Verilerinize dayalı olarak satır eklemek için döngüleri veya başka herhangi bir mantığı kullanabilirsiniz.

#### S: Tabloya ve hücrelerine stil ve biçimlendirme uygulayabilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak tabloya ve hücrelere stil ve formatlama uygulayabilirsiniz. Kitaplık, tablonun ve içeriğinin görünümünü özelleştirmek için çeşitli özellikler ve yöntemler sağlar.

#### S: Aspose.PDF for .NET, .NET Core ile uyumlu mu?

C: Evet, Aspose.PDF for .NET, .NET Core ile uyumludur. Hem .NET Framework hem de .NET Core uygulamalarında kullanabilirsiniz.

#### S: Bu yaklaşımı mevcut bir PDF belgesine yinelenen sütunlar eklemek için kullanabilir miyim?

C: Evet, mevcut bir PDF belgesine yinelenen sütunlar eklemek için bu yaklaşımı kullanabilirsiniz. Mevcut belgeyi Aspose.PDF for .NET kullanarak yükleyin ve yinelenen sütunu oluşturmak ve eklemek için aynı adımları izleyin.