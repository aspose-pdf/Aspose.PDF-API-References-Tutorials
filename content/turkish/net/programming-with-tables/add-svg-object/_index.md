---
title: PDF Dosyasına SVG Nesnesi Ekle
linktitle: PDF Dosyasına SVG Nesnesi Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak SVG nesnelerini PDF dosyasına kolayca ekleyin.
type: docs
weight: 30
url: /tr/net/programming-with-tables/add-svg-object/
---
Bu eğitimde Aspose.PDF for .NET kütüphanesini kullanarak PDF dosyasına SVG nesnesinin nasıl ekleneceğini öğreneceğiz. SVG (Ölçeklenebilir Vektör Grafikleri), kalite kaybı olmadan kolayca ölçeklenebilen popüler bir vektör grafik formatıdır. Aspose.PDF ile SVG nesnelerini PDF belgelerinize programlı olarak ekleyebilirsiniz.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio yüklü
- Aspose.PDF for .NET kütüphanesi kuruldu

## 1. Adım: Ortamı Ayarlayın

Öncelikle Visual Studio'da yeni bir C# projesi oluşturarak ortamı ayarlayalım. Visual Studio'yu açın ve şu adımları izleyin:

1. Yeni bir proje oluşturmak için "Dosya" > "Yeni" > "Proje"ye tıklayın.
2. Kurulumunuza bağlı olarak "Konsol Uygulaması (.NET Framework)" veya "Konsol Uygulaması (.NET Core)" şablonunu seçin.
3. Projeniz için uygun bir ad ve konum seçin ve ardından "Oluştur"u tıklayın.

## Adım 2: Belge ve Görüntü Nesneleri Oluşturun

Bu adımda PDF belgemiz ve SVG görselimiz için gerekli nesneleri oluşturacağız. Projenizin C# dosyasını açın ve aşağıdaki kodu ekleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Anında Belge nesnesi
Document doc = new Document();
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## 3. Adım: Görüntü Özelliklerini Ayarlayın

Daha sonra SVG imajımızın özelliklerini ayarlayacağız. Dosya tipini SVG olarak, SVG dosyasının yolunu ve görselin boyutlarını belirteceğiz. Önceki adımın sonrasına aşağıdaki kodu ekleyin:

```csharp
// Resim türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Kaynak dosyanın yolu
img.File = dataDir + "SVGToPDF.svg";
// Resim örneği için genişliği ayarlayın
img. FixWidth = 50;
// Resim örneği için yüksekliği ayarlayın
img.FixHeight = 50;
```

## Adım 4: Tabloyu Oluşturun ve Yapılandırın

Şimdi bir tablo nesnesi oluşturalım ve sütun genişliklerini ayarlayalım. Her biri 100 birim genişliğinde iki sütunlu bir tablo oluşturacağız. Aşağıdaki kodu ekleyin:

```csharp
// Örnek tablosu oluştur
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tablo hücreleri için genişliği ayarlama
table. ColumnWidths = "100 100";
```

## Adım 5: Tabloya Hücre Ekleme

Bu adımda tabloya bir satır ve hücreler ekleyeceğiz. Her satır, tabloda yatay bir satırı temsil eder ve satırlara hücreler eklenir. Aşağıdaki kodu ekleyin:

```csharp
//Satır nesnesi oluşturun ve onu tablo örneğine ekleyin
Aspose.Pdf.Row row = table.Rows.Add();
// Hücre nesnesi oluşturun ve onu satır örneğine ekleyin
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Adım 6: Hücrelere Metin ve Resim Ekleme

Daha sonra tablonun hücrelerine metin ve SVG resmini ekleyelim. İlk hücreye "İlk hücre" metnini, ikinci hücreye ise SVG görselini ekleyeceğiz. Aşağıdaki kodu ekleyin:

```csharp
// Hücre nesnesinin paragraf koleksiyonuna metin parçası ekleme
cell.Paragraphs.Add(new TextFragment("First cell"));
// Satır nesnesine başka bir hücre ekle
cell = row. Cells. Add();
// Yakın zamanda eklenen hücre örneğinin paragraf koleksiyonuna SVG resmi ekleyin
cell.Paragraphs.Add(img);
```

## Adım 7: Belgeye Sayfa Oluşturun ve Ekleyin

Şimdi bir sayfa nesnesi oluşturup onu belgeye ekleyelim. Tablo, sayfanın paragraf koleksiyonuna eklenecektir. Aşağıdaki kodu ekleyin:

```csharp
// Sayfa nesnesi oluşturun ve onu belge örneğinin sayfa koleksiyonuna ekleyin
Page page = doc.Pages.Add();
// Sayfa nesnesinin paragraf koleksiyonuna tablo ekleyin
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

