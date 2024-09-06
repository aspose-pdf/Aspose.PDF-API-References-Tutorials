---
title: Alfa Rengiyle Dikdörtgen Oluştur
linktitle: Alfa Rengiyle Dikdörtgen Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak şeffaf renkli bir dikdörtgenin nasıl oluşturulacağını öğrenin. Şeffaflığı özelleştirmek için adım adım kılavuz.
type: docs
weight: 60
url: /tr/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak alfa rengine sahip bir dikdörtgen oluşturmak için aşağıdaki C# kaynak kodunu adım adım inceleyeceğiz.

Başlamadan önce Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Ayrıca C# programlamanın temel bilgisine sahip olun.

## Adım 1: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istediğiniz dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Bir Belge Nesnesi Oluşturma ve Bir Sayfa Ekleme

Document sınıfının bir örneğini oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Adım 3: Bir Grafik Nesnesi ve Bir Dikdörtgen Oluşturma

Belirtilen boyutlara sahip bir Graph nesnesi ve yine belirli boyutlara sahip bir dikdörtgen oluşturuyoruz.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Adım 4: Dikdörtgen için alfa rengini ayarlama

System.Drawing.Color sınıfının FromArgb metodunu kullanarak dikdörtgen için bir alfa rengi belirleyebiliriz.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Adım 5: Dikdörtgeni Grafik Nesnesine Ekleme

Dikdörtgeni Graph nesnesinin şekil koleksiyonuna ekliyoruz.

```csharp
canvas.Shapes.Add(rect);
```

## Adım 6: Farklı bir alfa rengine sahip ikinci bir dikdörtgen oluşturma

Belirli ölçülerde ve başka bir alfa renginde ikinci bir dikdörtgen oluşturuyoruz.

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

### .NET için Aspose.PDF kullanarak Alfa Rengiyle Dikdörtgen Oluşturma için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneğini örneklendir
Document doc = new Document();
// PDF dosyasının sayfa sayfa koleksiyonunu ekle
Aspose.Pdf.Page page = doc.Pages.Add();
// Grafik örneği oluştur
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Belirli boyutlara sahip dikdörtgen nesnesi oluşturun
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// System.Drawing.Color yapısından 32 bitlik bir ARGB değerinden grafik dolgu rengini ayarlayın
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Grafik örneğinin şekiller koleksiyonuna dikdörtgen nesnesi ekleyin
canvas.Shapes.Add(rect);
// İkinci dikdörtgen nesnesini oluştur
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Sayfa nesnesinin paragraf koleksiyonuna grafik örneği ekle
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak alfa rengiyle bir dikdörtgenin nasıl oluşturulacağını açıkladık. Artık bu bilgiyi kullanarak PDF dosyalarınızda şeffaf renklerle geometrik şekiller oluşturabilirsiniz.

## SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, .NET için Aspose.PDF kullanarak alfa rengiyle bir dikdörtgen oluşturma sürecinde size rehberlik etmeyi amaçlamaktadır. PDF dosyalarınıza şeffaf renklerle geometrik şekiller eklemeyi öğreneceksiniz.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

A: Başlamadan önce, Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Ek olarak, C# programlama konusunda temel bir anlayışa sahip olmanız önerilir.

#### S: PDF dosyasını kaydedeceğim dizini nasıl belirlerim?

A: Sağlanan kaynak kodunda, sonuçta elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkenini değiştirebilirsiniz.

#### S: Graph nesnesinin ve Rectangle nesnesinin amacı nedir?

A: Grafik nesnesi çizim öğeleri için bir kapsayıcı görevi görürken, Dikdörtgen ise PDF'e ekleyeceğiniz geometrik şekli temsil eder.

#### S: Dikdörtgen için alfa rengini nasıl ayarlayabilirim?

 A: Dikdörtgen için bir alfa rengi belirleyebilirsiniz.`FillColor` mülkiyeti`GraphInfo` nesne ve`Color.FromRgb` ARGB değeri olan bir yöntem.

#### S: Farklı alfa renklerine sahip birden fazla dikdörtgen oluşturabilir miyim?

C: Evet, eğitimde gösterilen benzer adımları izleyerek farklı alfa renklerine sahip birden fazla dikdörtgen oluşturabilirsiniz.

#### S: Alfa renklerle dikdörtgenler oluşturduktan sonra ortaya çıkan PDF dosyasını nasıl kaydederim?

 A: Alfa renklerle dikdörtgenler oluşturduktan sonra, ortaya çıkan PDF dosyasını şu şekilde kaydedebilirsiniz:`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` Sağlanan kaynak kodundaki satır.