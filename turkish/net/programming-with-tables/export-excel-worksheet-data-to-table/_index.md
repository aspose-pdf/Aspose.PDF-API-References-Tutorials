---
title: Excel Çalışma Sayfası Verilerini Tabloya Aktar
linktitle: Excel Çalışma Sayfası Verilerini Tabloya Aktar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak verileri bir Excel sayfasından bir PDF tablosuna aktarın.
type: docs
weight: 70
url: /tr/net/programming-with-tables/export-excel-worksheet-data-to-table/
---

Bu öğreticide, Aspose.PDF for .NET kitaplığını kullanarak bir Excel çalışma sayfasından verileri dışa aktarmayı ve bir PDF belgesinde tablo oluşturmayı öğreneceğiz. Kaynak kodunu adım adım inceleyeceğiz ve her bölümü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, Excel çalışma sayfalarından veriler içeren tablolar içeren PDF dosyaları oluşturabileceksiniz. Başlayalım!

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Makinenizde yüklü Visual Studio
- Aspose.PDF for .NET kitaplığı projenize eklendi

## 1. Adım: Ortamı Kurma
Başlamak için Visual Studio'da yeni bir C# projesi oluşturun. Solution Explorer'da projenize sağ tıklayarak, "NuGet Paketlerini Yönet"i seçerek ve "Aspose.PDF"yi arayarak Aspose.PDF for .NET kitaplığına referans ekleyin. Paketi yükleyin ve gitmeye hazırsınız.

## 2. Adım: Excel Çalışma Sayfasını Yükleme
Kodumuzun ilk adımında Excel belgesinin bulunduğu dizinin yolunu tanımlıyoruz. "BELGE DİZİNİNİZİ" Excel dosyanızın bulunduğu gerçek dizin yolu ile değiştirin.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Burada, Excel çalışma kitabını yüklemek için Aspose.Cells kütüphanesini kullanıyoruz. "newBook1.xlsx"i Excel dosyanızın adıyla değiştirdiğinizden emin olun.

## 3. Adım: Çalışma Sayfasına Erişim
 Ardından, Excel dosyasındaki ilk çalışma sayfasına erişmemiz gerekiyor. Bunu kullanarak yapıyoruz`Worksheets` koleksiyonu`Workbook` nesne.

```csharp
// Excel dosyasındaki ilk çalışma sayfasına erişme
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Excel dosyanız birden çok çalışma sayfası içeriyorsa, dizin değerini değiştirebilirsiniz.`[0]` farklı bir çalışma sayfasına erişmek için

## 4. Adım: Verileri DataTable'a Aktarma
 Şimdi, Excel çalışma sayfasının içeriğini bir dışa aktaracağız.`DataTable` nesne. Kullanarak dışa aktarılacak hücre aralığını belirtiyoruz.`ExportDataTable` yöntem.

```csharp
// 1. hücreden başlayarak 7 satır ve 2 sütun içeriğini DataTable'a aktarma
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Bu örnekte, çalışma sayfasındaki ilk hücreden (0, 0) başlayarak son hücreye kadar tüm satırları ve sütunları dışa aktarıyoruz. Gereksinimlerinize göre uygun aralığı ayarlayın.

## 5. Adım: Bir PDF Belgesi Oluşturma
Şimdi Aspose.PDF kütüphanesini kullanarak yeni bir PDF belgesi oluşturacağız.

```csharp
//Bir Document örneğini somutlaştırın
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Bu, içerik ekleyebileceğimiz boş bir PDF belgesi oluşturur.

## Adım 6: Sayfa ve Tablo Ekleme
Verileri tablo biçiminde görüntülemek için PDF belgesine bir sayfa ve bir tablo eklememiz gerekir.

```csharp
// Belge örneğinde bir sayfa oluşturun
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Tablo nesnesi oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Bölümün paragraflar koleksiyonuna Tablo nesnesini ekleyin
sec1.Paragraphs.Add(tab1);
```

Burada yeni bir sayfa ve bir tablo nesnesi oluşturuyoruz. Daha sonra tabloyu sayfanın paragraf koleksiyonuna ekliyoruz.

## Adım 7: Tablo Özelliklerini Ayarlama
Verileri içe aktarmadan önce, sütun genişlikleri ve varsayılan hücre sınırları gibi tablonun bazı özelliklerini ayarlamamız gerekiyor.

```csharp
// Tablonun sütun genişliklerini ayarlama
tab1.ColumnWidths = "40 100 100";

// BorderInfo nesnesini kullanarak tablonun varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Bu örnekte sütun genişliklerini 40, 100 ve 100 birim olarak ayarladık. Verilerinize göre değerleri ayarlayın. Ayrıca varsayılan hücre kenarlığını, her bir hücrenin tüm kenarlarında kenarlıkları gösterecek şekilde ayarladık.

