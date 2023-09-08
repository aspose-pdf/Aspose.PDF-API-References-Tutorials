---
title: PDF Dosyasındaki Tablonun İçindeki HTML Etiketleri
linktitle: PDF Dosyasındaki Tablonun İçindeki HTML Etiketleri
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasındaki bir tablonun içindeki HTML etiketlerini nasıl kullanacağınızı öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-tables/html-tags-inside-table/
---
Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesindeki tablonun içindeki HTML etiketlerinin nasıl kullanılacağını öğreneceğiz. C#'ta kaynak kodunu adım adım anlatacağız. Bu eğitimin sonunda, HTML içeriğini bir PDF belgesindeki tabloya nasıl ekleyeceğinizi öğreneceksiniz. Hadi başlayalım!

## 1. Adım: Ortamı ayarlama
Aspose.PDF for .NET ile C# geliştirme ortamınızı yapılandırdığınızdan emin olun. Referansı kitaplığa ekleyin ve gerekli ad alanlarını içe aktarın.

## 2. Adım: Tablo verilerini oluşturma
String türünde bir "data" sütunu içeren bir DataTable oluşturuyoruz. Daha sonra HTML içeriğini kullanarak bu DataTable'a satırlar ekliyoruz.

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

## Adım 3: Belgeyi ve Tabloyu Oluşturma
Yeni bir PDF belgesi oluşturup bu belgeye bir sayfa ekliyoruz. Daha sonra Table sınıfının bir örneğini başlatıyoruz ve tablo özelliklerini ayarlıyoruz.

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

## 4. Adım: Verileri tabloya aktarma
DataTable'daki verileri "ImportDataTable" yöntemini kullanarak tabloya aktarıyoruz. DataTable'ın hangi satır ve sütun aralığının içe aktarılması gerektiğini belirtmek için yöntem parametrelerini belirtiriz.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Adım 5: Tabloyu belgeye ekleme
Tabloyu belge sayfasına ekliyoruz.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Aşama 6: Belgeyi kaydetme
PDF belgesini HTML içeriğini içeren tabloyla birlikte kaydediyoruz.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Aspose.PDF for .NET kullanan HTML Etiketleri İçinde Tablo için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
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
// Tablo kenarlığı rengini AçıkGri olarak ayarlayın
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Tablo hücreleri için kenarlığı ayarlama
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
Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesindeki tablonun içindeki HTML etiketlerinin nasıl kullanılacağını öğrendik. C# kullanarak bir PDF belgesindeki tablo hücrelerine HTML içeriği eklemek için bu adım adım kılavuzu kullanabilirsiniz.

### PDF dosyasındaki tablonun içindeki HTML etiketleri hakkında SSS

#### S: Tablo hücrelerinin içinde diğer HTML etiketlerini ve niteliklerini kullanabilir miyim?

 C: Evet, tablo hücrelerinin içinde aşağıdakiler gibi çeşitli HTML etiketleri ve nitelikleri kullanabilirsiniz:`<b>`, `<i>`, `<a>`ve daha fazlası. Aspose.PDF for .NET, tablo hücrelerinin içindeki içeriği formatlamak için kullanabileceğiniz çok çeşitli HTML öğelerini ve stillerini destekler.

#### S: CSS stillerini tablo hücrelerinin içindeki HTML içeriğine uygulayabilir miyim?

C: Evet, CSS stillerini tablo hücrelerinin içindeki HTML içeriğine uygulayabilirsiniz. Aspose.PDF for .NET, HTML öğelerine uygulanabilecek temel CSS stilleri için destek sağlar.

#### S: Tablo hücrelerinin içine HTML içeriğinin yanı sıra resimler de eklemek mümkün müdür?

 C: Evet, tablo hücrelerinin içine HTML içeriğinin yanı sıra resimler de ekleyebilirsiniz. HTML'yi kullanabilirsiniz`<img>` Yerel dosyalar veya URL'ler gibi çeşitli kaynaklardan gelen görselleri içerecek etiketler.

#### S: Tablo için farklı sütun genişliklerini nasıl belirleyebilirim?

 C: Tablo için farklı sütun genişliklerini aşağıdaki komutu kullanarak belirleyebilirsiniz:`ColumnWidths` tablonun özelliği. Özellik, boşlukla ayrılmış değerler içeren bir dize alır; burada her değer, bir sütunun genişliğini nokta cinsinden temsil eder.

#### S: İç içe geçmiş tabloları HTML içeriğine sahip bir hücrenin içinde kullanabilir miyim?

C: Evet, HTML içeriğine sahip bir hücrenin içindeki iç içe tabloları kullanabilirsiniz. İç içe geçme efekti elde etmek için ayrı tablo örnekleri oluşturabilir ve bunları bir hücrenin içindeki HTML içeriğinin parçası olarak ekleyebilirsiniz.