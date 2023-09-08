---
title: PDF Dosyasındaki Veritabanıyla Entegrasyon
linktitle: PDF Dosyasındaki Veritabanıyla Entegrasyon
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak bir veritabanındaki verileri PDF dosyasına gömün.
type: docs
weight: 120
url: /tr/net/programming-with-tables/integrate-with-database/
---
Bu eğitimde Aspose.PDF for .NET kullanarak bir veritabanındaki verileri PDF dosyasına nasıl yerleştireceğimizi öğreneceğiz. C#'ta kaynak kodunu adım adım anlatacağız. Bu eğitimin sonunda tablo verilerini bir veritabanından PDF belgesine nasıl aktaracağınızı öğreneceksiniz. Hadi başlayalım!

## 1. Adım: Ortamı ayarlama
Aspose.PDF for .NET ile C# geliştirme ortamınızı yapılandırdığınızdan emin olun. Referansı kitaplığa ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: DataTable'ı Oluşturma
PDF belgesine gömmek istediğimiz verileri temsil etmek için bir DataTable örneği oluşturuyoruz. Bu örnekte üç sütunlu bir DataTable oluşturuyoruz: Çalışan_Kimliği, Çalışan_Adı ve Cinsiyet. Ayrıca DataTable'a sahte veriler içeren iki satır ekliyoruz.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Adım 3: PDF Belgesi ve Tablosunu Oluşturma
Document örneğini oluşturup bu belgeye bir sayfa ekliyoruz. Daha sonra, tablomuzu PDF belgesinde temsil edecek bir Tablo örneği oluşturuyoruz. Tablo sütun genişliklerini ve kenarlık stillerini tanımlıyoruz.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Adım 4: Verileri DataTable'dan tabloya aktarma
DataTable'daki verileri PDF belgesindeki tabloya aktarmak için ImportDataTable yöntemini kullanıyoruz.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Adım 5: Tabloyu belgeye ekleme
Tabloyu belge sayfasının paragraf koleksiyonuna ekliyoruz.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Adım 6: Belgeyi kaydedin
PDF belgesini gömülü veritabanındaki verilerle birlikte kaydediyoruz.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Tebrikler! Artık Aspose.PDF for .NET kullanarak veritabanı verilerini bir PDF belgesine nasıl yerleştireceğinizi biliyorsunuz.

### Aspose.PDF for .NET kullanarak Integrate With Database için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// DataTable nesnesine programlı olarak 2 satır ekleyin
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Belge örneği oluştur
Document doc = new Document();
doc.Pages.Add();
// Tablonun yeni bir örneğini başlatır
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tablonun sütun genişliklerini ayarlayın
table.ColumnWidths = "40 100 100 100";
// Tablo kenarlığı rengini AçıkGri olarak ayarlayın
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Tablo hücreleri için kenarlığı ayarlama
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Giriş belgesinin ilk sayfasına tablo nesnesi ekleyin
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Tablo nesnesini içeren güncellenmiş belgeyi kaydet
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Çözüm
Bu eğitimde Aspose.PDF for .NET kullanarak bir veritabanındaki verileri bir PDF belgesine nasıl yerleştireceğimizi öğrendik. Verileri kendi veritabanınızdan içe aktarmak ve bunları PDF belgelerinde görüntülemek için bu adım adım kılavuzu kullanabilirsiniz. Bu güçlü kitaplığın sunduğu diğer özellikleri ve olanakları keşfetmek için Aspose.PDF belgelerini daha ayrıntılı olarak inceleyin.

### PDF dosyasındaki veritabanıyla entegrasyona ilişkin SSS'ler

#### S: Aspose.PDF for .NET'i MySQL, SQL Server veya Oracle gibi farklı veritabanı türleriyle kullanabilir miyim?

C: Evet, Aspose.PDF for .NET'i MySQL, SQL Server, Oracle ve diğerleri gibi farklı veritabanı türleriyle kullanabilirsiniz. Aspose.PDF for .NET, veritabanları, XML dosyaları ve daha fazlası dahil olmak üzere çeşitli veri kaynaklarından veri okumak için işlevler sağlar. İstediğiniz veritabanı türünden veri alabilir ve bunu bir DataTable'a veya Aspose.PDF for .NET ile uyumlu herhangi bir veri yapısına yerleştirebilirsiniz.

#### S: Tablonun görünümünü PDF belgesinde nasıl özelleştirebilirim?

C: Aspose.PDF for .NET kütüphanesinin sağladığı çeşitli özellikleri kullanarak PDF belgesindeki tablonun görünümünü özelleştirebilirsiniz. Örneğin, tablo ve hücreleri için farklı kenarlık stilleri, arka plan renkleri, yazı tipi stilleri ve hizalama ayarlayabilirsiniz. Tablo görünümünü özelleştirme hakkında daha fazla ayrıntı için Aspose.PDF for .NET belgelerine bakın.

#### S: Veritabanından içe aktarılan verilere köprüler veya etkileşimli öğeler eklemek mümkün müdür?

C: Evet, veritabanından içe aktarılan verilere köprüler veya diğer etkileşimli öğeler ekleyebilirsiniz. Aspose.PDF for .NET, PDF belgesine köprüler, yer imleri ve diğer etkileşimli öğelerin eklenmesini destekler. DataTable'daki içeriği tabloya aktarmadan önce değiştirebilir ve köprüler veya diğer etkileşimli özellikler ekleyebilirsiniz.

#### S: Belirli bir satır sayısını aşarsa tabloyu sayfalara ayırabilir miyim?

 C: Evet, belirli bir satır sayısını aşarsa tabloyu sayfalara ayırabilirsiniz. Bunu başarmak için şunları kullanabilirsiniz:`IsInNewPage`Yeni bir sayfanın belirli bir satırdan sonra başlaması gerektiğini belirtmek için Row nesnesinin özelliği. Sayfa başına görüntülenecek satır sayısını hesaplayabilir ve`IsInNewPage` buna göre mülk.

#### S: Gömülü veritabanı verilerini içeren PDF belgesini DOCX veya XLSX gibi farklı dosya formatlarına nasıl aktarabilirim?

C: Aspose.PDF for .NET, PDF belgelerini DOCX (Microsoft Word) ve XLSX (Microsoft Excel) dahil olmak üzere diğer çeşitli dosya formatlarına dönüştürmenize olanak tanır. Bunu başarmak için Aspose.PDF for .NET kütüphanesini Aspose.Words ve Aspose.Cells gibi diğer Aspose kütüphaneleriyle birlikte kullanabilirsiniz. Öncelikle PDF belgesini gömülü veritabanı verileriyle birlikte kaydedin ve ardından ilgili Aspose kitaplığını kullanarak onu istediğiniz dosya formatına dönüştürün.