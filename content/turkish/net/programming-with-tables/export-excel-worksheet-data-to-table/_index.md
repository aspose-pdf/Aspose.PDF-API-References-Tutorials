---
title: Excel Çalışma Sayfası Verilerini Tabloya Aktar
linktitle: Excel Çalışma Sayfası Verilerini Tabloya Aktar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak Excel sayfasındaki verileri PDF tablosuna aktarın.
type: docs
weight: 70
url: /tr/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
Bu eğitimde, Aspose.PDF for .NET kütüphanesini kullanarak bir Excel çalışma sayfasından veriyi nasıl dışarı aktaracağımızı ve bir PDF belgesinde tablo nasıl oluşturacağımızı öğreneceğiz. Kaynak kodu adım adım ele alacağız ve her bölümü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, Excel çalışma sayfalarından veri içeren tablolar içeren PDF dosyaları üretebileceksiniz. Başlayalım!

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi
- Makinenizde Visual Studio yüklü
- Aspose.PDF for .NET kütüphanesi projenize eklendi

## Adım 1: Ortamı Kurma
Başlamak için, Visual Studio'da yeni bir C# projesi oluşturun. Çözüm Gezgini'nde projenize sağ tıklayarak, "NuGet Paketlerini Yönet"i seçerek ve "Aspose.PDF"i arayarak Aspose.PDF for .NET kitaplığına referansı ekleyin. Paketi yükleyin ve gitmeye hazırsınız.

## Adım 2: Excel Çalışma Sayfasını Yükleme
Kodumuzun ilk adımında, Excel belgesini içeren dizine giden yolu tanımlıyoruz. "YOUR DOCUMENT DIRECTORY" ifadesini Excel dosyanızın bulunduğu gerçek dizin yoluyla değiştirin.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Burada, Excel çalışma kitabını yüklemek için Aspose.Cells kütüphanesini kullanıyoruz. "newBook1.xlsx"i Excel dosyanızın adıyla değiştirdiğinizden emin olun.

## Adım 3: Çalışma Sayfasına Erişim
 Sonra, Excel dosyasındaki ilk çalışma sayfasına erişmemiz gerekiyor. Bunu şu şekilde yapıyoruz:`Worksheets` koleksiyonu`Workbook` nesne.

```csharp
// Excel dosyasındaki ilk çalışma sayfasına erişim
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Excel dosyanız birden fazla çalışma sayfası içeriyorsa, dizin değerini değiştirebilirsiniz`[0]` farklı bir çalışma sayfasına erişmek için.

## Adım 4: Verileri DataTable'a Aktarma
 Şimdi Excel çalışma sayfasının içeriğini bir Excel dosyasına aktaracağız.`DataTable` nesne. Dışa aktarılacak hücre aralığını şunu kullanarak belirtiriz:`ExportDataTable` Yöntem.

```csharp
// 1. hücreden başlayarak 7 satır ve 2 sütunun içeriğini DataTable'a aktarma
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Bu örnekte, çalışma sayfasındaki ilk hücreden (0, 0) başlayarak son hücreye kadar tüm satırları ve sütunları dışa aktarıyoruz. Gereksinimlerinize göre uygun aralığı ayarlayın.

## Adım 5: PDF Belgesi Oluşturma
Şimdi Aspose.PDF kütüphanesini kullanarak yeni bir PDF belgesi oluşturacağız.

```csharp
// Bir Belge örneğini örneklendirin
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Bu, içerik ekleyebileceğimiz boş bir PDF belgesi oluşturur.

## Adım 6: Sayfa ve Tablo Ekleme
Verileri tablo formatında gösterebilmek için PDF belgesine bir sayfa ve bir tablo eklememiz gerekiyor.

```csharp
// Belge örneğinde bir sayfa oluşturun
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Bir Tablo nesnesi oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Bölümün paragraf koleksiyonuna Tablo nesnesini ekleyin
sec1.Paragraphs.Add(tab1);
```

Burada yeni bir sayfa ve bir tablo nesnesi oluşturuyoruz. Daha sonra tabloyu sayfanın paragraphs koleksiyonuna ekliyoruz.

## Adım 7: Tablo Özelliklerini Ayarlama
Verileri içe aktarmadan önce tablonun sütun genişlikleri ve varsayılan hücre kenarlıkları gibi bazı özelliklerini ayarlamamız gerekiyor.

```csharp
// Tablonun sütun genişliklerini ayarlayın
tab1.ColumnWidths = "40 100 100";

