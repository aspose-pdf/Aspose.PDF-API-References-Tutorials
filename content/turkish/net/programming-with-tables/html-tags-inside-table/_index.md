---
title: PDF Dosyasındaki Tablo İçindeki HTML Etiketleri
linktitle: PDF Dosyasındaki Tablo İçindeki HTML Etiketleri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki bir tablonun içinde HTML etiketlerinin nasıl kullanılacağını öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-tables/html-tags-inside-table/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki tablonun içinde HTML etiketlerinin nasıl kullanılacağını öğreneceğiz. Kaynak kodunu adım adım C# dilinde açıklayacağız. Bu eğitimin sonunda, bir PDF belgesindeki tabloya HTML içeriğinin nasıl ekleneceğini öğreneceksiniz. Başlayalım!

## Adım 1: Ortamı kurma
C# geliştirme ortamınızı .NET için Aspose.PDF ile yapılandırdığınızdan emin olun. Referansı kütüphaneye ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: Tablo verileri oluşturma
String türünde bir "data" sütunu içeren bir DataTable oluşturuyoruz. Daha sonra bu DataTable'a HTML içeriği kullanarak satırlar ekliyoruz.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Adım 3: Belge ve Tablo Oluşturma
Yeni bir PDF belgesi oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz. Sonra, Table sınıfının bir örneğini başlatıyoruz ve tablo özelliklerini ayarlıyoruz.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Adım 4: Verileri tabloya aktarma
"ImportDataTable" metodunu kullanarak DataTable'dan verileri tabloya aktarıyoruz. DataTable'ın hangi satır ve sütun aralığının içe aktarılacağını belirtmek için metot parametrelerini belirtiyoruz.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Adım 5: Tabloyu belgeye ekleme
Tabloyu belge sayfasına ekliyoruz.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Aşama 6: Belgenin kaydedilmesi
HTML içeriğinin bulunduğu tabloyu PDF belgesi olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### .NET için Aspose.PDF kullanarak Tablo İçindeki HTML Etiketleri için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Tablonun yeni bir örneğini başlatır
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Tablonun sütun genişliklerini ayarlayın
tableProvider.ColumnWidths = "400 50 ";
// Tablo kenarlık rengini AçıkGri olarak ayarlayın
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Tablo hücreleri için kenarlığı ayarlayın
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Çözüm
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki tablonun içinde HTML etiketlerinin nasıl kullanılacağını öğrendik. Bu adım adım kılavuzu kullanarak C# kullanarak bir PDF belgesindeki tablo hücrelerine HTML içeriği ekleyebilirsiniz.

### PDF dosyasındaki tablonun içindeki HTML etiketleri için SSS

#### S: Tablo hücrelerinin içinde başka HTML etiketleri ve nitelikleri kullanabilir miyim?

 A: Evet, tablo hücrelerinin içinde çeşitli HTML etiketleri ve öznitelikleri kullanabilirsiniz, örneğin:`<b>`, `<i>`, `<a>`ve daha fazlası. Aspose.PDF for .NET, tablo hücrelerindeki içeriği biçimlendirmek için kullanabileceğiniz çok çeşitli HTML öğelerini ve stillerini destekler.

#### S: Tablo hücrelerinin içindeki HTML içeriğine CSS stilleri uygulayabilir miyim?

C: Evet, tablo hücrelerinin içindeki HTML içeriğine CSS stilleri uygulayabilirsiniz. Aspose.PDF for .NET, HTML öğelerine uygulanabilen temel CSS stilleri için destek sağlar.

#### S: Tablo hücrelerinin içine HTML içeriğiyle birlikte resim eklemek mümkün müdür?

 A: Evet, tablo hücrelerinin içine HTML içeriğiyle birlikte resimler ekleyebilirsiniz. HTML kullanabilirsiniz`<img>` Yerel dosyalar veya URL'ler gibi çeşitli kaynaklardan gelen görselleri eklemek için etiketler.

#### S: Tablo için farklı sütun genişliklerini nasıl belirleyebilirim?

 A: Tablo için farklı sütun genişliklerini, şunu kullanarak belirleyebilirsiniz:`ColumnWidths` tablonun özelliği. Özellik, her değerin bir sütunun genişliğini noktalar halinde temsil ettiği boşluklarla ayrılmış değerler içeren bir dize alır.

#### S: HTML içeriği olan bir hücrenin içinde iç içe geçmiş tablolar kullanabilir miyim?

A: Evet, HTML içerikli bir hücrenin içinde iç içe geçmiş tablolar kullanabilirsiniz. Ayrı tablo örnekleri oluşturabilir ve iç içe geçme etkisini elde etmek için bunları bir hücrenin içindeki HTML içeriğinin parçası olarak ekleyebilirsiniz.