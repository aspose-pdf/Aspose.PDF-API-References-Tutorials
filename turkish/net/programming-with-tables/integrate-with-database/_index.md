---
title: PDF Dosyasında Veritabanıyla Entegre Edin
linktitle: PDF Dosyasında Veritabanıyla Entegre Edin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir veritabanındaki verileri PDF dosyasına gömün.
type: docs
weight: 120
url: /tr/net/programming-with-tables/integrate-with-database/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir veritabanındaki verileri PDF dosyasına nasıl gömeceğimizi öğreneceğiz. C#'ta kaynak kodunu adım adım anlatacağız. Bu eğitimin sonunda, tablo verilerini bir veritabanından bir PDF belgesine nasıl aktaracağınızı öğreneceksiniz. Hadi başlayalım!

## 1. Adım: Ortamı ayarlama
C# geliştirme ortamınızı Aspose.PDF for .NET ile yapılandırdığınızdan emin olun. Referansı kitaplığa ekleyin ve gerekli ad alanlarını içe aktarın.

## 2. Adım: DataTable'ı Oluşturma
PDF belgesine gömmek istediğimiz verileri temsil etmek için bir DataTable örneği oluşturuyoruz. Bu örnekte, üç sütunlu bir DataTable oluşturuyoruz: Çalışan_Kimliği, Çalışan_Adı ve Cinsiyet. Ayrıca DataTable'a kukla verilerle iki satır ekliyoruz.

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

## 3. Adım: PDF Belgesini ve Tablosunu Oluşturma
Document örneğini oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz. Ardından, tablomuzu PDF belgesinde temsil edecek bir Tablo örneği oluşturuyoruz. Tablo sütun genişliklerini ve kenarlık stillerini tanımlıyoruz.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Adım 4: DataTable'dan tabloya veri aktarma
Verileri DataTable'dan PDF belgesindeki tabloya aktarmak için ImportDataTable yöntemini kullanıyoruz.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Adım 5: Tabloyu belgeye ekleme
Tabloyu belge sayfasının paragraf koleksiyonuna ekliyoruz.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## 6. Adım: Belgeyi kaydedin
PDF belgesini gömülü veritabanındaki verilerle kaydediyoruz.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Tebrikler! Artık Aspose.PDF for .NET kullanarak veritabanı verilerini bir PDF belgesine nasıl gömeceğinizi biliyorsunuz.

### Aspose.PDF for .NET kullanarak Veritabanıyla Entegre Etme için örnek kaynak kodu

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
// Tablonun sütun genişliklerini ayarlama
table.ColumnWidths = "40 100 100 100";
// Tablo kenarlık rengini LightGray olarak ayarlayın
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
Bu öğreticide, Aspose.PDF for .NET kullanarak bir veri tabanındaki verileri bir PDF belgesine nasıl gömeceğimizi öğrendik. Verileri kendi veritabanınızdan içe aktarmak ve bunları PDF belgelerinde görüntülemek için bu adım adım kılavuzu kullanabilirsiniz. Bu güçlü kitaplığın sunduğu diğer özellikleri ve olasılıkları keşfetmek için Aspose.PDF belgelerini daha fazla keşfedin.

### PDF dosyasında veritabanıyla entegrasyon için SSS'ler

#### S: Aspose.PDF for .NET'i MySQL, SQL Server veya Oracle gibi farklı veritabanı türleri ile kullanabilir miyim?

C: Evet, Aspose.PDF for .NET'i MySQL, SQL Server, Oracle ve diğerleri gibi farklı veritabanı türleri ile kullanabilirsiniz. Aspose.PDF for .NET, veritabanları, XML dosyaları ve daha fazlası dahil olmak üzere çeşitli veri kaynaklarından veri okumak için işlevsellikler sağlar. İstediğiniz veri tabanı türünden verileri alabilir ve bunu bir DataTable'a veya Aspose.PDF for .NET ile uyumlu başka herhangi bir veri yapısına yerleştirebilirsiniz.

#### S: Tablonun görünümünü PDF belgesinde nasıl özelleştirebilirim?

C: Aspose.PDF for .NET kitaplığı tarafından sağlanan çeşitli özellikleri kullanarak PDF belgesindeki tablonun görünümünü özelleştirebilirsiniz. Örneğin, tablo ve hücreleri için farklı kenarlık stilleri, arka plan renkleri, yazı tipi stilleri ve hizalama ayarlayabilirsiniz. Tablo görünümünü özelleştirme hakkında daha fazla ayrıntı için Aspose.PDF for .NET belgelerine bakın.

#### S: Veritabanından içe aktarılan verilere köprüler veya etkileşimli öğeler eklemek mümkün müdür?

C: Evet, veritabanından içe aktarılan verilere köprüler veya diğer etkileşimli öğeler ekleyebilirsiniz. Aspose.PDF for .NET, PDF belgesine köprüler, yer imleri ve diğer etkileşimli öğeler eklemeyi destekler. İçeriği tabloya aktarmadan önce DataTable'da işleyebilir ve köprüler veya diğer etkileşimli özellikler ekleyebilirsiniz.

#### S: Belirli bir satır sayısını aşarsa tabloyu sayfalandırabilir miyim?

 C: Evet, belirli sayıda satırı aşarsa tabloyu sayfalandırabilirsiniz. Bunu başarmak için,`IsInNewPage`yeni bir sayfanın belirli bir satırdan sonra başlaması gerektiğini belirtmek için Row nesnesinin özelliği. Sayfa başına görüntülenecek satır sayısını hesaplayabilir ve`IsInNewPage` mülkiyet buna göre.

#### S: Gömülü veritabanı verileri içeren PDF belgesini DOCX veya XLSX gibi farklı dosya biçimlerine nasıl aktarabilirim?

Y: Aspose.PDF for .NET, PDF belgelerini DOCX (Microsoft Word) ve XLSX (Microsoft Excel) dahil olmak üzere çeşitli diğer dosya biçimlerine dönüştürmenize olanak tanır. Bunu başarmak için Aspose.PDF for .NET kitaplığını Aspose.Words ve Aspose.Cells gibi diğer Aspose kitaplıklarıyla birlikte kullanabilirsiniz. İlk olarak, gömülü veri tabanı verileriyle PDF belgesini kaydedin ve ardından onu istediğiniz dosya formatına dönüştürmek için ilgili Aspose kitaplığını kullanın.