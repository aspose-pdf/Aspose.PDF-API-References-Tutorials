---
title: Tablo Hücresine Resim Ekleme
linktitle: Tablo Hücresine Resim Ekleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir tablo hücresine resim ekleyin, PDF belgelerindeki resimlerin hassas bir şekilde işlenmesi için adım adım bir kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-tables/add-image-in-a-table-cell/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak bir tablo hücresine görüntü ekleme sürecinde size rehberlik edeceğiz. Sağlanan C# kaynak kodu, bu işlevin nasıl elde edileceğini gösterir. Aşağıda özetlenen adımları izleyerek, resimleri tablo hücrelerinize etkili bir şekilde dahil edebileceksiniz.

Koda dalmadan önce, Aspose.PDF for .NET kitaplığının kurulu olduğundan ve projenizde referans verildiğinden emin olun.

## 1. Adım: Belgeyi Ayarlama

 Başlamak için, yeni bir örnek oluşturmamız gerekiyor.`Document`Aspose.Pdf ad alanından sınıf. Bu sınıf bir PDF belgesini temsil eder.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesi örneği oluşturma
Document pdfDocument = new Document();
```

## 2. Adım: Sayfa Oluşturma

Ardından, PDF belgesine bir sayfa eklememiz gerekiyor. Sayfa, tablo ve diğer öğeler için bir kap görevi görür.

```csharp
// Pdf belgesinde bir sayfa oluşturun
Page sec1 = pdfDocument.Pages.Add();
```

## 3. Adım: Tablo Ekleme

 Bu adımda, somutlaştırarak bir tablo oluşturacağız.`Table` Aspose.Pdf ad alanından sınıf.

```csharp
// Bir tablo nesnesini somutlaştırın
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Adım 4: Varsayılan Hücre Kenarlığını Ayarlama

 Tutarlılığı sağlamak için, kullanarak varsayılan bir hücre sınırı ayarlayabiliriz.`DefaultCellBorder` tablonun özelliği`BorderInfo` nesne.

```csharp
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Adım 5: Sütun Genişliklerini Ayarlama

 Tablodaki her sütunun genişliğini tanımlamak için`ColumnWidths` mülk. Genişlikleri, boşlukla ayrılmış değerler içeren bir dize olarak belirtin.

```csharp
// Tablonun sütun genişlikleriyle ayarla
tab1.ColumnWidths = "100 100 120";
```

## Adım 6: Tablo Hücresine Görüntü Ekleme

Şimdi heyecan verici kısım geliyor, bir tablo hücresine resim eklemek. Bunu yapmak için şu alt adımları izleyeceğiz:

## Adım 6.1: Bir Görüntü Nesnesi Oluşturma

 örneğini oluşturun`Image` Aspose.Pdf ad alanından sınıf. Yı kur`File` özelliğini eklemek istediğiniz resim dosyasının yoluna ekleyin.

```csharp
// Bir Görüntü nesnesi oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Adım 6.2: Satır ve Hücre Oluşturma

Resmi tabloya eklemek için öncelikle bir satır ve gerekli hücreleri oluşturmamız gerekiyor.

```csharp
// Tabloda bir satır oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Satıra bir metin hücresi ekleyin
row1.Cells.Add("Sample text in cell");

// Resmi tutan hücreyi ekleyin
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Adım 6.3: Görüntüyü Tablo Hücresine Ekleme

Son olarak görüntüyü hücre içinde paragraf olarak ekleyerek tablo hücresine ekleyebiliriz.

```csharp
// Resmi tablo hücresine ekleyin
cell2.Paragraphs.Add(img);
```

## Adım 6.4: Ek Hücreler Ekleme

Görüntü hücresini ekledikten sonra gerekirse satıra daha fazla hücre ekleyebiliriz.

```csharp
// Satıra başka bir hücre ekle
row1.Cells.Add("Previous cell with image");

// Üçüncü hücrenin dikey hizalamasını ayarlayın
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## 7. Adım: Belgeyi Kaydetme

 Son olarak, değiştirilmiş belgeyi kullanarak belirli bir konuma kaydedebiliriz.`Save` yöntem.

```csharp
// Belgeyi Kaydet
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Tebrikler! Aspose.PDF for .NET kullanarak bir tablo hücresine nasıl resim ekleneceğini başarıyla öğrendiniz. Daha fazla özelleştirme seçeneğini keşfetmekten ve bu işlevi projelerinize entegre etmekten çekinmeyin.

### Aspose.PDF for .NET kullanarak bir tablo hücresine görüntü eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesi örneği oluşturma
Document pdfDocument = new Document();
// Pdf belgesinde bir sayfa oluşturun
Page sec1 = pdfDocument.Pages.Add();
// Bir tablo nesnesini somutlaştırın
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//İstenilen sayfanın paragraf koleksiyonuna tablo ekleme
sec1.Paragraphs.Add(tab1);
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Tablonun sütun genişlikleriyle ayarla
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Resmi tutan hücreyi ekleyin
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Resmi tablo hücresine ekleyin
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Belgeyi Kaydet
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir tablo hücresine nasıl resim ekleneceğine dair adım adım bir kılavuz ele aldık. Belgeyi ayarlayarak, bir sayfa oluşturarak ve bir tablo ekleyerek başladık. Ardından, varsayılan hücre kenarlığını ve sütun genişliklerini ayarlıyoruz. Bir tablo hücresine nasıl resim ekleneceğini ve hücrenin dikey hizalamasının nasıl ayarlanacağını gösterdik. Son olarak, değiştirilen belgeyi kaydettik. Bu adımları izleyerek PDF belgelerinizi tablo hücrelerindeki resimlerle verimli bir şekilde geliştirebilirsiniz.