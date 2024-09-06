---
title: Üstbilgi Altbilgi Bölümündeki Tablo
linktitle: Üstbilgi Altbilgi Bölümündeki Tablo
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin üstbilgi/altbilgi bölümüne tablo eklemeyi öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinin başlık veya altbilgi bölümüne bir tablonun nasıl ekleneceğini adım adım göstereceğiz. Sağlanan C# kaynak kodu, boş bir PDF belgesi oluşturmayı, bir sayfa eklemeyi, başlık bölümünü yapılandırmayı, bir tablo oluşturmayı, tabloya satırlar ve hücreler eklemeyi ve son olarak PDF belgesini kaydetmeyi gösterir.

## Adım 1: Ortamı kurma

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 2: PDF Belgesi ve Sayfasını Oluşturma

 İlk adım, bir örnek oluşturmaktır`Document` sınıfını seçin ve belgeye bir sayfa ekleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Bir Belge nesnesi örneği oluşturun
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// PDF belgesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizi kaydetmek istediğiniz dizinin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 3: Başlık bölümünü yapılandırma

 Şimdi PDF belgesinin başlık bölümünü, bir örnek oluşturarak yapılandıracağız.`HeaderFooter` sınıf. İşte nasıl:

```csharp
// PDF dosyası için bir başlık bölümü oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Sayfanın başlık bölümünü tanımlayın
page. Header = header;

// Başlık bölümünün üst kenar boşluğunu ayarlayın
header. Margin. Top = 20;
```

## Adım 4: Tablonun oluşturulması

 Şimdi şunu kullanarak bir tablo oluşturacağız:`Table` sınıfını ekleyin ve başlık bölümünün paragraf koleksiyonuna ekleyin. İşte nasıl:

```csharp
// Bir Tablo nesnesi örneği oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tabloyu başlık bölümünün paragraf koleksiyonuna ekleyin
header.Paragraphs.Add(tab1);

// Tablonun sütunlarının genişliklerini tanımlayın
tab1.ColumnWidths = "60,300";
```

Yukarıdaki kod belirtilen genişlikte iki sütundan oluşan bir tablo oluşturur.

## Adım 5: Tabloya satırlar ve hücreler ekleyin

 Şimdi tabloya satırlar ve hücreler ekleyeceğiz`Row` sınıf ve`Cell` sınıf. İşte nasıl:

