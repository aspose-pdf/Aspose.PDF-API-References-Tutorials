---
title: Tablo Hücresine Resim Ekleme
linktitle: Tablo Hücresine Resim Ekleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile tablo hücresine bir görüntü ekleyin; PDF belgelerindeki görüntülerin hassas şekilde işlenmesi için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-tables/add-image-in-a-table-cell/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir tablo hücresine görüntü ekleme sürecinde size rehberlik edeceğiz. Sağlanan C# kaynak kodu, bu işlevselliğe nasıl ulaşılacağını gösterir. Aşağıda özetlenen adımları takip ederek resimleri tablo hücrelerinize etkili bir şekilde dahil edebileceksiniz.

Kodun ayrıntılarına girmeden önce Aspose.PDF for .NET kütüphanesinin kurulu olduğundan ve projenizde referans verildiğinden emin olun.

## 1. Adım: Belgeyi Ayarlama

 Başlamak için yeni bir örneğini oluşturmamız gerekiyor.`Document` Aspose.Pdf ad alanından sınıf. Bu sınıf bir PDF belgesini temsil eder.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Bir Belge nesnesinin örneğini oluşturma
Document pdfDocument = new Document();
```

## Adım 2: Sayfa Oluşturma

Daha sonra PDF belgesine bir sayfa eklememiz gerekiyor. Sayfa, tablo ve diğer öğeler için bir kap görevi görür.

```csharp
// Pdf belgesinde bir sayfa oluşturun
Page sec1 = pdfDocument.Pages.Add();
```

## Adım 3: Tablo Ekleme

 Bu adımda, örnekleyerek bir tablo oluşturacağız.`Table` Aspose.Pdf ad alanından sınıf.

```csharp
// Bir tablo nesnesinin örneğini oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Adım 4: Varsayılan Hücre Sınırını Ayarlama

 Tutarlılığı sağlamak için varsayılan hücre kenarlığını aşağıdaki komutu kullanarak ayarlayabiliriz:`DefaultCellBorder`tablonun özelliği`BorderInfo` nesne.

```csharp
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlama
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Adım 5: Sütun Genişliklerini Ayarlama

 Tablodaki her bir sütunun genişliğini tanımlamak için`ColumnWidths` mülk. Genişlikleri boşlukla ayrılmış değerler içeren bir dize olarak belirtin.

```csharp
// Tablonun sütun genişliklerine göre ayarlama
tab1.ColumnWidths = "100 100 120";
```

## Adım 6: Tablo Hücresine Görüntü Ekleme

Şimdi heyecan verici kısım geliyor: tablo hücresine resim ekleme. Bunu yapmak için şu alt adımları izleyeceğiz:

## Adım 6.1: Görüntü Nesnesi Oluşturma

 Bir örneğini oluşturun`Image` Aspose.Pdf ad alanından sınıf. Yı kur`File` özelliğini eklemek istediğiniz görüntü dosyasının yoluna ekleyin.

```csharp
// Bir Görüntü nesnesi oluşturma
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Adım 6.2: Satır ve Hücre Oluşturma

Görseli tabloya eklemek için öncelikle bir satır ve gerekli hücreleri oluşturmamız gerekiyor.

```csharp
// Tabloda bir satır oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Satıra bir metin hücresi ekleme
row1.Cells.Add("Sample text in cell");

// Resmin bulunduğu hücreyi ekleyin
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Adım 6.3: Görüntüyü Tablo Hücresine Ekleme

Son olarak görseli hücre içerisinde paragraf olarak ekleyerek tablo hücresine ekleyebiliriz.

```csharp
// Resmi tablo hücresine ekleyin
cell2.Paragraphs.Add(img);
```

## Adım 6.4: Ek Hücre Ekleme

Görüntü hücresini ekledikten sonra gerekirse satıra daha fazla hücre ekleyebiliriz.

```csharp
//Satıra başka bir hücre ekle
row1.Cells.Add("Previous cell with image");

