---
title: Kenar Boşlukları veya Dolgu
linktitle: Kenar Boşlukları veya Dolgu
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir tabloda kenar boşluklarının veya dolgunun nasıl ayarlanacağını öğrenin.
type: docs
weight: 140
url: /tr/net/programming-with-tables/margins-or-padding/
---
Bu eğitimde, bir tabloda kenar boşlukları veya dolgu ayarlamak için Aspose.PDF for .NET'i kullanmanın adım adım sürecinde size rehberlik edeceğiz. Bu işlevselliği C# kaynak kodunuzda anlamanıza ve uygulamanıza yardımcı olmak için açıklamalar ve kod parçacıkları sağlayacağız.

## Adım 1: Belge ve Sayfanın Kurulumu
Başlamak için, aşağıdaki kodu kullanarak belgeyi ve sayfayı ayarlamanız gerekir:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak Belge nesnesini örneklendirin
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Adım 2: Bir Tablo Oluşturma
Şimdi Aspose.Pdf.Table sınıfını kullanarak bir tablo nesnesi oluşturacağız:

```csharp
// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tabloyu istenilen bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(tab1);
```

## Adım 3: Sütun Genişliklerini ve Varsayılan Hücre Kenarlığını Ayarlama
Tablonun sütun genişliklerini ve varsayılan hücre kenarlığını ayarlamak için aşağıdaki kodu kullanın:

```csharp
// Tablonun sütun genişliklerini ayarlayın
tab1. ColumnWidths = "50 50 50";
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Adım 4: Tablo Kenarlığı ve Hücre Dolgusunun Ayarlanması
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

// Başka bir özelleştirilmiş BorderInfo nesnesini kullanarak tablo sınırını ayarlayın
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Adım 5: Satır ve Hücre Ekleme
Şimdi tabloya satırlar ve hücreler ekleyelim. Yeni bir satır oluşturacağız ve ona hücreler ekleyeceğiz:

```csharp
//Tabloda satırlar ve ardından satırlarda hücreler oluşturun
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

### .NET için Aspose.PDF kullanarak Kenar Boşlukları veya Dolgu için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak Belge nesnesini örneklendirin
Document doc = new Document();
Page page = doc.Pages.Add();
// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// İstenilen bölümün paragraf koleksiyonuna tabloyu ekleyin
page.Paragraphs.Add(tab1);
// Tablonun sütun genişlikleriyle ayarlayın
tab1.ColumnWidths = "50 50 50";
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
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("hücrenin içine yerleştirilecek büyük metin dizesine sahip sütun3");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Satır1.Hücreler[2].Paragraflar[0].SabitGenişlik= 80;
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
Tebrikler! Aspose.PDF for .NET kullanarak bir tabloda kenar boşluklarını veya dolguyu nasıl ayarlayacağınızı başarıyla öğrendiniz. Bu bilgi, belge biçimlendirme yeteneklerinizi geliştirmenize ve tablolarınızı görsel olarak çekici hale getirmenize yardımcı olacaktır.

### SSS

#### S: Bir tablodaki her bir hücre için farklı kenar boşlukları veya dolgu belirleyebilir miyim?

 A: Evet, .NET için Aspose.PDF kullanarak bir tablodaki tek tek hücreler için farklı kenar boşlukları veya dolgular ayarlayabilirsiniz. Sağlanan örnekte, tüm tablo için varsayılan hücre dolgusunu şu şekilde ayarladık:`DefaultCellPadding` Özellik. Belirli hücreler için farklı dolgu ayarlamak için, şuraya erişebilirsiniz:`MarginInfo` Her hücrenin ayrı ayrı boyutlarını belirleyip kenar boşluklarını değiştirebilirsiniz.

#### S: Tablonun kenarlık rengini veya stilini nasıl değiştirebilirim?

 A: Tablonun kenarlık rengini veya stilini değiştirmek için,`Color` Ve`Width` özellikleri`BorderInfo` nesne. Verilen örnekte, kenarlık rengini siyaha ve genişliğini 1F (bir nokta) olarak ayarladık`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Rengi ve genişliğini isteğinize göre ayarlayabilirsiniz.

#### S: Tabloya üstbilgi veya altbilgi eklemek mümkün mü?

A: Evet, .NET için Aspose.PDF kullanarak tabloya başlıklar veya altbilgiler ekleyebilirsiniz. Başlıklar ve altbilgiler genellikle sütun etiketleri, tablo başlıkları veya özet veriler gibi ek bilgiler içeren ayrı satırlardır. Ek satırlar oluşturabilir, bunları farklı şekilde biçimlendirebilir ve bunları tablo içeriğinin üstüne veya altına ekleyebilirsiniz.

#### S: Bir tablo hücresi içindeki metnin hizalamasını nasıl ayarlarım?

 A: Bir tablo hücresi içindeki metin hizalamasını ayarlamak için şunu kullanabilirsiniz:`HorizontalAlignment` Ve`VerticalAlignment` özellikleri`TextFragment` nesne. Örneğin, metni yatay olarak ortaya hizalamak için,`mytext.HorizontalAlignment = HorizontalAlignment.Center;` Benzer şekilde, şunu da ayarlayabilirsiniz:`mytext.VerticalAlignment` Dikey hizalamayı kontrol etmek için.

#### S: Tablo hücrelerine metin yerine resim ekleyebilir miyim?

 A: Evet, .NET için Aspose.PDF'yi kullanarak tablo hücrelerine resim ekleyebilirsiniz. Bir`TextFragment` nesne, bir tane yaratabilirsiniz`Image` nesneyi seçin, resim dosyasını yükleyin ve istediğiniz hücreye ekleyin`cell.Paragraphs.Add(image);`yöntem. Bu, metin içeriğinin yanında tabloya resim eklemenize olanak tanır.