## 8. Adım: Verileri Tabloya Aktarma
Şimdi, verileri bilgisayardan içe aktaracağız.`DataTable` kullanarak tabloya nesne`ImportDataTable` yöntem.

```csharp
// Yukarıda oluşturulan DataTable'dan Table nesnesine veri aktarın
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Burada, içe aktarılacak satır ve sütun aralığını belirtiyoruz. Bu örnekte, tüm satırları ve sütunları içe aktarıyoruz.`dataTable` nesne.

## Adım 9: Tabloyu Biçimlendirmek
Tablonun görünümünü iyileştirmek için belirli hücrelere veya satırlara biçimlendirme uygulayabiliriz. Bu adımda, tablonun ilk satırını ve alternatif satırlarını biçimlendireceğiz.

```csharp
// Tablodan 1. sırayı alın
Aspose.Pdf.Row row1 = tab1.Rows[0];

// İlk satırı biçimlendir
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // İlk satırdaki hücrelerin arka plan rengini ayarlayın
     curCell.BackgroundColor = Color.Blue;// İlk satırdaki hücrelerin yüzünü ayarlayın
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // İlk satırdaki hücrelerin yazı tipi rengini ayarlayın
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // İlk satırdaki hücreler için metin hizalamasını ayarlayın
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternatif satır formatı
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Hücrelerin arka plan rengini alternatif satırlarda ayarlayın
         curCell.BackgroundColor = Color.Gray;
        
         // Hücrelerin metin rengini alternatif satırlarda ayarlayın
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Burada, ilk satırdaki hücreleri yineliyoruz ve arka plan rengini, yazı tipi yüzünü, yazı tipi rengini ve metin hizalamasını ayarlıyoruz. Ardından, alternatif satırlardaki tüm hücreleri yineliyoruz ve arka plan ve metin rengini belirliyoruz.

## 10. Adım: PDF Belgesini Kaydetme
Son olarak, PDF belgesini belirtilen konuma kaydediyoruz.

```csharp
// PDF'yi kaydet
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Çıktı PDF dosyası için "BELGE DİZİNİNİZİ" istenen dizin yolu ve dosya adıyla değiştirdiğinizden emin olun.

### Aspose.Words for .NET kullanarak Excel Çalışma Sayfası Verilerini Tabloya Dışa Aktarma için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Excel dosyasındaki ilk çalışma sayfasına erişme
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// 1. hücreden başlayarak 7 satır ve 2 sütun içeriğini DataTable'a aktarma
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Bir Document örneğini oluşturun
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Belge örneğinde bir sayfa oluşturun
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Tablo nesnesi oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Bölümün paragraflar koleksiyonuna Tablo nesnesini ekleyin
sec1.Paragraphs.Add(tab1);

// Tablonun sütun genişliklerini ayarlayın. ColumnCount'u manuel olarak belirlememiz gerekiyor.
// Mevcut excel çalışma sayfasında üç sütun olduğu için aynı sayıyı belirtiyoruz.
tab1.ColumnWidths = "40 100 100";

// BorderInfo nesnesini kullanarak tablonun varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Yukarıda oluşturulan DataTable'dan Table nesnesine veri aktarın
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Tablodan 1. sırayı alın
Aspose.Pdf.Row row1 = tab1.Rows[0];

// 1. sıradaki tüm hücreleri yineleyin ve arka plan rengini mavi olarak ayarlayın
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Tablonun 1. satırındaki tüm hücrelerin arka planını ayarlayın.
	curCell.BackgroundColor = Color.Blue;
	// Tablodaki 1. satırdaki hücreler için yazı tipi yüzünü ayarlayın.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	//Tablonun 1. satırındaki tüm hücrelerin yazı tipi rengini ayarlayın.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// 1. sıradaki hücreler için metin hizalamasını Orta olarak ayarlayın.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// 1. sıradaki tüm hücreleri yineleyin ve arka plan rengini mavi olarak ayarlayın
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// 1. sıra hariç tüm hücrelerin arka plan rengini ayarlayın.
		curCell.BackgroundColor = Color.Gray;
		// 1. satır hariç tüm hücrelerin Metin rengini ayarlayın.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Pdf'i kaydet
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kitaplığını kullanarak bir Excel çalışma sayfasındaki verileri bir PDF tablosuna nasıl aktaracağımızı öğrendik. Excel çalışma sayfasını yükleme, PDF belgesi oluşturma, tablo ekleme, verileri içe aktarma ve tabloyu biçimlendirme sürecini adım adım ele aldık. Artık Excel verilerini içeren tablolarla programlı olarak PDF dosyaları oluşturabilirsiniz.