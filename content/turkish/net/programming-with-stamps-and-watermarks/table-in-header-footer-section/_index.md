---
title: Üstbilgi Altbilgi Bölümündeki Tablo
linktitle: Üstbilgi Altbilgi Bölümündeki Tablo
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile bir PDF belgesinin üstbilgi/altbilgi bölümüne nasıl tablo ekleyeceğinizi öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinin üstbilgi veya altbilgi bölümüne nasıl tablo ekleyeceğiniz konusunda size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodu size boş bir PDF belgesinin nasıl oluşturulacağını, sayfa ekleneceğini, başlık bölümünün nasıl yapılandırılacağını, tablo oluşturulacağını, tabloya satır ve hücrelerin nasıl ekleneceğini ve son olarak PDF belgesinin nasıl kaydedileceğini gösterir.

## 1. Adım: Ortamı ayarlama

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.

## Adım 2: PDF Belgesini ve Sayfasını Oluşturma

 İlk adım, bir örneğini oluşturmaktır.`Document` sınıfa gidin ve belgeye bir sayfa ekleyin. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Bir Belge nesnesinin örneğini oluşturma
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// PDF belgesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

"BELGELERİNİZ DİZİNİ"ni, PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Başlık bölümünü yapılandırma

 Şimdi PDF belgesinin başlık bölümünü, örneğini oluşturarak yapılandıracağız.`HeaderFooter` sınıf. İşte nasıl:

```csharp
// PDF dosyası için bir başlık bölümü oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Sayfanın başlık bölümünü tanımlayın
page. Header = header;

// Başlık bölümünün üst kenar boşluğunu ayarlayın
header. Margin. Top = 20;
```

## 4. Adım: Tabloyu oluşturma

 Şimdi bu komutu kullanarak bir tablo oluşturacağız.`Table` sınıfını seçin ve bunu başlık bölümünün paragraf koleksiyonuna ekleyin. İşte nasıl:

```csharp
// Bir Tablo nesnesi örneği oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tabloyu başlık bölümünün paragraf koleksiyonuna ekleyin
header.Paragraphs.Add(tab1);

// Tablonun sütunlarının genişliklerini tanımlayın
tab1.ColumnWidths = "60,300";
```

Yukarıdaki kod, belirtilen genişlikte iki sütuna sahip bir tablo oluşturur.

## 5. Adım: Tabloya satır ve hücre ekleyin

 Şimdi tabloya satırları ve hücreleri kullanarak ekleyeceğiz.`Row` sınıf ve`Cell` sınıf. İşte nasıl:

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

## Adım 6: PDF Belgesini Kaydetme

Tablo başlık bölümüne eklendikten sonra PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// PDF dosyasını kaydedin
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

"BELGELERİNİZ DİZİNİ"ni, PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Üst Bilgi Alt Bilgi Bölümündeki Tablo için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş kurucuyu çağırarak Belge örneğini oluşturun
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Pdf belgesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// PDF dosyasının Başlık Bölümünü oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//PDF dosyası için Tek Başlığı Ayarlama
page.Header = header;

// Başlık bölümünün üst kenar boşluğunu ayarlayın
header.Margin.Top = 20;

// Bir tablo nesnesinin örneğini oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
header.Paragraphs.Add(tab1);

// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlama
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Tablonun sütun genişliklerine göre ayarlama
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// İlk satırın satır aralığı değerini 2 olarak ayarlayın
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Satır2 için arka plan rengini ayarlayın
row2.BackgroundColor = Color.White;

// Resmin bulunduğu hücreyi ekleyin
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin üstbilgi veya altbilgi bölümüne nasıl tablo ekleyeceğinizi öğrendiniz. Artık PDF belgelerinizde ek bilgiler görüntülemek için tablolar ekleyerek üstbilgilerinizi ve altbilgilerinizi özelleştirebilirsiniz.

### Üst bilgi alt bilgi bölümündeki tablo için SSS

#### S: PDF belgesinin üstbilgi veya altbilgi bölümüne tablo eklemenin amacı nedir?

C: Bir PDF belgesinin üstbilgi veya altbilgi bölümüne bir tablo eklemek, başlıklar, alt başlıklar, logolar gibi yapılandırılmış ve düzenli bilgileri veya belgenin her sayfasında tutarlı bir şekilde görünmesini istediğiniz diğer içerikleri görüntülemenize olanak tanır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin üstbilgi veya altbilgi bölümüne tablo eklenmesini nasıl sağlar?

C: Kod, boş bir PDF belgesi oluşturma, sayfa ekleme, başlık bölümünü yapılandırma, satırlar ve hücreler içeren bir tablo oluşturma ve son olarak PDF belgesini kaydetme sürecini gösterir. Sonuç, PDF belgesinin başlık bölümünde görüntülenen bir tablodur.

#### S: Tablo hücrelerinin kenarlıklar, arka plan rengi ve metin stili gibi görünümünü özelleştirebilir miyim?

C: Evet, hücre kenarlıkları, arka plan rengi, metin stili, yazı tipi, yazı tipi boyutu ve daha fazlası gibi özellikleri ayarlayarak tablo hücrelerinin görünümünü özelleştirebilirsiniz.

#### S: Tablo, PDF belgesinin başlık bölümüne nasıl eklenir?

C: Kod, tabloyu başlık bölümünün paragraf koleksiyonuna ekler, bu da tablonun her sayfanın başlığında görüntülenmesini sağlar.

#### S: Gerektiğinde tabloya daha fazla satır ve hücre ekleyebilir miyim?

 C: Kesinlikle, tabloya daha fazla satır ve hücre ekleyebilirsiniz.`Rows.Add()` Ve`Cells.Add()` yöntemler. Bu, tablo içeriğini istediğiniz gibi yapılandırmanıza olanak tanır.

#### S: Tablo sütunlarının genişliğini ayarlamak mümkün mü?
 C: Evet, tablo sütunlarının genişliğini aşağıdaki düğmeyi kullanarak ayarlayabilirsiniz:`ColumnWidths` mülk. Bu, tablonun düzenini kontrol etmenizi sağlar.

#### S: Hücreleri tablodaki birden çok sütuna veya satıra nasıl yayabilirim?
 C: Hücreleri birden çok sütuna yaymak için`ColSpan` karşılık gelen hücrenin özelliği. Benzer şekilde, şunları kullanabilirsiniz:`RowSpan` Hücreleri birden çok satıra yayma özelliği.

#### S: PDF belgesinin hem üstbilgi hem de altbilgi bölümlerine tablo eklemek istersem ne olur?

C: Hem üstbilgi hem de altbilgi bölümleri için benzer bir yaklaşım uygulayabilirsiniz. Basitçe bir`HeaderFooter` altbilgi örneğini yapılandırın ve tabloyu paragraf koleksiyonuna ekleyin.

#### S: Tablo hücrelerindeki görselleri kullanabilir miyim ve bu nasıl elde edilir?

 C: Evet, tablo hücrelerinin içine resim ekleyebilirsiniz. Kod örneği, bir hücreye bir resim oluşturarak bir resim eklemeyi gösterir.`Image` nesnesini seçin, dosya yolunu ve boyutlarını ayarlayın ve ardından onu bir hücrenin paragraflarına ekleyin.

#### S: Tablonun PDF belgesindeki tüm sayfalarda tutarlı bir şekilde görünmesini nasıl sağlayabilirim?

 C: Tabloyu üst bilgi veya alt bilgi bölümüne eklediğinizde`HeaderFooter` Örneğin Aspose.PDF, tablonun her sayfada tutarlı bir şekilde görünmesini sağlayarak tek tip bir düzen sağlar.