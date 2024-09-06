---
title: Tablo Hücresine Resim Ekle
linktitle: Tablo Hücresine Resim Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir tablo hücresine resim ekleyin. PDF belgelerindeki resimlerin hassas bir şekilde işlenmesi için adım adım bir kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-tables/add-image-in-a-table-cell/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir tablo hücresine resim ekleme sürecinde size rehberlik edeceğiz. Sağlanan C# kaynak kodu bu işlevselliğin nasıl elde edileceğini gösterir. Aşağıda özetlenen adımları izleyerek, resimleri tablo hücrelerinize etkili bir şekilde dahil edebileceksiniz.

Koda dalmadan önce, Aspose.PDF for .NET kütüphanesinin projenizde yüklü olduğundan ve referans verildiğinden emin olun.

## Adım 1: Belgeyi Ayarlama

 Başlamak için, yeni bir örnek oluşturmamız gerekiyor`Document` Aspose.Pdf ad alanından sınıf. Bu sınıf bir PDF belgesini temsil eder.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Bir Belge nesnesi örneği oluşturun
Document pdfDocument = new Document();
```

## Adım 2: Bir Sayfa Oluşturma

Sonra, PDF belgesine bir sayfa eklememiz gerekiyor. Bir sayfa, tablo ve diğer öğeler için bir kapsayıcı görevi görür.

```csharp
// PDF belgesinde bir sayfa oluşturun
Page sec1 = pdfDocument.Pages.Add();
```

## Adım 3: Tablo Ekleme

 Bu adımda, örnek oluşturarak bir tablo oluşturacağız`Table` Aspose.Pdf ad alanından sınıf.

```csharp
// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Adım 4: Varsayılan Hücre Kenarlığını Ayarlama

 Tutarlılığı sağlamak için, varsayılan bir hücre kenarlığı ayarlayabiliriz`DefaultCellBorder`tablonun özelliği`BorderInfo` nesne.

```csharp
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Adım 5: Sütun Genişliklerini Ayarlama

 Tablodaki her sütunun genişliğini tanımlamak için şunu ayarlayabiliriz:`ColumnWidths` özellik. Genişlikleri boşluklarla ayrılmış değerler içeren bir dize olarak belirtin.

```csharp
// Tablonun sütun genişlikleriyle ayarlayın
tab1.ColumnWidths = "100 100 120";
```

## Adım 6: Bir Tablo Hücresine Resim Ekleme

Şimdi heyecan verici kısma geliyoruz, bir tablo hücresine resim ekleme. Bunu yapmak için şu alt adımları takip edeceğiz:

## Adım 6.1: Bir Görüntü Nesnesi Oluşturma

 Bir örneğini oluşturun`Image` Aspose.Pdf ad alanından sınıf.`File` Eklemek istediğiniz resim dosyasının yoluna ait özellik.

```csharp
// Bir Görüntü nesnesi oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Adım 6.2: Satır ve Hücreler Oluşturma

Resmi tabloya eklemek için öncelikle bir satır ve gerekli hücreleri oluşturmamız gerekiyor.

```csharp
// Tabloda bir satır oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Satıra bir metin hücresi ekle
row1.Cells.Add("Sample text in cell");

// Resmi tutan hücreyi ekleyin
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Adım 6.3: Resmi Tablo Hücresine Ekleme

Son olarak, resmi hücrenin içine paragraf olarak ekleyerek tablo hücresine ekleyebiliriz.

```csharp
// Resmi tablo hücresine ekle
cell2.Paragraphs.Add(img);
```

## Adım 6.4: Ek Hücreler Ekleme

Resim hücresini ekledikten sonra, ihtiyaç halinde satıra daha fazla hücre ekleyebiliriz.

```csharp
//Satıra başka bir hücre ekle
row1.Cells.Add("Previous cell with image");

// Üçüncü hücrenin dikey hizalamasını ayarlayın
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Adım 7: Belgeyi Kaydetme

 Son olarak, değiştirilen belgeyi belirtilen bir konuma şu şekilde kaydedebiliriz:`Save` Yöntem.

```csharp
// Belgeyi Kaydet
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Tebrikler! Aspose.PDF for .NET kullanarak bir tablo hücresine resim eklemeyi başarıyla öğrendiniz. Daha fazla özelleştirme seçeneğini keşfetmekten ve bu işlevselliği projelerinize entegre etmekten çekinmeyin.

### .NET için Aspose.PDF kullanarak bir tablo hücresine resim eklemek için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Bir Belge nesnesi örneği oluşturun
Document pdfDocument = new Document();
// PDF belgesinde bir sayfa oluşturun
Page sec1 = pdfDocument.Pages.Add();
// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// İstenilen sayfanın paragraf koleksiyonuna tabloyu ekleyin
sec1.Paragraphs.Add(tab1);
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Tablonun sütun genişlikleriyle ayarlayın
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Resmi tutan hücreyi ekleyin
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Resmi tablo hücresine ekle
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Belgeyi Kaydet
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir tablo hücresine resim ekleme konusunda adım adım bir kılavuz ele aldık. Belgeyi ayarlayarak, bir sayfa oluşturarak ve bir tablo ekleyerek başladık. Ardından, varsayılan hücre kenarlığını ve sütun genişliklerini ayarladık. Bir tablo hücresine resim eklemeyi ve hücrenin dikey hizalamasını ayarlamayı gösterdik. Son olarak, değiştirilen belgeyi kaydettik. Bu adımları izleyerek, PDF belgelerinizi tablo hücrelerindeki resimlerle verimli bir şekilde geliştirebilirsiniz.

### SSS

#### S: Aspose.PDF for .NET kullanarak aynı tablo içindeki farklı hücrelere birden fazla resim ekleyebilir miyim?

A: Evet, Aspose.PDF for .NET kullanarak aynı tablo içindeki farklı hücrelere birden fazla resim ekleyebilirsiniz. Tabloya eklemek istediğiniz her resim için eğitimde gösterilen aynı işlemi takip etmeniz yeterlidir.

#### S: Resim boyutunu ve tablo hücresi içindeki konumunu özelleştirebilir miyim?

 A: Evet, özellikleri ayarlayarak resim boyutunu ve tablo hücresi içindeki konumunu özelleştirebilirsiniz.`Image`nesne. Görüntünün genişliğini ve yüksekliğini, ayrıca hücre içindeki hizalamayı ayarlayabilirsiniz.

#### S: Satır ve sütun sayısı dinamik olan bir tabloya resim ekleyebilir miyim?

A: Evet, dinamik satır ve sütun sayısına sahip bir tabloya resim ekleyebilirsiniz. Aspose.PDF for .NET, farklı boyutlarda tablolar oluşturmada esneklik sağlar. Gerektiğinde satır ve hücre ekleyebilir ve ardından belirli hücrelere buna göre resim ekleyebilirsiniz.

#### S: Aspose.PDF for .NET tarafından tablo hücrelerine resim eklemek için hangi resim formatları destekleniyor?

A: Aspose.PDF for .NET, JPEG, PNG, GIF, BMP ve TIFF dahil olmak üzere çok çeşitli resim formatlarını destekler. Bu formatlardan herhangi birinin resimlerini kullanarak tablo hücrelerine ekleyebilirsiniz.

#### S: Mevcut bir PDF belgesindeki tablolara resim ekleyebilir miyim?

A: Evet, Aspose.PDF for .NET kullanarak mevcut bir PDF belgesindeki tablolara resim ekleyebilirsiniz. Sadece mevcut belgeyi yükleyin ve öğreticide gösterildiği gibi tabloya resim eklemek için aynı adımları izleyin.