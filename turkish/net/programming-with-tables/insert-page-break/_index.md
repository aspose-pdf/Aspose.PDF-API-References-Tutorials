---
title: Sayfa Sonu Ekle
linktitle: Sayfa Sonu Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl sayfa sonu ekleyeceğinizi öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-tables/insert-page-break/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesine sayfa sonu eklemeyi öğreneceğiz. C#'ta kaynak kodunu adım adım anlatacağız. Bu eğitimin sonunda, bir PDF belgesi tablosunda belirli sayıda satırdan sonra nasıl sayfa sonu ekleneceğini öğreneceksiniz. Hadi başlayalım!

## 1. Adım: Ortamı ayarlama
C# geliştirme ortamınızı Aspose.PDF for .NET ile yapılandırdığınızdan emin olun. Referansı kitaplığa ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: Belge ve Tabloyu Oluşturma
Yeni bir Document örneği oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz. Ardından, tablomuzu PDF belgesinde temsil edecek bir Tablo örneği oluşturuyoruz. Tablo için kenarlık stillerini de tanımlıyoruz.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## 3. Adım: Tabloya satır ekleyin
Diziye 200 satır eklemek için bir döngü kullanıyoruz. Her satır için bir Row örneği oluşturuyoruz ve metin içerikli iki hücre ekliyoruz.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // 10 satır eklendiğinde yeni bir sayfa sonu ekliyoruz
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Adım 4: Tabloyu belgeye ekleme
Tabloyu belge sayfasının paragraf koleksiyonuna ekliyoruz.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## 5. Adım: Belgeyi kaydedin
PDF belgesini sayfa sonu eklenmiş olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Aspose.Words for .NET kullanarak Sayfa Sonu Ekleme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge örneği örneği
Document doc = new Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
doc.Pages.Add();
// Tablo örneği oluştur
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Tablo için kenarlık stilini ayarla
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Kenarlık rengi olan tablo için varsayılan kenarlık stilini Kırmızı olarak ayarla
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Tablo sütun genişliğini belirtin
tab.ColumnWidths = "100 100";
// Tablo için 200 satır eklemek için bir döngü oluşturun
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// 10 satır eklendiğinde, yeni satırı yeni sayfada oluştur
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// PDF dosyasının paragraf koleksiyonuna tablo ekleyin
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// PDF belgesini kaydedin
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine sayfa sonu eklemeyi öğrendik. C# kullanarak bir PDF belgesindeki bir tabloda belirli sayıda satırdan sonra sayfa sonu eklemek için bu adım adım kılavuzu kullanabilirsiniz.