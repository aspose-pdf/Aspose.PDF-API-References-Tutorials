---
title: Üstbilgi Altbilgi Bölümündeki Tablo
linktitle: Üstbilgi Altbilgi Bölümündeki Tablo
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin üst bilgi/alt bilgi bölümüne tablo eklemeyi öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinin üst bilgi veya alt bilgi bölümüne nasıl tablo ekleyeceğiniz konusunda size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodu size boş bir PDF belgesi oluşturmayı, sayfa eklemeyi, başlık bölümünü yapılandırmayı, tablo oluşturmayı, tabloya satırlar ve hücreler eklemeyi ve son olarak PDF belgesini kaydetmeyi gösterir.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF Belgesini ve Sayfasını Oluşturma

 İlk adım, örneğinin bir örneğini oluşturmaktır.`Document` class ve belgeye bir sayfa ekleyin. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge nesnesi örneği oluşturma
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// PDF belgesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

"BELGELER DİZİNİNİZİ", PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Başlık bölümünü yapılandırma

 Şimdi, örneğini oluşturarak PDF belgesinin başlık bölümünü yapılandıracağız.`HeaderFooter` sınıf. İşte nasıl:

```csharp
// PDF dosyası için bir başlık bölümü oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Sayfa için başlık bölümünü tanımlayın
page. Header = header;

// Başlık bölümünün üst kenar boşluğunu ayarlayın
header. Margin. Top = 20;
```

## 4. Adım: Tabloyu oluşturma

 Şimdi kullanarak bir tablo oluşturacağız.`Table`class ve onu başlık bölümünün paragraf koleksiyonuna ekleyin. İşte nasıl:

```csharp
// Bir Tablo nesnesini somutlaştırın
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tabloyu başlık bölümünün paragraf koleksiyonuna ekleyin
header.Paragraphs.Add(tab1);

// Tablonun sütunlarının genişliklerini tanımlayın
tab1.ColumnWidths = "60,300";
```

Yukarıdaki kod, belirtilen genişlikte iki sütun içeren bir tablo oluşturur.

## 5. Adım: Tabloya satır ve hücre ekleyin

 Şimdi tabloya satırlar ve hücreler ekleyeceğiz.`Row` sınıf ve`Cell` sınıf. İşte nasıl:

```csharp
// Tabloda bir satır oluşturun ve hücreleri ekleyin
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// İlk satırın ilk hücresini birleştir
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Tabloda başka bir satır oluşturun ve resim içeren bir hücre ekleyin
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## 6. Adım: PDF Belgesini Kaydetme

Tablo başlık bölümüne eklendikten sonra, PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// PDF dosyasını kaydedin
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Üstbilgi Altbilgi Bölümündeki Tablo için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucuyu çağırarak Belge örneğini oluşturun
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Pdf belgesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// PDF dosyasının bir Başlık Bölümü oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// PDF dosyası için Tek Başlığı ayarlayın
page.Header = header;

//Başlık bölümü için üst kenar boşluğunu ayarlayın
header.Margin.Top = 20;

// Bir tablo nesnesini somutlaştırın
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
header.Paragraphs.Add(tab1);

// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Tablonun sütun genişlikleriyle ayarla
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// İlk satır için satır yayılma değerini 2 olarak ayarlayın
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Row2 için arka plan rengini ayarlayın
row2.BackgroundColor = Color.White;

// Resmi tutan hücreyi ekleyin
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Görüntü genişliğini 60 olarak ayarlayın
img.FixWidth = 60;

// Resmi tablo hücresine ekleyin
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Metnin dikey hizalamasını ortaya hizalanmış olarak ayarla
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Pdf dosyasını kaydedin
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin üst bilgi veya alt bilgi bölümüne tablo eklemeyi öğrendiniz. Artık PDF belgelerinizde ek bilgileri görüntülemek için tablolar ekleyerek üstbilgilerinizi ve altbilgilerinizi özelleştirebilirsiniz.
