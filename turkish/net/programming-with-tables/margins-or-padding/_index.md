---
title: Kenar Boşlukları veya Dolgu
linktitle: Kenar Boşlukları veya Dolgu
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir tabloda kenar boşluklarını veya dolguyu nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 140
url: /tr/net/programming-with-tables/margins-or-padding/
---

Bu eğitimde, bir tabloda kenar boşluklarını veya dolguyu ayarlamak için Aspose.PDF for .NET'i kullanma sürecinde size adım adım rehberlik edeceğiz. C# kaynak kodunuzdaki bu işlevi anlamanıza ve uygulamanıza yardımcı olacak açıklamalar ve kod parçacıkları sağlayacağız.

## 1. Adım: Belge ve Sayfayı Ayarlama
Başlamak için, aşağıdaki kodu kullanarak belgeyi ve sayfayı ayarlamanız gerekir:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak Belge nesnesinin örneğini oluşturun
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 2. Adım: Tablo Oluşturma
Ardından, Aspose.Pdf.Table sınıfını kullanarak bir tablo nesnesi oluşturacağız:

```csharp
// Bir tablo nesnesini somutlaştırın
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tabloyu istenen bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(tab1);
```

## 3. Adım: Sütun Genişliklerini ve Varsayılan Hücre Kenarlığını Ayarlama
Tablonun sütun genişliklerini ve varsayılan hücre kenarlığını ayarlamak için aşağıdaki kodu kullanın:

```csharp
// Tablonun sütun genişliklerini ayarlayın
tab1. ColumnWidths = "50 50 50";
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Adım 4: Tablo Kenarlığını ve Hücre Dolgusunu Ayarlama
Tablo kenarlığını ve hücre dolgusunu ayarlamak için bir MarginInfo nesnesi oluşturun ve özelliklerini ayarlayın:

```csharp
// Bir MarginInfo nesnesi oluşturun ve sol, alt, sağ ve üst kenar boşluklarını ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Varsayılan hücre dolgusunu MarginInfo nesnesine ayarlayın
tab1. DefaultCellPadding = margin;

// Başka bir özelleştirilmiş BorderInfo nesnesi kullanarak tablo kenarlığını ayarlayın
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Adım 5: Satır ve Hücre Ekleme
Şimdi tabloya satırlar ve hücreler ekleyelim. Yeni bir satır oluşturacağız ve buna hücreler ekleyeceğiz:

```csharp
// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Adım 6: Hücrelere Metin Ekleme
Bir hücreye metin eklemek için bir TextFragment nesnesi oluşturun ve bunu istediğiniz hücreye ekleyin:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## 7. Adım: PDF'yi Kaydetme
PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// PDF'yi kaydet
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanan Margins Or Padding için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak Belge nesnesini başlatın
Document doc = new Document();
Page page = doc.Pages.Add();
// Bir tablo nesnesini somutlaştırın
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(tab1);
// Tablonun sütun genişlikleriyle ayarla
tab1.ColumnWidths = "50 50 50";
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
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("hücre içine yerleştirilecek büyük metin dizili col3");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Satır1.Hücreler[2].Paragraflar[0].SabitGenişlik= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Pdf'i kaydet
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Çözüm
Tebrikler! Aspose.PDF for .NET kullanarak bir tabloda kenar boşluklarını veya dolguyu nasıl ayarlayacağınızı başarıyla öğrendiniz. Bu bilgi, belge biçimlendirme becerilerinizi geliştirmenize ve tablolarınızı görsel olarak çekici hale getirmenize yardımcı olacaktır.