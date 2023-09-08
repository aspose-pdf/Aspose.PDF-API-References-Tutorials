---
title: Excel Çalışma Sayfası Verilerini Tabloya Aktarma
linktitle: Excel Çalışma Sayfası Verilerini Tabloya Aktarma
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak verileri bir Excel sayfasından PDF tablosuna aktarın.
type: docs
weight: 70
url: /tr/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
Bu eğitimde, Aspose.PDF for .NET kitaplığını kullanarak bir Excel çalışma sayfasından verileri nasıl dışa aktaracağımızı ve bir PDF belgesinde nasıl tablo oluşturacağımızı öğreneceğiz. Kaynak kodunu adım adım inceleyeceğiz ve her bölümü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda Excel çalışma sayfalarından veri içeren tablolar içeren PDF dosyaları oluşturabileceksiniz. Başlayalım!

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Makinenizde Visual Studio yüklü
- Aspose.PDF for .NET kütüphanesi projenize eklendi

## 1. Adım: Ortamı Ayarlama
Başlamak için Visual Studio'da yeni bir C# projesi oluşturun. Solution Explorer'da projenize sağ tıklayıp "NuGet Paketlerini Yönet" seçeneğini seçip "Aspose.PDF" ifadesini arayarak Aspose.PDF for .NET kitaplığına referansı ekleyin. Paketi yükleyin ve başlamaya hazırsınız.

## Adım 2: Excel Çalışma Sayfasını Yükleme
Kodumuzun ilk adımında Excel belgesinin bulunduğu dizinin yolunu tanımlıyoruz. "BELGE DİZİNİNİZ" ifadesini Excel dosyanızın bulunduğu gerçek dizin yolu ile değiştirin.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Burada Excel çalışma kitabını yüklemek için Aspose.Cells kütüphanesini kullanıyoruz. "newBook1.xlsx" ifadesini Excel dosyanızın adıyla değiştirdiğinizden emin olun.

## Adım 3: Çalışma Sayfasına Erişim
 Daha sonra Excel dosyasındaki ilk çalışma sayfasına erişmemiz gerekiyor. Bunu kullanarak yapıyoruz`Worksheets` koleksiyonu`Workbook` nesne.

```csharp
// Excel dosyasındaki ilk çalışma sayfasına erişme
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Excel dosyanız birden fazla çalışma sayfası içeriyorsa dizin değerini değiştirebilirsiniz`[0]` Farklı bir çalışma sayfasına erişmek için.

## Adım 4: Verileri DataTable'a Aktarma
 Şimdi Excel çalışma sayfasının içeriğini bir dosyaya aktaracağız.`DataTable` nesne. Dışa aktarılacak hücre aralığını kullanarak belirleriz.`ExportDataTable` yöntem.

```csharp
// 1. hücreden başlayarak 7 satır ve 2 sütunun içeriğini DataTable'a aktarma
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Bu örnekte, çalışma sayfasındaki ilk hücreden (0, 0) son hücreye kadar tüm satır ve sütunları dışa aktarıyoruz. Gereksinimlerinize göre uygun aralığı ayarlayın.

## Adım 5: PDF Belgesi Oluşturma
Şimdi Aspose.PDF kütüphanesini kullanarak yeni bir PDF belgesi oluşturacağız.

```csharp
// Bir Belge örneği oluşturun
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Bu, içerik ekleyebileceğimiz boş bir PDF belgesi oluşturur.

## Adım 6: Sayfa ve Tablo Ekleme
Verileri tablo formatında görüntülemek için PDF belgesine bir sayfa ve bir tablo eklememiz gerekir.

```csharp
// Belge örneğinde bir sayfa oluşturun
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Tablo nesnesi oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tablo nesnesini bölümün paragraf koleksiyonuna ekleyin
sec1.Paragraphs.Add(tab1);
```

Burada yeni bir sayfa ve tablo nesnesi oluşturuyoruz. Daha sonra tabloyu sayfanın paragraf koleksiyonuna ekliyoruz.

## Adım 7: Tablo Özelliklerini Ayarlama
Verileri içe aktarmadan önce tablonun sütun genişlikleri ve varsayılan hücre sınırları gibi bazı özelliklerini ayarlamamız gerekir.

```csharp
// Tablonun sütun genişliklerini ayarlayın
tab1.ColumnWidths = "40 100 100";

