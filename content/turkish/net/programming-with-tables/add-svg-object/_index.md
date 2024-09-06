---
title: PDF Dosyasına SVG Nesnesi Ekle
linktitle: PDF Dosyasına SVG Nesnesi Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasına kolayca SVG nesneleri ekleyin.
type: docs
weight: 30
url: /tr/net/programming-with-tables/add-svg-object/
---
Bu eğitimde, Aspose.PDF for .NET kütüphanesini kullanarak PDF dosyasına bir SVG nesnesinin nasıl ekleneceğini öğreneceğiz. SVG (Ölçeklenebilir Vektör Grafikleri), kalite kaybı olmadan kolayca ölçeklenebilen vektör grafikleri için popüler bir formattır. Aspose.PDF ile PDF belgelerinize programatik olarak SVG nesneleri ekleyebilirsiniz.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio yüklendi
- .NET kütüphanesi için Aspose.PDF yüklendi

## Adım 1: Ortamı Ayarlayın

Öncelikle Visual Studio'da yeni bir C# projesi oluşturarak ortamı ayarlayalım. Visual Studio'yu açın ve şu adımları izleyin:

1. Yeni bir proje oluşturmak için "Dosya" > "Yeni" > "Proje"ye tıklayın.
2. Kurulumunuza bağlı olarak "Konsol Uygulaması (.NET Framework)" veya "Konsol Uygulaması (.NET Core)" şablonunu seçin.
3. Projeniz için uygun bir isim ve konum seçin, ardından "Oluştur"a tıklayın.

## Adım 2: Belge ve Görüntü Nesneleri Oluşturun

Bu adımda, PDF belgemiz ve SVG resmimiz için gerekli nesneleri oluşturacağız. Projenizin C# dosyasını açın ve aşağıdaki kodu ekleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Anlık Belge nesnesi
Document doc = new Document();
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Adım 3: Görüntü Özelliklerini Ayarlayın

Sonra, SVG resmimiz için özellikleri ayarlayacağız. Dosya türünü SVG, SVG dosyasının yolunu ve resmin boyutlarını belirteceğiz. Önceki adımdan sonra aşağıdaki kodu ekleyin:

```csharp
// Resim türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Kaynak dosya yolu
img.File = dataDir + "SVGToPDF.svg";
// Resim örneği için genişliği ayarlayın
img. FixWidth = 50;
// Resim örneği için yüksekliği ayarlayın
img.FixHeight = 50;
```

## Adım 4: Tabloyu Oluşturun ve Yapılandırın

Şimdi bir tablo nesnesi oluşturalım ve sütun genişliklerini ayarlayalım. Her biri 100 birim genişliğinde iki sütundan oluşan bir tablo oluşturacağız. Aşağıdaki kodu ekleyin:

```csharp
// Örnek tablo oluştur
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tablo hücreleri için genişlik ayarlayın
table. ColumnWidths = "100 100";
```

## Adım 5: Tabloya Hücreler Ekleyin

Bu adımda tabloya bir satır ve hücreler ekleyeceğiz. Her satır tabloda yatay bir satırı temsil eder ve hücreler satırlara eklenir. Aşağıdaki kodu ekleyin:

