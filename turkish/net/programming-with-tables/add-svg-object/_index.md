---
title: PDF Dosyasına SVG Nesnesi Ekle
linktitle: PDF Dosyasına SVG Nesnesi Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasına kolayca SVG nesneleri ekleyin.
type: docs
weight: 30
url: /tr/net/programming-with-tables/add-svg-object/
---
Bu öğreticide, Aspose.PDF for .NET kitaplığını kullanarak PDF dosyasına bir SVG nesnesinin nasıl ekleneceğini öğreneceğiz. SVG (Scalable Vector Graphics), kaliteden ödün vermeden kolayca ölçeklenebilen popüler bir vektör grafik formatıdır. Aspose.PDF ile PDF belgelerinize programlı olarak SVG nesneleri ekleyebilirsiniz.

## Gereksinimler

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio yüklü
- Aspose.PDF for .NET library yüklü

## 1. Adım: Ortamı Kurun

Öncelikle Visual Studio'da yeni bir C# projesi oluşturarak ortamı kuralım. Visual Studio'yu açın ve şu adımları izleyin:

1. Yeni bir proje oluşturmak için "Dosya" > "Yeni" > "Proje"ye tıklayın.
2. Kurulumunuza bağlı olarak "Konsol Uygulaması (.NET Framework)" veya "Konsol Uygulaması (.NET Core)" şablonunu seçin.
3. Projeniz için uygun bir ad ve konum seçin, ardından "Oluştur"u tıklayın.

## 2. Adım: Belge ve Görüntü Nesneleri Oluşturun

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

Ardından, SVG resmimizin özelliklerini ayarlayacağız. Dosya tipini SVG, SVG dosyasının yolunu ve görselin boyutlarını belirleyeceğiz. Önceki adımdan sonra aşağıdaki kodu ekleyin:

```csharp
// Görüntü türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Kaynak dosya yolu
img.File = dataDir + "SVGToPDF.svg";
// Görüntü örneği için genişliği ayarla
img. FixWidth = 50;
// Görüntü örneği için yüksekliği ayarla
img.FixHeight = 50;
```

## 4. Adım: Tabloyu Oluşturun ve Yapılandırın

Şimdi bir tablo nesnesi oluşturalım ve sütun genişliklerini ayarlayalım. Her biri 100 birim genişliğinde iki sütunlu bir tablo oluşturacağız. Aşağıdaki kodu ekleyin:

```csharp
// Örnek tablo oluştur
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tablo hücreleri için genişliği ayarla
table. ColumnWidths = "100 100";
```

## Adım 5: Tabloya Hücreleri Ekleyin

Bu adımda tabloya bir satır ve hücreler ekleyeceğiz. Tablodaki her satır yatay bir satırı temsil eder ve satırlara hücreler eklenir. Aşağıdaki kodu ekleyin:

```csharp
//Satır nesnesi oluşturun ve bunu tablo örneğine ekleyin
Aspose.Pdf.Row row = table.Rows.Add();
// Hücre nesnesi oluşturun ve bunu satır örneğine ekleyin
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## 6. Adım: Hücrelere Metin ve Resim Ekleyin

Ardından, tablonun hücrelerine metin ve SVG görüntüsü ekleyelim. İlk hücreye "First cell" yazısını, ikinci hücreye de SVG görselini ekleyeceğiz. Aşağıdaki kodu ekleyin:

```csharp
// Hücre nesnesinin paragraf koleksiyonuna metin parçası ekleyin
cell.Paragraphs.Add(new TextFragment("First cell"));
// Satır nesnesine başka bir hücre ekle
cell = row. Cells. Add();
// Son eklenen hücre örneğinin paragraf koleksiyonuna SVG görüntüsü ekleyin
cell.Paragraphs.Add(img);
```

## 7. Adım: Bir Sayfa Oluşturun ve Belgeye Ekleyin

Şimdi bir sayfa nesnesi oluşturalım ve belgeye ekleyelim. Tablo, sayfanın paragraf koleksiyonuna eklenecektir. Aşağıdaki kodu ekleyin:

```csharp
// Sayfa nesnesi oluşturun ve onu belge örneğinin sayfalar koleksiyonuna ekleyin
Page page = doc.Pages.Add();
// Sayfa nesnesinin paragraf koleksiyonuna tablo ekle
page.Paragraphs.Add(table);
```

## 8. Adım: PDF Dosyasını Kaydedin

Son olarak, PDF dosyasını belirtilen konuma kaydedeceğiz. Aşağıdaki kodu ekleyin:

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

// Belge nesnesini örneklendir
Document doc = new Document();
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Görüntü türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Kaynak dosya yolu
img.File = dataDir + "SVGToPDF.svg";
// Görüntü örneği için genişliği ayarla
img.FixWidth = 50;
// Görüntü örneği için yüksekliği ayarla
img.FixHeight = 50;
// Tablo örneği oluştur
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tablo hücreleri için genişliği ayarla
table.ColumnWidths = "100 100";
//Satır nesnesi oluşturun ve bunu tablo örneğine ekleyin
Aspose.Pdf.Row row = table.Rows.Add();
// Hücre nesnesi oluşturun ve bunu satır örneğine ekleyin
Aspose.Pdf.Cell cell = row.Cells.Add();
// Hücre nesnesinin paragraf koleksiyonuna metin parçası ekleyin
cell.Paragraphs.Add(new TextFragment("First cell"));
// Satır nesnesine başka bir hücre ekle
cell = row.Cells.Add();
// Son eklenen hücre örneğinin paragraf koleksiyonuna SVG görüntüsü ekleyin
cell.Paragraphs.Add(img);
// Sayfa nesnesi oluşturun ve onu belge örneğinin sayfalar koleksiyonuna ekleyin
Page page = doc.Pages.Add();
// Sayfa nesnesinin paragraf koleksiyonuna tablo ekle
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kitaplığını kullanarak bir PDF dosyasına SVG nesnesi eklemeyi öğrendik. Belge oluşturma, ortamı ayarlama, tablo hücresine SVG görüntüsü ekleme ve PDF dosyasını kaydetme sürecini adım adım ele aldık. Artık SVG nesnelerini programlı olarak PDF belgelerinize dahil edebilirsiniz.

### PDF dosyasına SVG nesnesi eklemek için SSS

#### S: PDF belgesine birden çok SVG nesnesi ekleyebilir miyim?

 C: Evet, PDF belgesine birden çok SVG nesnesi ekleyebilirsiniz. Ek oluşturmanız ve yapılandırmanız yeterlidir`Aspose.Pdf.Image` eklemek istediğiniz her SVG görüntüsü için örnekler ve ardından bunları PDF belgesindeki istediğiniz tablo hücrelerine veya paragraflara ekleyin.

#### S: Tablo hücresindeki SVG görüntüsünün boyutunu ve konumunu nasıl ayarlayabilirim?

 A: Tablo hücresindeki SVG görüntüsünün boyutunu ve konumunu ayarlamak için`FixWidth` Ve`FixHeight` özellikleri`Aspose.Pdf.Image`misal. gibi diğer özellikleri de kullanabilirsiniz.`HorizontalAlignment` Ve`VerticalAlignment` konumlandırmayı kontrol etmek için tablo hücresinin.

#### S: Aynı tablo hücresinde SVG görüntüsünün yanına metin eklemek mümkün müdür?

 C: Evet, aynı tablo hücresinde SVG görüntüsünün yanına metin eklemek mümkündür. kullanabilirsiniz`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` SVG görüntüsüyle birlikte hücreye metin ekleme yöntemi.

#### S: SVG görüntüsüne köprüler ekleyebilir miyim?

 A: Evet, kullanarak SVG görüntüsüne köprüler ekleyebilirsiniz.`Hyperlink` mülkiyeti`Aspose.Pdf.Image` misal. Görüntüyü tıklanabilir yapmak için köprü URL'sini veya eylemi ayarlayın.

#### S: Aspose.PDF for .NET, .NET Core 3.1 veya sonraki sürümlerle uyumlu mu?

C: Evet, Aspose.PDF for .NET, .NET Core 3.1 ve sonraki sürümlerle uyumludur. Hem .NET Framework hem de .NET Core uygulamalarında kullanabilirsiniz.