// BorderInfo nesnesini kullanarak tablonun varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Bu örnekte, sütun genişliklerini 40, 100 ve 100 birim olarak ayarladık. Değerleri verilerinize göre ayarlayın. Ayrıca, her hücrenin tüm taraflarında kenarlıklar görüntülemek için varsayılan hücre kenarlığını ayarladık.

## Adım 8: Verileri Tabloya Aktarma
 Şimdi, verileri şuradan içe aktaracağız:`DataTable` nesneyi tabloya kullanarak`ImportDataTable` Yöntem.

```csharp
// Yukarıda oluşturulan DataTable'dan Tablo nesnesine veri aktarın
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Burada, içe aktarılacak satır ve sütun aralığını belirtiyoruz. Bu örnekte, tüm satır ve sütunları içe aktarıyoruz`dataTable` nesne.

## Adım 9: Tabloyu Biçimlendirme
Tablonun görünümünü geliştirmek için belirli hücrelere veya satırlara biçimlendirme uygulayabiliriz. Bu adımda, tablonun ilk satırını ve diğer satırlarını biçimlendireceğiz.

```csharp
// Tablodan 1. satırı al
Aspose.Pdf.Row row1 = tab1.Rows[0];

// İlk satırı biçimlendir
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // İlk satırdaki hücrelerin arka plan rengini ayarlayın
     curCell.BackgroundColor = Color.Blue;// İlk satırdaki hücreler için yüzü ayarlayın
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // İlk satırdaki hücrelerin yazı tipi rengini ayarlayın
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // İlk satırdaki hücreler için metin hizalamasını ayarlayın
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternatif satır biçimi
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Alternatif satırlardaki hücrelerin arka plan rengini ayarlayın
         curCell.BackgroundColor = Color.Gray;
        
         // Alternatif satırlardaki hücrelerin metin rengini ayarlayın
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Burada, ilk satırdaki hücrelerde yineleme yaparız ve arka plan renklerini, yazı tipi yüzlerini, yazı tipi rengini ve metin hizalamalarını ayarlarız. Sonra, alternatif satırlardaki tüm hücrelerde yineleme yaparız ve arka plan ve metin renklerini ayarlarız.

## Adım 10: PDF Belgesini Kaydetme
Son olarak PDF dokümanını belirtilen konuma kaydediyoruz.