// Üçüncü hücrenin dikey hizalamasını ayarlayın
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Adım 7: Belgeyi Kaydetme

 Son olarak, değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen bir konuma kaydedebiliriz:`Save` yöntem.

```csharp
// Belgeyi Kaydet
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Tebrikler! Aspose.PDF for .NET kullanarak bir tablo hücresine nasıl resim ekleyeceğinizi başarıyla öğrendiniz. Daha fazla özelleştirme seçeneğini keşfetmekten ve bu işlevselliği projelerinize entegre etmekten çekinmeyin.

### Aspose.PDF for .NET kullanarak tablo hücresine resim eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Bir Belge nesnesinin örneğini oluşturma
Document pdfDocument = new Document();
// Pdf belgesinde bir sayfa oluşturun
Page sec1 = pdfDocument.Pages.Add();
// Bir tablo nesnesinin örneğini oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tabloyu istediğiniz sayfanın paragraf koleksiyonuna ekleyin
sec1.Paragraphs.Add(tab1);
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlama
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Tablonun sütun genişliklerine göre ayarlama
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Resmin bulunduğu hücreyi ekleyin
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Resmi tablo hücresine ekleyin
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Belgeyi Kaydet
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir tablo hücresine nasıl resim ekleneceğine dair adım adım bir kılavuz ele aldık. Belgeyi ayarlayarak, bir sayfa oluşturarak ve bir tablo ekleyerek başladık. Daha sonra varsayılan hücre kenarlığını ve sütun genişliklerini ayarlıyoruz. Tablo hücresine nasıl resim ekleneceğini ve hücrenin dikey hizasının nasıl ayarlanacağını gösterdik. Son olarak değiştirilen belgeyi kaydettik. Bu adımları izleyerek PDF belgelerinizi tablo hücrelerindeki resimlerle verimli bir şekilde geliştirebilirsiniz.

### SSS'ler

#### S: Aspose.PDF for .NET'i kullanarak aynı tablodaki farklı hücrelere birden fazla görüntü ekleyebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak aynı tablodaki farklı hücrelere birden fazla görüntü ekleyebilirsiniz. Tabloya eklemek istediğiniz her görüntü için eğitimde gösterilen işlemin aynısını uygulamanız yeterlidir.

#### S: Tablo hücresindeki görüntü boyutunu ve konumunu özelleştirebilir miyim?

 C: Evet, tablo hücresinin özelliklerini ayarlayarak tablo hücresi içindeki görüntü boyutunu ve konumunu özelleştirebilirsiniz.`Image`nesne. Görüntünün genişliğini ve yüksekliğini ve ayrıca hücre içindeki hizalamayı ayarlayabilirsiniz.

#### S: Dinamik sayıda satır ve sütuna sahip bir tabloya resim ekleyebilir miyim?

C: Evet, dinamik sayıda satır ve sütun içeren bir tabloya görseller ekleyebilirsiniz. Aspose.PDF for .NET, farklı boyutlarda tablolar oluşturmada esneklik sağlar. Gerektiğinde satır ve hücre ekleyebilir ve ardından belirli hücrelere uygun şekilde görseller ekleyebilirsiniz.

#### S: Tablo hücrelerine resim eklemek için Aspose.PDF for .NET hangi resim formatlarını destekliyor?

C: Aspose.PDF for .NET, JPEG, PNG, GIF, BMP ve TIFF dahil çok çeşitli görüntü formatlarını destekler. Tablo hücrelerine eklemek için bu formatlardan herhangi birinin görsellerini kullanabilirsiniz.

#### S: Mevcut bir PDF belgesindeki tablolara resim ekleyebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak mevcut bir PDF belgesindeki tablolara görüntüler ekleyebilirsiniz. Mevcut belgeyi yükleyin ve öğreticide gösterildiği gibi tabloya resim eklemek için aynı adımları izleyin.