```csharp
//Satır nesnesi oluştur ve onu tablo örneğine ekle
Aspose.Pdf.Row row = table.Rows.Add();
// Hücre nesnesi oluştur ve onu satır örneğine ekle
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Adım 6: Hücrelere Metin ve Resim Ekleme

Sonra, tablonun hücrelerine metin ve SVG resmi ekleyelim. İlk hücreye "First cell" metnini ve ikinci hücreye SVG resmini ekleyeceğiz. Aşağıdaki kodu ekleyin:

```csharp
// Hücre nesnesinin paragraf koleksiyonuna metin parçası ekle
cell.Paragraphs.Add(new TextFragment("First cell"));
// Satır nesnesine başka bir hücre ekle
cell = row. Cells. Add();
// Son eklenen hücre örneğinin paragraf koleksiyonuna SVG resmi ekleyin
cell.Paragraphs.Add(img);
```

## Adım 7: Belgeye Bir Sayfa Oluşturun ve Ekleyin

Şimdi bir sayfa nesnesi oluşturalım ve bunu belgeye ekleyelim. Tablo sayfanın paragraf koleksiyonuna eklenecek. Aşağıdaki kodu ekleyin:

```csharp
// Sayfa nesnesi oluştur ve bunu belge örneğinin sayfalar koleksiyonuna ekle
Page page = doc.Pages.Add();
// Sayfa nesnesinin paragraf koleksiyonuna tablo ekle
page.Paragraphs.Add(table);
```

## Adım 8: PDF Dosyasını Kaydedin

Son olarak PDF dosyasını belirtilen konuma kaydedeceğiz. Aşağıdaki kodu ekleyin:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### .NET için Aspose.PDF kullanarak SVG nesnesi eklemek için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesini örnekle
Document doc = new Document();
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Resim türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Kaynak dosya yolu
img.File = dataDir + "SVGToPDF.svg";
// Resim örneği için genişliği ayarlayın
img.FixWidth = 50;
// Resim örneği için yüksekliği ayarlayın
img.FixHeight = 50;
// Tablo örneği oluştur
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tablo hücreleri için genişlik ayarlayın
table.ColumnWidths = "100 100";
//Satır nesnesi oluştur ve onu tablo örneğine ekle
Aspose.Pdf.Row row = table.Rows.Add();
// Hücre nesnesi oluştur ve onu satır örneğine ekle
Aspose.Pdf.Cell cell = row.Cells.Add();
// Hücre nesnesinin paragraf koleksiyonuna metin parçası ekle
cell.Paragraphs.Add(new TextFragment("First cell"));
// Satır nesnesine başka bir hücre ekle
cell = row.Cells.Add();
// Son eklenen hücre örneğinin paragraf koleksiyonuna SVG resmi ekleyin
cell.Paragraphs.Add(img);
// Sayfa nesnesi oluştur ve bunu belge örneğinin sayfalar koleksiyonuna ekle
Page page = doc.Pages.Add();
// Sayfa nesnesinin paragraf koleksiyonuna tablo ekle
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kütüphanesini kullanarak bir PDF dosyasına SVG nesnesi eklemeyi öğrendik. Bir belge oluşturma, ortamı ayarlama, bir tablo hücresine SVG resmi ekleme ve PDF dosyasını kaydetme adım adım sürecini ele aldık. Artık SVG nesnelerini PDF belgelerinize programatik olarak dahil edebilirsiniz.

### PDF dosyasına SVG nesnesi eklemeyle ilgili SSS

#### S: PDF belgesine birden fazla SVG nesnesi ekleyebilir miyim?

 A: Evet, PDF belgesine birden fazla SVG nesnesi ekleyebilirsiniz. Basitçe ek nesneler oluşturun ve yapılandırın`Aspose.Pdf.Image` Eklemek istediğiniz her SVG resmi için örnekler oluşturun ve ardından bunları PDF belgesindeki istediğiniz tablo hücrelerine veya paragraflara ekleyin.

#### S: Tablo hücresindeki SVG resminin boyutunu ve konumunu nasıl ayarlayabilirim?

 A: Tablo hücresindeki SVG görüntüsünün boyutunu ve konumunu ayarlamak için,`FixWidth` Ve`FixHeight` özellikleri`Aspose.Pdf.Image`örnek. Ayrıca şu gibi diğer özellikleri de kullanabilirsiniz:`HorizontalAlignment` Ve`VerticalAlignment` Tablo hücresinin konumlandırmasını kontrol etmek için.

#### S: Aynı tablo hücresindeki SVG resminin yanına metin eklemek mümkün müdür?

 A: Evet, aynı tablo hücresindeki SVG resminin yanına metin eklemek mümkündür.`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` SVG resminin yanına hücreye metin ekleme yöntemi.

#### S: SVG resmine köprü metni ekleyebilir miyim?

 A: Evet, SVG resmine köprü metni ekleyebilirsiniz.`Hyperlink` mülkiyeti`Aspose.Pdf.Image` Örnek. Resmi tıklanabilir yapmak için köprü metni URL'sini veya eylemi ayarlayın.

#### S: Aspose.PDF for .NET, .NET Core 3.1 veya sonraki sürümleriyle uyumlu mudur?

A: Evet, Aspose.PDF for .NET, .NET Core 3.1 ve sonraki sürümlerle uyumludur. Hem .NET Framework hem de .NET Core uygulamalarında kullanabilirsiniz.