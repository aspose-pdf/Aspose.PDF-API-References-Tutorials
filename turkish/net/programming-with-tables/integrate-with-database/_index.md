---
title: Veritabanıyla Entegre Edin
linktitle: Veritabanıyla Entegre Edin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir veritabanındaki verileri bir PDF belgesine gömün.
type: docs
weight: 120
url: /tr/net/programming-with-tables/integrate-with-database/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak bir veri tabanındaki verileri bir PDF belgesine nasıl gömeceğimizi öğreneceğiz. C#'ta kaynak kodunu adım adım anlatacağız. Bu eğitimin sonunda, tablo verilerini bir veritabanından bir PDF belgesine nasıl aktaracağınızı öğreneceksiniz. Hadi başlayalım!

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

### Aspose.Words for .NET kullanarak Veritabanıyla Entegre Etme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
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