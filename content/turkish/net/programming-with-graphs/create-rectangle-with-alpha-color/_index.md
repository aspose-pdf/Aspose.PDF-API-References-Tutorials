---
title: Alfa Rengiyle Dikdörtgen Oluştur
linktitle: Alfa Rengiyle Dikdörtgen Oluştur
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak şeffaf renkli bir dikdörtgenin nasıl oluşturulacağını öğrenin. Şeffaflığı özelleştirmek için adım adım kılavuz.
type: docs
weight: 60
url: /tr/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak alfa renkli bir dikdörtgen oluşturmak için aşağıdaki C# kaynak kodunu adım adım anlatacağız.

Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

## Adım 1: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istediğiniz dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Bir Belge Nesnesinin Örneklenmesi ve Sayfa Ekleme

Document sınıfının bir örneğini oluşturup bu belgeye bir sayfa ekliyoruz.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Adım 3: Grafik Nesnesi ve Dikdörtgen Oluşturma

Belirtilen boyutlara sahip bir Graph nesnesi ve belirli boyutlara sahip bir dikdörtgen oluşturuyoruz.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## 4. Adım: Dikdörtgenin alfa rengini ayarlama

System.Drawing.Color sınıfının FromArgb yöntemini kullanarak dikdörtgen için bir alfa rengi belirtebiliriz.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Adım 5: Dikdörtgeni Grafik Nesnesine Ekleme

Dikdörtgeni Graph nesnesinin şekil koleksiyonuna ekliyoruz.

```csharp
canvas.Shapes.Add(rect);
```

## Adım 6: Farklı alfa rengiyle ikinci bir dikdörtgen oluşturma

Belirli boyutlara ve başka bir alfa rengine sahip ikinci bir dikdörtgen oluşturuyoruz.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Adım 7: Grafik Nesnesini Sayfaya Ekleme

Graph nesnesini Page nesnesinin Paragraph koleksiyonuna ekliyoruz.

```csharp
page.Paragraphs.Add(canvas);
```

## Adım 8: Ortaya Çıkan PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "CreateRectangleWithAlphaColor_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Aspose.PDF for .NET kullanarak Alfa Renkli Dikdörtgen Oluşturma için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneğini oluştur
Document doc = new Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
Aspose.Pdf.Page page = doc.Pages.Add();
// Grafik örneği oluştur
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Belirli boyutlara sahip dikdörtgen nesne oluşturma
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//Grafik dolgu rengini System.Drawing.Color yapısından 32 bit ARGB değerinden ayarlayın
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Graph örneğinin şekiller koleksiyonuna dikdörtgen nesnesi ekleme
canvas.Shapes.Add(rect);
// İkinci dikdörtgen nesneyi oluştur
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Sayfa nesnesinin paragraf koleksiyonuna grafik örneği ekleme
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak alfa renkli dikdörtgenin nasıl oluşturulacağını anlattık. Artık bu bilgiyi PDF dosyalarınızda şeffaf renklere sahip geometrik şekiller oluşturmak için kullanabilirsiniz.

## SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET'i kullanarak alfa renkli bir dikdörtgen oluşturma sürecinde size rehberlik etmektir. PDF dosyalarınıza şeffaf renklere sahip geometrik şekilleri nasıl ekleyeceğinizi öğreneceksiniz.

#### S: Başlamadan önce hangi önkoşullar gereklidir?

C: Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ek olarak, C# programlama konusunda temel bir anlayışa sahip olmanız tavsiye edilir.

#### S: PDF dosyasının kaydedileceği dizini nasıl belirlerim?

C: Sağlanan kaynak kodunda, elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkenini değiştirebilirsiniz.

#### S: Graph nesnesinin ve Rectangle'ın amacı nedir?

C: Grafik nesnesi çizim öğeleri için bir kap görevi görürken Dikdörtgen, PDF'ye ekleyeceğiniz geometrik şekli temsil eder.

#### S: Dikdörtgen için alfa rengini nasıl ayarlayabilirim?

C: Dikdörtgen için bir alfa rengi belirleyebilirsiniz.`FillColor` mülkiyeti`GraphInfo` nesne ve`Color.FromRgb` ARGB değeri olan yöntem.

#### S: Farklı alfa renklerine sahip birden fazla dikdörtgen oluşturabilir miyim?

C: Evet, eğitimde gösterildiği gibi benzer adımları izleyerek farklı alfa renklerine sahip birden çok dikdörtgen oluşturabilirsiniz.

#### S: Alfa renkli dikdörtgenler oluşturduktan sonra ortaya çıkan PDF dosyasını nasıl kaydederim?

 C: Alfa renkli dikdörtgenler oluşturduktan sonra ortaya çıkan PDF dosyasını`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` Sağlanan kaynak kodundaki satır.