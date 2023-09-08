---
title: Kenar Boşlukları veya Dolgu
linktitle: Kenar Boşlukları veya Dolgu
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir tabloda kenar boşluklarını veya dolguyu nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 140
url: /tr/net/programming-with-tables/margins-or-padding/
---
Bu eğitimde, bir tabloda kenar boşluklarını veya dolguları ayarlamak için Aspose.PDF for .NET'i kullanma sürecinde size adım adım rehberlik edeceğiz. Bu işlevselliği anlamanıza ve C# kaynak kodunuzda uygulamanıza yardımcı olacak açıklamalar ve kod parçacıkları sunacağız.

## 1. Adım: Belgeyi ve Sayfayı Ayarlama
Başlamak için aşağıdaki kodu kullanarak belgeyi ve sayfayı ayarlamanız gerekir:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş yapıcısını çağırarak Document nesnesini örnekleyin
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Adım 2: Tablo Oluşturma
Daha sonra Aspose.Pdf.Table sınıfını kullanarak bir tablo nesnesi oluşturacağız:

```csharp
// Bir tablo nesnesinin örneğini oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(tab1);
```

## Adım 3: Sütun Genişliklerini ve Varsayılan Hücre Kenarlığını Ayarlama
Tablonun sütun genişliklerini ve varsayılan hücre kenarlığını ayarlamak için aşağıdaki kodu kullanın:

```csharp
// Tablonun sütun genişliklerini ayarlayın
tab1. ColumnWidths = "50 50 50";
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlama
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Adım 4: Tablo Kenarlığını ve Hücre Dolgusunu Ayarlama
Tablo kenarlığını ve hücre dolgusunu ayarlamak için bir MarginInfo nesnesi oluşturun ve özelliklerini ayarlayın:

```csharp
// MarginInfo nesnesi oluşturun ve sol, alt, sağ ve üst kenar boşluklarını ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Varsayılan hücre dolgusunu MarginInfo nesnesine ayarlayın
tab1. DefaultCellPadding = margin;

// Başka bir özelleştirilmiş BorderInfo nesnesini kullanarak tablo kenarlığını ayarlayın
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Adım 5: Satır ve Hücre Ekleme
Şimdi tabloya satır ve hücre ekleyelim. Yeni bir satır oluşturup ona hücreler ekleyeceğiz:

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

## Adım 7: PDF'yi kaydetme
PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// PDF'yi kaydet
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanan Kenar Boşlukları veya Dolgu için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş yapıcısını çağırarak Document nesnesini başlatın
Document doc = new Document();
Page page = doc.Pages.Add();
// Bir tablo nesnesinin örneğini oluşturma
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(tab1);
// Tablonun sütun genişliklerine göre ayarlama
tab1.ColumnWidths = "50 50 50";
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
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("hücrenin içine yerleştirilecek büyük metin dizesine sahip col3");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// PDF'yi kaydet
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Çözüm
Tebrikler! Aspose.PDF for .NET'i kullanarak bir tabloda kenar boşluklarını veya dolguyu nasıl ayarlayacağınızı başarıyla öğrendiniz. Bu bilgi, belge biçimlendirme yeteneklerinizi geliştirmenize ve tablolarınızı görsel olarak çekici hale getirmenize yardımcı olacaktır.

### SSS'ler

#### S: Bir tablodaki tek tek hücreler için farklı kenar boşlukları veya dolgular ayarlayabilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak bir tablodaki tek tek hücreler için farklı kenar boşlukları veya dolgular ayarlayabilirsiniz. Verilen örnekte, tablonun tamamı için varsayılan hücre dolgusunu aşağıdaki komutu kullanarak ayarladık:`DefaultCellPadding` mülk. Belirli hücreler için farklı dolgu ayarlamak amacıyla`MarginInfo` her hücrenin ayrı ayrı ve kenar boşluklarını değiştirin.

#### S: Tablonun kenarlık rengini veya stilini nasıl değiştirebilirim?

 C: Tablonun kenarlık rengini veya stilini değiştirmek için`Color` Ve`Width` özellikleri`BorderInfo` nesne. Verilen örnekte, kenarlık rengini siyah ve genişliğini 1F (bir nokta) olarak ayarladık.`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Rengini ve genişliğini ihtiyaçlarınıza göre ayarlayabilirsiniz.

#### S: Tabloya üstbilgi veya altbilgi eklemek mümkün mü?

C: Evet, Aspose.PDF for .NET'i kullanarak tabloya üstbilgi veya altbilgi ekleyebilirsiniz. Üstbilgiler ve altbilgiler genellikle sütun etiketleri, tablo başlıkları veya özet verileri gibi ek bilgileri içeren ayrı satırlardır. Ek satırlar oluşturabilir, bunları farklı şekilde biçimlendirebilir ve tablo içeriğinin üstüne veya altına ekleyebilirsiniz.

#### S: Bir tablo hücresindeki metin hizalamasını nasıl ayarlayabilirim?

 C: Bir tablo hücresindeki metin hizalamasını ayarlamak için`HorizontalAlignment` Ve`VerticalAlignment` özellikleri`TextFragment` nesne. Örneğin, metni yatay olarak ortaya hizalamak için`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Benzer şekilde, ayarlayabilirsiniz`mytext.VerticalAlignment` Dikey hizalamayı kontrol etmek için.

#### S: Tablo hücrelerine metin yerine resim ekleyebilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak tablo hücrelerine görüntüler ekleyebilirsiniz. Bir oluşturmak yerine`TextFragment` nesne oluşturabilirsiniz.`Image` nesnesini seçin, görüntü dosyasını yükleyin ve düğmeyi kullanarak istediğiniz hücreye ekleyin.`cell.Paragraphs.Add(image);` yöntem. Bu, tabloya metin içeriğinin yanında resimler eklemenizi sağlar.