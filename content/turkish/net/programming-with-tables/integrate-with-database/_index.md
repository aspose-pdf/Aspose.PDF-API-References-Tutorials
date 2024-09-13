---
title: PDF Dosyasında Veritabanıyla Entegre Et
linktitle: PDF Dosyasında Veritabanıyla Entegre Et
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak veritabanındaki verileri PDF dosyasına gömün.
type: docs
weight: 120
url: /tr/net/programming-with-tables/integrate-with-database/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir veritabanından PDF dosyasına veri yerleştirmeyi öğreneceğiz. Kaynak kodunu adım adım C# dilinde açıklayacağız. Bu eğitimin sonunda, bir veritabanından tablo verilerini bir PDF belgesine nasıl içe aktaracağınızı öğreneceksiniz. Başlayalım!

## Adım 1: Ortamı kurma
C# geliştirme ortamınızı .NET için Aspose.PDF ile yapılandırdığınızdan emin olun. Referansı kütüphaneye ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: DataTable'ı Oluşturma
PDF belgesine yerleştirmek istediğimiz verileri temsil etmek için bir DataTable örneği oluşturuyoruz. Bu örnekte, üç sütunlu bir DataTable oluşturuyoruz: Employee_ID, Employee_Name ve Gender. Ayrıca, DataTable'a sahte veriler içeren iki satır ekliyoruz.

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

## Adım 3: PDF Belgesi ve Tablo Oluşturma
Bir Document örneği oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz. Sonra, PDF belgesinde tablomuzu temsil edecek bir Table örneği oluşturuyoruz. Tablo sütun genişliklerini ve kenarlık stillerini tanımlıyoruz.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Adım 4: DataTable'dan tabloya veri aktarma
PDF belgesindeki tabloya DataTable'daki verileri aktarmak için ImportDataTable metodunu kullanıyoruz.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Adım 5: Tabloyu belgeye ekleme
Tabloyu belge sayfasının paragraf koleksiyonuna ekliyoruz.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Adım 6: Belgeyi kaydedin
Gömülü veritabanındaki verileri içeren PDF dokümanını kaydediyoruz.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Tebrikler! Artık Aspose.PDF for .NET kullanarak veritabanı verilerini bir PDF belgesine nasıl gömeceğinizi biliyorsunuz.

### .NET için Aspose.PDF kullanarak Veritabanıyla Entegre Etme için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//DataTable nesnesine programlı olarak 2 satır ekleyin
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
// Tablo kenarlık rengini AçıkGri olarak ayarlayın
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Tablo hücreleri için kenarlığı ayarlayın
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Giriş belgesinin ilk sayfasına tablo nesnesi ekle
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Tablo nesnesini içeren güncellenmiş belgeyi kaydet
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir veritabanından verileri bir PDF belgesine nasıl gömeceğimizi öğrendik. Bu adım adım kılavuzu kullanarak verileri kendi veritabanınızdan içe aktarabilir ve PDF belgelerinde görüntüleyebilirsiniz. Bu güçlü kütüphanenin sunduğu diğer özellikleri ve olasılıkları keşfetmek için Aspose.PDF belgelerini daha fazla inceleyin.

### PDF dosyasında veritabanıyla bütünleşmeye ilişkin SSS

#### S: Aspose.PDF for .NET'i MySQL, SQL Server veya Oracle gibi farklı veritabanı türleriyle kullanabilir miyim?

C: Evet, Aspose.PDF for .NET'i MySQL, SQL Server, Oracle ve diğerleri gibi farklı veritabanı türleriyle kullanabilirsiniz. Aspose.PDF for .NET, veritabanları, XML dosyaları ve daha fazlası dahil olmak üzere çeşitli veri kaynaklarından veri okumak için işlevler sağlar. İstediğiniz veritabanı türünden veri alabilir ve bunları bir DataTable'a veya Aspose.PDF for .NET ile uyumlu başka bir veri yapısına doldurabilirsiniz.

#### S: PDF belgesindeki tablonun görünümünü nasıl özelleştirebilirim?

A: Aspose.PDF for .NET kitaplığı tarafından sağlanan çeşitli özellikleri kullanarak PDF belgesindeki tablonun görünümünü özelleştirebilirsiniz. Örneğin, tablo ve hücreleri için farklı kenarlık stilleri, arka plan renkleri, yazı tipleri ve hizalama ayarlayabilirsiniz. Tablo görünümünü özelleştirme hakkında daha fazla ayrıntı için Aspose.PDF for .NET belgelerine bakın.

#### S: Veritabanından aktarılan verilere hiperlink veya etkileşimli elemanlar eklemek mümkün müdür?

A: Evet, veritabanından içe aktarılan verilere köprü metinleri veya diğer etkileşimli öğeler ekleyebilirsiniz. Aspose.PDF for .NET, PDF belgesine köprü metinleri, yer imleri ve diğer etkileşimli öğeler eklemeyi destekler. DataTable'daki içeriği tabloya içe aktarmadan önce düzenleyebilir ve köprü metinleri veya diğer etkileşimli özellikler ekleyebilirsiniz.

#### S: Tablo belirli sayıda satırı aşarsa sayfalandırabilir miyim?

A: Evet, tablo belirli sayıda satırı aşarsa sayfalandırabilirsiniz. Bunu başarmak için şunu kullanabilirsiniz:`IsInNewPage` Satır nesnesinin, belirli bir satırdan sonra yeni bir sayfanın başlaması gerektiğini belirten özelliği. Sayfa başına görüntülenecek satır sayısını hesaplayabilir ve`IsInNewPage` mülkiyet buna göre.

#### S: Gömülü veritabanı verilerinin bulunduğu PDF belgesini DOCX veya XLSX gibi farklı dosya formatlarına nasıl aktarabilirim?

A: Aspose.PDF for .NET, PDF belgelerini DOCX (Microsoft Word) ve XLSX (Microsoft Excel) dahil olmak üzere çeşitli diğer dosya biçimlerine dönüştürmenize olanak tanır. Bunu başarmak için Aspose.PDF for .NET kitaplığını Aspose.Words ve Aspose.Cells gibi diğer Aspose kitaplıklarıyla birlikte kullanabilirsiniz. Öncelikle, PDF belgesini gömülü veritabanı verileriyle kaydedin ve ardından ilgili Aspose kitaplığını kullanarak istediğiniz dosya biçimine dönüştürün.