### Aspose.PDF for .NET kullanarak SVG nesnesi eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesini somutlaştır
Document doc = new Document();
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Resim türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Kaynak dosyanın yolu
img.File = dataDir + "SVGToPDF.svg";
// Resim örneği için genişliği ayarlayın
img.FixWidth = 50;
// Resim örneği için yüksekliği ayarlayın
img.FixHeight = 50;
// Tablo örneği oluştur
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tablo hücreleri için genişliği ayarlama
table.ColumnWidths = "100 100";
//Satır nesnesi oluşturun ve onu tablo örneğine ekleyin
Aspose.Pdf.Row row = table.Rows.Add();
// Hücre nesnesi oluşturun ve onu satır örneğine ekleyin
Aspose.Pdf.Cell cell = row.Cells.Add();
// Hücre nesnesinin paragraf koleksiyonuna metin parçası ekleme
cell.Paragraphs.Add(new TextFragment("First cell"));
// Satır nesnesine başka bir hücre ekle
cell = row.Cells.Add();
// Yakın zamanda eklenen hücre örneğinin paragraf koleksiyonuna SVG resmi ekleyin
cell.Paragraphs.Add(img);
// Sayfa nesnesi oluşturun ve onu belge örneğinin sayfa koleksiyonuna ekleyin
Page page = doc.Pages.Add();
// Sayfa nesnesinin paragraf koleksiyonuna tablo ekleyin
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kütüphanesini kullanarak bir PDF dosyasına SVG nesnesinin nasıl ekleneceğini öğrendik. Belge oluşturma, ortamı ayarlama, tablo hücresine SVG görüntüsü ekleme ve PDF dosyasını kaydetme sürecini adım adım ele aldık. Artık SVG nesnelerini PDF belgelerinize programlı olarak dahil edebilirsiniz.

### PDF dosyasına SVG nesnesi eklemeyle ilgili SSS

#### S: PDF belgesine birden fazla SVG nesnesi ekleyebilir miyim?

 C: Evet, PDF belgesine birden fazla SVG nesnesi ekleyebilirsiniz. Basitçe ek oluşturun ve yapılandırın`Aspose.Pdf.Image` Eklemek istediğiniz her SVG görüntüsü için örnekler oluşturun ve ardından bunları PDF belgesindeki istediğiniz tablo hücrelerine veya paragraflara ekleyin.

#### S: Tablo hücresindeki SVG görüntüsünün boyutunu ve konumunu nasıl ayarlayabilirim?

 C: Tablo hücresindeki SVG görüntüsünün boyutunu ve konumunu ayarlamak için`FixWidth` Ve`FixHeight` özellikleri`Aspose.Pdf.Image`misal. Ayrıca aşağıdaki gibi diğer özellikleri de kullanabilirsiniz`HorizontalAlignment` Ve`VerticalAlignment` Konumlandırmayı kontrol etmek için tablo hücresinin.

#### S: Aynı tablo hücresinde SVG görüntüsünün yanına metin eklemek mümkün müdür?

 C: Evet, aynı tablo hücresinde SVG görüntüsünün yanına metin eklemek mümkündür. Şunu kullanabilirsiniz:`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` SVG görüntüsüyle birlikte hücreye metin ekleme yöntemi.

#### S: SVG görüntüsüne köprüler ekleyebilir miyim?

 C: Evet, kullanarak SVG görüntüsüne köprüler ekleyebilirsiniz.`Hyperlink` mülkiyeti`Aspose.Pdf.Image` misal. Resmin tıklanabilir olması için köprü URL'sini veya eylemi ayarlayın.

#### S: Aspose.PDF for .NET, .NET Core 3.1 veya sonraki sürümlerle uyumlu mu?

C: Evet, Aspose.PDF for .NET, .NET Core 3.1 ve sonraki sürümlerle uyumludur. Hem .NET Framework hem de .NET Core uygulamalarında kullanabilirsiniz.