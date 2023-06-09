---
title: Pencereye Otomatik Sığdır
linktitle: Pencereye Otomatik Sığdır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'i kullanmak ve PDF oluşturmada pencereye otomatik sığdırmak için adım adım kılavuz.
type: docs
weight: 50
url: /tr/net/programming-with-tables/auto-fit-to-window/
---

Aşağıdaki makale, sağlanan C# kaynak kodunun Aspose.PDF kitaplığını .NET kullanarak Otomatik Pencereye Sığdır işlevine ulaşmak için nasıl kullanılacağına ilişkin adım adım bir kılavuzdur. Pencereye Otomatik Sığdır işlevi, görüntüleme penceresine uyarlanmış bir düzen ile PDF dosyaları oluşturmanıza olanak tanır. Bu özellik, özellikle PDF belgenizin kullanıcı tarafından kullanılan PDF okuyucu penceresinin boyutuna otomatik olarak ayarlanmasını istediğinizde kullanışlıdır.

## 1. Adım: Ortamı Kurma

Başlamadan önce makinenize Aspose.PDF for .NET kütüphanesini kurmanız gerekir. Ayrıca gerekli ad alanlarını projenize aktardığınızdan emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir PDF Belgesi Oluşturma

 Başlamak için bir oluşturmanız gerekir`Document` varsayılan yapıcısını çağırarak nesne.

```csharp
Document doc = new Document();
```

 Ardından, içinde bir bölüm oluşturun.`Pdf` nesne.

```csharp
Page sec1 = doc.Pages.Add();
```

## Adım 3: Belgeye Tablo Ekleme

 Bu adımda, PDF belgemize bir tablo ekleyeceğiz. İlk önce bir oluştur`Table` nesne.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Ardından, tabloyu bölümün paragraf koleksiyonuna ekleyin.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  4. Adım: Tablo Görünümünü Özelleştirme

Hücre sınırları ve kenar boşluğu gibi özellikleri ayarlayarak tablonun görünümünü özelleştirebilirsiniz.

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

Şimdi tablomuza satırlar ve hücreler ekleyelim. Bir satır oluşturarak ve bu satıra hücreler ekleyerek başlayın.

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

## 5. Adım: Belgeyi Kaydetme

Son olarak, çıktı dosyası yolunu belirtin ve belgeyi kaydedin.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Otomatik Pencereye Sığdır için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak Pdf nesnesini başlatın
Document doc = new Document();
// Pdf nesnesinde bölümü oluşturun
Page sec1 = doc.Pages.Add();

// Bir tablo nesnesini somutlaştırın
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
sec1.Paragraphs.Add(tab1);

// Tablonun sütun genişlikleriyle ayarla
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Başka bir özelleştirilmiş BorderInfo nesnesi kullanarak tablo kenarlığını ayarlayın
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

Bu eğitimde, Pencereye Otomatik Sığdır özelliğiyle bir PDF dosyası oluşturmak için Aspose.PDF for .NET'i nasıl kullanacağımızı öğrendik. Bu özellik, PDF belgenizin otomatik olarak görüntüleme penceresinin boyutuna göre ayarlanmasını istediğinizde son derece kullanışlıdır. Aspose.PDF for .NET, PDF dosyalarını oluşturmak ve değiştirmek için birçok başka güçlü özellik sunar. Tüm yeteneklerini keşfetmek için bu kitaplığı daha fazla keşfetmenizi tavsiye ederim.