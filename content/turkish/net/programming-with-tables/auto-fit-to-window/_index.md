---
title: Pencereye Otomatik Uyum
linktitle: Pencereye Otomatik Uyum
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF'i kullanma ve PDF oluşturmada pencereye otomatik sığdırma özelliğini elde etme konusunda adım adım kılavuz.
type: docs
weight: 50
url: /tr/net/programming-with-tables/auto-fit-to-window/
---
Aşağıdaki makale, .NET için Aspose.PDF kütüphanesini kullanarak Auto Fit To Window işlevselliğini elde etmek için sağlanan C# kaynak kodunun nasıl kullanılacağına dair adım adım bir kılavuzdur. Auto Fit To Window işlevi, görüntüleme penceresine uyarlanmış bir düzene sahip PDF dosyaları oluşturmanıza olanak tanır. Bu özellik, PDF belgenizin kullanıcı tarafından kullanılan PDF okuyucu penceresinin boyutuna otomatik olarak ayarlanmasını istediğinizde özellikle yararlıdır.

## Adım 1: Ortamı Kurma

Başlamadan önce, makinenize .NET için Aspose.PDF kütüphanesini yüklemeniz gerekir. Ayrıca projenize gerekli ad alanlarını içe aktardığınızdan emin olun.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesi Oluşturma

 Başlamak için bir tane oluşturmanız gerekir`Document` nesneyi varsayılan kurucusunu çağırarak çağırır.

```csharp
Document doc = new Document();
```

 Daha sonra, bir bölüm oluşturun`Pdf` nesne.

```csharp
Page sec1 = doc.Pages.Add();
```

## Adım 3: Belgeye Tablo Ekleme

 Bu adımda PDF belgemize bir tablo ekleyeceğiz. İlk önce bir`Table` nesne.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Daha sonra tabloyu bölümün paragraf koleksiyonuna ekleyin.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Adım 4: Tablo Görünümünü Özelleştirme

Hücre kenarlıkları ve kenar boşluğu gibi özellikleri ayarlayarak tablonun görünümünü özelleştirebilirsiniz.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Adım 4: Tabloya Satır ve Hücre Ekleme

Şimdi tablomuza satırlar ve hücreler ekleyelim. Bir satır oluşturarak ve bu satıra hücreler ekleyerek başlayalım.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Adım 5: Belgeyi Kaydetme

Son olarak çıktı dosya yolunu belirtin ve belgeyi kaydedin.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak Pencereye Otomatik Sığdırma için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak Pdf nesnesini örneklendirin
Document doc = new Document();
// Pdf nesnesinde bölümü oluşturun
Page sec1 = doc.Pages.Add();

// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// İstenilen bölümün paragraf koleksiyonuna tabloyu ekleyin
sec1.Paragraphs.Add(tab1);

// Tablonun sütun genişlikleriyle ayarlayın
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Başka bir özelleştirilmiş BorderInfo nesnesini kullanarak tablo kenarlığını ayarlayın
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// MarginInfo nesnesini oluşturun ve sol, alt, sağ ve üst kenar boşluklarını ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Varsayılan hücre dolgusunu MarginInfo nesnesine ayarlayın
tab1.DefaultCellPadding = margin;

//Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Tablo nesnesini içeren güncellenmiş belgeyi kaydet
doc.Save(dataDir);
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET'i kullanarak Auto Fit To Window özelliğiyle bir PDF dosyası oluşturmayı öğrendik. Bu özellik, PDF belgenizin görüntüleme penceresinin boyutuna otomatik olarak ayarlanmasını istediğinizde son derece kullanışlıdır. Aspose.PDF for .NET, PDF dosyaları oluşturmak ve düzenlemek için birçok başka güçlü özellik sunar. Tüm yeteneklerini keşfetmek için bu kütüphaneyi daha fazla incelemenizi öneririm.

### SSS

#### S: PDF oluşturmada Pencereye Otomatik Sığdır özelliğinin amacı nedir?

A: PDF oluşturmadaki Pencereye Otomatik Sığdır özelliği, PDF belgesinin düzeninin kullanıcı tarafından kullanılan PDF okuyucu penceresinin boyutuna otomatik olarak ayarlanmasını sağlar. Bu, daha iyi görüntüleme sağlar ve içeriğin mevcut görüntüleme alanına mükemmel şekilde uymasını sağlar.

#### S: Tablonun görünümünü, yazı tipi boyutunu ve renkleri gibi şeyleri özelleştirebilir miyim?

A: Evet, .NET için Aspose.PDF kullanarak PDF belgesindeki tablonun görünümünü özelleştirebilirsiniz. Sağlanan kod parçacığı, hücre sınırları, kenar boşlukları ve sütun genişlikleri gibi özelliklerin nasıl ayarlanacağını gösterir. Tablonun ve içeriğinin yazı tipi boyutunu, renklerini ve diğer stil özelliklerini daha da özelleştirebilirsiniz.

#### S: Aspose.PDF for .NET'i C# projeme nasıl entegre edebilirim?

A: Aspose.PDF for .NET'i C# projenizde kullanmak için öncelikle makinenize Aspose.PDF for .NET kütüphanesini yüklemeniz gerekir. Daha sonra, C# projenize kütüphaneye bir referans ekleyebilirsiniz. Son olarak, Aspose.PDF for .NET tarafından sağlanan sınıflara ve yöntemlere erişmek için gerekli ad alanlarını içe aktarın.

#### S: Aspose.PDF for .NET, .NET Core uygulamalarıyla uyumlu mudur?

A: Evet, Aspose.PDF for .NET, .NET Core uygulamalarıyla uyumludur. .NET Framework, .NET Core ve .NET 5.0+ dahil olmak üzere çeşitli .NET platformlarını destekler.

#### S: PDF belgesine daha fazla tablo ekleyebilir miyim?

A: Evet, kod parçacığında gösterildiği gibi benzer adımları izleyerek bir PDF belgesine birden fazla tablo ekleyebilirsiniz. Basitçe yeni örnekler oluşturun`Aspose.Pdf.Table` sınıfına ekleyin ve bunları PDF belgesinin farklı bölümlerine veya sayfalarına ekleyin.