```csharp
// Tabloda bir satır oluşturun ve hücreler ekleyin
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// İlk satırın ilk hücresini birleştir
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Tabloda başka bir satır oluşturun ve bir resim içeren bir hücre ekleyin
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

## Adım 6: PDF Belgesini Kaydetme

Tablo başlık bölümüne eklendikten sonra PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// PDF dosyasını kaydedin
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizi kaydetmek istediğiniz dizinin gerçek yoluyla değiştirdiğinizden emin olun.

### .NET için Aspose.PDF kullanarak Tablo Başlık Alt Bilgi Bölümü için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucuyu çağırarak Belge örneğini örneklendirin
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// PDF belgesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//PDF dosyasının Başlık Bölümünü Oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// PDF dosyası için Garip Başlığı Ayarla
page.Header = header;

// Başlık bölümü için üst kenar boşluğunu ayarlayın
header.Margin.Top = 20;

// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// İstenilen bölümün paragraf koleksiyonuna tabloyu ekleyin
header.Paragraphs.Add(tab1);

// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Tablonun sütun genişlikleriyle ayarlayın
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// İlk satır için satır aralığı değerini 2 olarak ayarlayın
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Satır2 için arka plan rengini ayarlayın
row2.BackgroundColor = Color.White;

// Resmi tutan hücreyi ekleyin
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Resim genişliğini 60'a ayarlayın
img.FixWidth = 60;

// Resmi tablo hücresine ekle
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Metnin dikey hizalamasını ortaya hizalanmış olarak ayarla
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// PDF dosyasını kaydedin
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin başlık veya altbilgi bölümüne tablo eklemeyi öğrendiniz. Artık PDF belgelerinizde ek bilgiler görüntülemek için tablolar ekleyerek başlık ve altbilgilerinizi özelleştirebilirsiniz.

### Başlık ve altbilgi bölümündeki tablo için SSS

#### S: PDF belgesinin üstbilgi veya altbilgi bölümüne tablo eklemenin amacı nedir?

A: Bir PDF belgesinin üst bilgi veya alt bilgi bölümüne tablo eklemek, başlıklar, alt başlıklar, logolar veya belgenin her sayfasında tutarlı bir şekilde görünmesini istediğiniz diğer içerikler gibi yapılandırılmış ve düzenli bilgileri görüntülemenize olanak tanır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin üst bilgi veya alt bilgi bölümüne tablo eklenmesini nasıl sağlıyor?

A: Kod, boş bir PDF belgesi oluşturma, bir sayfa ekleme, başlık bölümünü yapılandırma, satırlar ve hücreler içeren bir tablo oluşturma ve son olarak PDF belgesini kaydetme sürecini gösterir. Sonuç, PDF belgesinin başlık bölümünde görüntülenen bir tablodur.

#### S: Tablo hücrelerinin görünümünü (kenarlıklar, arka plan rengi ve metin stili gibi) özelleştirebilir miyim?

C: Evet, hücre kenarlıkları, arka plan rengi, metin stili, yazı tipi, yazı tipi boyutu ve daha fazlası gibi özellikleri ayarlayarak tablo hücrelerinin görünümünü özelleştirebilirsiniz.

#### S: PDF belgesinin başlık bölümüne tablo nasıl eklenir?

A: Kod, tabloyu başlık bölümünün paragraf koleksiyonuna ekleyerek tablonun her sayfanın başlığında görüntülenmesini sağlar.

#### S: İhtiyaç duyduğumda tabloya daha fazla satır ve hücre ekleyebilir miyim?

 A: Kesinlikle, tabloya daha fazla satır ve hücre ekleyebilirsiniz.`Rows.Add()` Ve`Cells.Add()` Yöntemler. Bu, tablo içeriğini istediğiniz gibi yapılandırmanıza olanak tanır.

#### S: Tablo sütunlarının genişliğini ayarlamak mümkün müdür?
 A: Evet, tablo sütunlarının genişliğini kullanarak ayarlayabilirsiniz.`ColumnWidths` özellik. Bu, tablonun düzenini kontrol etmenizi sağlar.

#### S: Tablo içindeki birden fazla sütun veya satıra hücreleri nasıl yayabilirim?
 A: Hücreleri birden fazla sütuna yaymak için şunu kullanabilirsiniz:`ColSpan`ilgili hücrenin özelliği. Benzer şekilde, şunu kullanabilirsiniz`RowSpan` Hücreleri birden fazla satıra yayma özelliği.

#### S: PDF belgesinin hem üstbilgi hem de altbilgi bölümlerine tablo eklemek istersem ne olur?

 A: Hem üstbilgi hem de altbilgi bölümleri için benzer bir yaklaşımı takip edebilirsiniz. Basitçe bir`HeaderFooter` Altbilgi için örnek oluşturun, yapılandırın ve tabloyu paragraf koleksiyonuna ekleyin.

#### S: Tablo hücrelerinde resim kullanabilir miyim ve bu nasıl mümkün olur?

 A: Evet, tablo hücrelerine resim ekleyebilirsiniz. Kod örneği, bir hücreye resim eklemeyi, bir`Image` nesneyi, dosya yolunu ve boyutlarını ayarlayarak ve ardından onu bir hücrenin paragraflarına ekleyerek.

#### S: Tablonun PDF belgesindeki tüm sayfalarda tutarlı bir şekilde görünmesini nasıl sağlayabilirim?

 A: Tabloyu üstbilgi veya altbilgi bölümüne eklediğinizde`HeaderFooter` Örneğin, Aspose.PDF tablonun her sayfada tutarlı bir şekilde görünmesini sağlayarak tekdüze bir düzen sağlar.