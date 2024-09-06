---
title: PDF Dosyasına Sayfa Sonu Ekle
linktitle: PDF Dosyasına Sayfa Sonu Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasına sayfa sonu eklemeyi öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-tables/insert-page-break/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasına sayfa sonu eklemeyi öğreneceğiz. Kaynak kodunu adım adım C# dilinde açıklayacağız. Bu eğitimin sonunda, bir PDF belgesinin tablosunda belirli sayıda satırdan sonra sayfa sonu eklemeyi öğreneceksiniz. Hadi başlayalım!

## Adım 1: Ortamı kurma
C# geliştirme ortamınızı .NET için Aspose.PDF ile yapılandırdığınızdan emin olun. Referansı kütüphaneye ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: Belge ve Tablo Oluşturma
Yeni bir Belge örneği oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz. Sonra, PDF belgesinde tablomuzu temsil edecek bir Tablo örneği oluşturuyoruz. Ayrıca tablo için kenarlık stillerini tanımlıyoruz.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Adım 3: Tabloya satır ekleyin
Diziye 200 satır eklemek için bir döngü kullanırız. Her satır için bir Row örneği oluştururuz ve metin içerikli iki hücre ekleriz.

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

## Adım 5: Belgeyi kaydedin
PDF belgesini sayfa sonu eklenmiş şekilde kaydediyoruz.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### .NET için Aspose.PDF kullanarak Sayfa Sonu Ekleme için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge örneğini örneklendir
Document doc = new Document();
// PDF dosyasının sayfa sayfa koleksiyonunu ekle
doc.Pages.Add();
// Tablo örneği oluştur
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Tablo için kenarlık stilini ayarlayın
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Tablo için varsayılan kenarlık stilini, kenarlık rengini Kırmızı olarak ayarlayın
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Tablo sütun genişliğini belirtin
tab.ColumnWidths = "100 100";
// Tabloya 200 satır eklemek için bir döngü oluşturun
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// 10 satır eklendiğinde, yeni satırı yeni sayfada göster
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// PDF dosyasının paragraf koleksiyonuna tablo ekle
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// PDF belgesini kaydedin
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Çözüm
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesine sayfa sonu eklemeyi öğrendik. C# kullanarak bir PDF belgesindeki bir tabloda belirli sayıda satırdan sonra sayfa sonu eklemek için bu adım adım kılavuzu kullanabilirsiniz.

### PDF dosyasına sayfa sonu eklemeyle ilgili SSS

#### S: Sayfa sonundan sonra oluşturulan yeni sayfaların sayfa boyutunu nasıl değiştirebilirim?

 A: Sayfa sonundan sonra oluşturulan yeni sayfalar için sayfa boyutunu değiştirmek için,`PageSize` mülkiyeti`Page` nesne. Örneğin, sayfa boyutunu A4 olarak ayarlamak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// Sayfa boyutunu A4 olarak ayarlayın
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### S: Sayfa sonundan sonraki yeni sayfalar için sayfa kenar boşluklarını kontrol edebilir miyim?

 A: Evet, sayfa sonundan sonra yeni sayfalar için sayfa kenar boşluklarını kontrol edebilirsiniz.`Margin` mülkiyeti`Page` sayfa kenar boşluklarını ayarlamak için nesne. Örneğin, tüm kenar boşluklarını 10 puana ayarlamak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// Tüm kenar boşluklarını 10 puana ayarlayın
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### S: Sayfa sonundan sonra yeni sayfalara üstbilgi ve altbilgi eklemek mümkün müdür?

 A: Evet, sayfa sonundan sonra yeni sayfalara üstbilgiler ve altbilgiler ekleyebilirsiniz.`Page.Header` Ve`Page.Footer` sayfanın üstbilgi ve altbilgi bölümlerine içerik eklemek için özellikler. Örneğin:

```csharp
// Yeni sayfalara başlık ekle
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Yeni sayfalara altbilgi ekleyin
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### S: Belirli sayıda satırdan sonra gelenler dışında belirli yerlere sayfa sonu ekleyebilir miyim?

 A: Evet, belirli sayıda satırdan sonra değil, belirli konumlara sayfa sonları ekleyebilirsiniz.`IsInNewPage` bir satırın özelliği`true` tablonun o satırdan sonra yeni bir sayfaya başlamasını zorlamak için.

#### S: İçerik yüksekliğine göre sayfa sonu davranışını nasıl ayarlayabilirim?

 A: Kullanabilirsiniz`IsBroken` sayfalar arasında otomatik satır sonlandırma özelliğini etkinleştirmek veya devre dışı bırakmak için tablonun özelliği. Ayarlandığında`true`, içerik yüksekliğine göre satırların sayfalar arasında bölünmesine olanak tanır.