```csharp
// PDF'yi kaydet
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

"BELGE DİZİNİNİZ" ifadesini çıktı PDF dosyası için istediğiniz dizin yolu ve dosya adıyla değiştirdiğinizden emin olun.

### .NET için Aspose.PDF kullanarak Excel Çalışma Sayfası Verilerini Tabloya Aktarma için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Excel dosyasındaki ilk çalışma sayfasına erişim
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// 1. hücreden başlayarak 7 satır ve 2 sütunun içeriğini DataTable'a aktarma
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Bir Belge örneği oluşturun
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Belge örneğinde bir sayfa oluşturun
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Bir Tablo nesnesi oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Bölümün paragraf koleksiyonuna Tablo nesnesini ekleyin
sec1.Paragraphs.Add(tab1);

// Tablonun sütun genişliklerini ayarlayın. ColumnCount'u manuel olarak belirtmemiz gerekiyor.
// Mevcut Excel çalışma sayfası üç sütundan oluştuğu için aynı sayıyı belirtiyoruz
tab1.ColumnWidths = "40 100 100";

// BorderInfo nesnesini kullanarak tablonun varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Yukarıda oluşturulan DataTable'dan Tablo nesnesine veri aktarın
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Tablodan 1. satırı al
Aspose.Pdf.Row row1 = tab1.Rows[0];

// 1. satırdaki tüm hücreleri dolaşın ve arka plan renklerini mavi olarak ayarlayın
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Tablonun 1. satırındaki tüm hücrelerin arka planını ayarlayın.
	curCell.BackgroundColor = Color.Blue;
	// Tablonun 1. satırındaki hücrelerin yazı tipini ayarlayın.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Tablonun 1. satırındaki tüm hücrelerin yazı rengini ayarlayın.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// 1. satırdaki hücrelerin metin hizalamasını Orta olarak ayarlayın.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// 1. satırdaki tüm hücreleri dolaşın ve arka plan renklerini mavi olarak ayarlayın
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// 1. satır hariç tüm hücrelerin arka plan rengini ayarlayın.
		curCell.BackgroundColor = Color.Gray;
		// 1. satır hariç tüm hücrelerin Metin rengini ayarlayın.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// PDF'yi kaydet
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kitaplığını kullanarak bir Excel çalışma sayfasından bir PDF tablosuna veri aktarmayı öğrendik. Excel çalışma sayfasını yükleme, bir PDF belgesi oluşturma, bir tablo ekleme, veri içe aktarma ve tabloyu biçimlendirme adım adım sürecini ele aldık. Artık Excel verilerini içeren tablolara sahip PDF dosyalarını programatik olarak üretebilirsiniz.

### SSS

#### S: Excel çalışma sayfası verilerini PDF tablosuna aktarmanın amacı nedir?

A: Excel çalışma sayfası verilerini bir PDF tablosuna aktarmak, verileri yapılandırılmış ve organize bir biçimde sunmanıza olanak tanır. Excel çalışma sayfalarından veri içeren tablolar içeren PDF dosyaları oluşturmanızı sağlayarak, bilgileri taşınabilir bir belge biçiminde paylaşmayı ve korumayı kolaylaştırır.

#### S: PDF tablosunun görünümünü özelleştirebilir miyim?

A: Evet, Aspose.PDF for .NET tarafından sağlanan çeşitli özellikleri kullanarak PDF tablosunun görünümünü özelleştirebilirsiniz. Sağlanan C# kaynak kodunda, sütun genişliklerini, hücre kenarlıklarını, metin hizalamasını, yazı tipi stilini ve daha fazlasını özel gereksinimlerinize uyacak şekilde değiştirebilirsiniz.

#### S: Birden fazla çalışma sayfası içeren Excel dosyalarını nasıl işlerim?

 A: Sağlanan C# kodunda, Excel dosyasındaki ilk çalışma sayfasına indeksi kullanarak eriştik`[0]` Excel dosyanız birden fazla çalışma sayfası içeriyorsa, bunlara dizin değerini buna göre değiştirerek erişebilirsiniz, örneğin:`[1]` ikinci çalışma sayfası için veya`[2]` Üçüncü çalışma kağıdı için.

#### S: PDF tablosundaki belirli satırlara veya hücrelere farklı biçimlendirme uygulayabilir miyim?

C: Evet, PDF tablosundaki belirli satırlara veya hücrelere farklı biçimlendirme uygulayabilirsiniz. Sağlanan C# kaynak kodunda, arka plan rengini, yazı tipi stilini ve yazı tipi rengini değiştirerek ilk satırı ve alternatif satırları nasıl farklı şekilde biçimlendireceğinizi gösterdik. İhtiyaç duyduğunuzda belirli satırlara veya hücrelere benzer biçimlendirme teknikleri uygulayabilirsiniz.

#### S: Aspose.PDF for .NET, Excel verilerini PDF tablosuna aktarmaya izin veren tek kütüphane midir?

A: Aspose.PDF for .NET, .NET uygulamalarında PDF belgeleriyle çalışmak için güçlü bir kütüphanedir. Başka kütüphaneler de mevcut olsa da, Aspose.PDF for .NET, Excel verilerinden tablolar içeren PDF dosyaları oluşturmak, düzenlemek ve dışa aktarmak için çok çeşitli özellikler ve yetenekler sunar ve bu da onu bu tür görevler için popüler bir seçim haline getirir.