// BorderInfo nesnesini kullanarak tablonun varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Bu örnekte sütun genişliklerini 40, 100 ve 100 birime ayarladık. Verilerinize göre değerleri ayarlayın. Ayrıca, her hücrenin her tarafında kenarlıklar görüntülenecek şekilde varsayılan hücre kenarlığını da ayarladık.

## Adım 8: Verileri Tabloya Aktarma
 Şimdi verileri dosyadan içe aktaracağız.`DataTable` kullanarak tabloya nesne ekleyin.`ImportDataTable` yöntem.

```csharp
// Yukarıda oluşturulan DataTable'dan Table nesnesine veri aktarın
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Burada içe aktarılacak satır ve sütun aralığını belirtiyoruz. Bu örnekte, tüm satırları ve sütunları içe aktarıyoruz.`dataTable` nesne.

## Adım 9: Tabloyu Biçimlendirmek
Tablonun görünümünü geliştirmek için belirli hücrelere veya satırlara biçimlendirme uygulayabiliriz. Bu adımda tablonun ilk satırını ve alternatif satırlarını biçimlendireceğiz.

```csharp
// Tablodan 1. satırı alın
Aspose.Pdf.Row row1 = tab1.Rows[0];

// İlk satırı biçimlendir
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // İlk satırdaki hücrelerin arka plan rengini ayarlayın
     curCell.BackgroundColor = Color.Blue;// İlk satırdaki hücrelerin yüzünü ayarlayın
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // İlk satırdaki hücrelerin yazı tipi rengini ayarlayın
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // İlk satırdaki hücrelerin metin hizalamasını ayarlama
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternatif satır biçimi
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Alternatif satırlardaki hücrelerin arka plan rengini ayarlama
         curCell.BackgroundColor = Color.Gray;
        
         // Alternatif satırlardaki hücrelerin metin rengini ayarlama
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Burada, ilk satırdaki hücreler arasında geçiş yapıyoruz ve bunların arka plan rengini, yazı tipi yüzünü, yazı tipi rengini ve metin hizalamasını ayarlıyoruz. Daha sonra alternatif satırlardaki tüm hücreleri yineleyerek arka planlarını ve metin renklerini ayarlıyoruz.

## Adım 10: PDF Belgesini Kaydetme
Son olarak PDF belgesini belirtilen konuma kaydediyoruz.

