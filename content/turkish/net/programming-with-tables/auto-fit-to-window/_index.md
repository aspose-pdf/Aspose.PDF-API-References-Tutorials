---
title: Pencereye Otomatik Sığdır
linktitle: Pencereye Otomatik Sığdır
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanmak ve PDF oluşturma sırasında pencereye otomatik uyum sağlamak için adım adım kılavuz.
type: docs
weight: 50
url: /tr/net/programming-with-tables/auto-fit-to-window/
---
Aşağıdaki makale, .NET için Aspose.PDF kütüphanesini kullanarak Pencereye Otomatik Sığdır işlevini elde etmek için sağlanan C# kaynak kodunun nasıl kullanılacağını açıklayan adım adım bir kılavuzdur. Pencereye Otomatik Sığdır işlevi, görüntüleme penceresine uyarlanmış bir düzene sahip PDF dosyaları oluşturmanıza olanak tanır. Bu özellik özellikle PDF belgenizin, kullanıcı tarafından kullanılan PDF okuyucu penceresinin boyutuna otomatik olarak ayarlanmasını istediğinizde kullanışlıdır.

## 1. Adım: Ortamı Ayarlama

Başlamadan önce, Aspose.PDF kütüphanesini .NET için makinenize kurmanız gerekir. Ayrıca gerekli ad alanlarını projenize aktardığınızdan emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesi Oluşturma

 Başlamak için bir oluşturmanız gerekir`Document` nesnenin varsayılan yapıcısını çağırarak.

```csharp
Document doc = new Document();
```

 Daha sonra, bir bölüm oluşturun.`Pdf` nesne.

```csharp
Page sec1 = doc.Pages.Add();
```

## Adım 3: Belgeye Tablo Ekleme

 Bu adımda PDF belgemize bir tablo ekleyeceğiz. İlk önce bir oluştur`Table` nesne.

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

Şimdi tablomuza satır ve hücre ekleyelim. Bir satır oluşturup bu satıra hücreler ekleyerek başlayın.

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

Son olarak çıktı dosyası yolunu belirtin ve belgeyi kaydedin.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Pencereye Otomatik Sığdır için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş yapıcısını çağırarak Pdf nesnesini başlatın
Document doc = new Document();
// Pdf nesnesinde bölümü oluşturun
Page sec1 = doc.Pages.Add();

// Bir tablo nesnesinin örneğini oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
sec1.Paragraphs.Add(tab1);

// Tablonun sütun genişliklerine göre ayarlama
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlama
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Başka bir özelleştirilmiş BorderInfo nesnesini kullanarak tablo kenarlığını ayarlayın
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// MarginInfo nesnesi oluşturun ve sol, alt, sağ ve üst kenar boşluklarını ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Varsayılan hücre dolgusunu MarginInfo nesnesine ayarlayın
tab1.DefaultCellPadding = margin;

// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
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

Bu eğitimde, Pencereye Otomatik Sığdır özelliğiyle bir PDF dosyası oluşturmak için Aspose.PDF for .NET'in nasıl kullanılacağını öğrendik. Bu özellik, PDF belgenizin görüntüleme penceresinin boyutuna otomatik olarak ayarlanmasını istediğinizde son derece kullanışlıdır. Aspose.PDF for .NET, PDF dosyalarını oluşturmak ve değiştirmek için birçok başka güçlü özellik sunar. Tüm yeteneklerini keşfetmek için bu kütüphaneyi daha fazla keşfetmenizi öneririm.

### SSS'ler

#### S: PDF oluşturmada Pencereye Otomatik Sığdır özelliğinin amacı nedir?

C: PDF oluşturmadaki Pencereye Otomatik Sığdır özelliği, PDF belgesinin düzeninin, kullanıcı tarafından kullanılan PDF okuyucu penceresinin boyutuna otomatik olarak ayarlanmasını sağlar. Bu, daha iyi görüntülemeye olanak tanır ve içeriğin mevcut görüntüleme alanına mükemmel şekilde sığmasını sağlar.

#### S: Yazı tipi boyutu ve renkleri gibi tablonun görünümünü özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak PDF belgesindeki tablonun görünümünü özelleştirebilirsiniz. Sağlanan kod parçacığı hücre sınırları, kenar boşlukları ve sütun genişlikleri gibi özelliklerin nasıl ayarlanacağını gösterir. Tablonun ve içeriğinin yazı tipi boyutunu, renklerini ve diğer stil özelliklerini daha da özelleştirebilirsiniz.

#### S: Aspose.PDF for .NET'i C# projeme nasıl entegre edebilirim?

C: Aspose.PDF for .NET'i C# projenizde kullanmak için öncelikle Aspose.PDF for .NET kütüphanesini makinenize yüklemeniz gerekir. Daha sonra C# projenizdeki kütüphaneye bir referans ekleyebilirsiniz. Son olarak Aspose.PDF for .NET tarafından sağlanan sınıflara ve yöntemlere erişmek için gerekli ad alanlarını içe aktarın.

#### S: Aspose.PDF for .NET, .NET Core uygulamalarıyla uyumlu mudur?

C: Evet, Aspose.PDF for .NET, .NET Core uygulamalarıyla uyumludur. .NET Framework, .NET Core ve .NET 5.0+ dahil olmak üzere çeşitli .NET platformlarını destekler.

#### S: PDF belgesine daha fazla tablo ekleyebilir miyim?

C: Evet, kod parçacığında gösterilene benzer adımları izleyerek bir PDF belgesine birden fazla tablo ekleyebilirsiniz. Basitçe yeni örneklerini oluşturun`Aspose.Pdf.Table` sınıfa ekleyin ve bunları PDF belgesinin farklı bölümlerine veya sayfalarına ekleyin.