```csharp
// PDF'yi kaydet
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Çıktı PDF dosyası için "BELGE DİZİNİ"ni istediğiniz dizin yolu ve dosya adı ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanarak Excel Çalışma Sayfası Verilerini Tabloya Dışa Aktarma için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Excel dosyasındaki ilk çalışma sayfasına erişme
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// 1. hücreden başlayarak 7 satır ve 2 sütunun içeriğini DataTable'a aktarma
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Bir Belge örneğini örnekleyin
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Belge örneğinde bir sayfa oluşturun
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Tablo nesnesi oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tablo nesnesini bölümün paragraf koleksiyonuna ekleyin
sec1.Paragraphs.Add(tab1);

// Tablonun sütun genişliklerini ayarlayın. ColumnCount'u manuel olarak belirtmemiz gerekiyor.
// Mevcut excel çalışma sayfasında üç sütun olduğundan aynı sayıyı belirtiyoruz
tab1.ColumnWidths = "40 100 100";

// BorderInfo nesnesini kullanarak tablonun varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Yukarıda oluşturulan DataTable'dan Table nesnesine veri aktarın
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Tablodan 1. satırı alın
Aspose.Pdf.Row row1 = tab1.Rows[0];

// 1. satırdaki tüm hücreleri yineleyin ve arka plan rengini mavi olarak ayarlayın
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Tablonun 1. satırındaki tüm hücrelerin arka planını ayarlayın.
	curCell.BackgroundColor = Color.Blue;
	// Tablonun 1. satırındaki hücrelerin yazı tipi yüzünü ayarlayın.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Tablonun 1. satırındaki tüm hücrelerin yazı tipi rengini ayarlayın.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// 1. satırdaki hücrelerin metin hizalamasını Orta olarak ayarlayın.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// 1. satırdaki tüm hücreleri yineleyin ve arka plan rengini mavi olarak ayarlayın
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// 1. satır dışındaki tüm hücrelerin arka plan rengini ayarlayın.
		curCell.BackgroundColor = Color.Gray;
		// 1. satır dışındaki tüm hücrelerin Metin rengini ayarlayın.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// PDF'yi kaydet
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kütüphanesini kullanarak bir Excel çalışma sayfasındaki verileri bir PDF tablosuna nasıl aktaracağımızı öğrendik. Excel çalışma sayfasını yükleme, PDF belgesi oluşturma, tablo ekleme, verileri içe aktarma ve tabloyu biçimlendirme işlemlerini adım adım ele aldık. Artık program aracılığıyla Excel verilerini içeren tablolarla PDF dosyaları oluşturabilirsiniz.

### SSS'ler

#### S: Excel çalışma sayfası verilerini PDF tablosuna aktarmanın amacı nedir?

C: Excel çalışma sayfası verilerini bir PDF tablosuna aktarmak, verileri yapılandırılmış ve düzenli bir biçimde sunmanıza olanak tanır. Excel çalışma sayfalarından veri içeren tablolarla PDF dosyaları oluşturmanıza olanak tanır ve bilgilerin taşınabilir bir belge biçiminde paylaşılmasını ve korunmasını kolaylaştırır.

#### S: PDF tablosunun görünümünü özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET tarafından sağlanan çeşitli özellikleri kullanarak PDF tablosunun görünümünü özelleştirebilirsiniz. Sağlanan C# kaynak kodunda sütun genişliklerini, hücre kenarlıklarını, metin hizalamasını, yazı tipi stilini ve daha fazlasını özel gereksinimlerinize uyacak şekilde değiştirebilirsiniz.

#### S: Birden fazla çalışma sayfası içeren Excel dosyalarını nasıl yönetirim?

 C: Sağlanan C# kodunda, dizini kullanarak Excel dosyasındaki ilk çalışma sayfasına eriştik.`[0]` . Excel dosyanız birden fazla çalışma sayfası içeriyorsa, dizin değerini uygun şekilde değiştirerek bunlara erişebilirsiniz.`[1]` ikinci çalışma sayfası için veya`[2]` üçüncü çalışma sayfası için.

#### S: PDF tablosundaki belirli satırlara veya hücrelere farklı formatlama uygulayabilir miyim?

C: Evet, PDF tablosundaki belirli satırlara veya hücrelere farklı formatlama uygulayabilirsiniz. Sağlanan C# kaynak kodunda, arka plan rengini, yazı tipi stilini ve yazı tipi rengini değiştirerek ilk satırın ve alternatif satırların nasıl farklı şekilde biçimlendirileceğini gösterdik. Gerektiğinde belirli satırlara veya hücrelere benzer biçimlendirme tekniklerini uygulayabilirsiniz.

#### S: Aspose.PDF for .NET, Excel verilerinin PDF tablosuna aktarılmasına izin veren tek kitaplık mıdır?

C: Aspose.PDF for .NET, .NET uygulamalarında PDF belgeleriyle çalışmak için güçlü bir kütüphanedir. Başka kütüphaneler de mevcut olsa da, Aspose.PDF for .NET, Excel verilerinden tablolar içeren PDF dosyaları oluşturmak, düzenlemek ve dışa aktarmak için çok çeşitli özellikler ve yetenekler sunar ve bu da onu bu tür görevler için popüler bir seçim haline getirir.