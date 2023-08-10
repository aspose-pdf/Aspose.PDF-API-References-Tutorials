---
title: Alfa Rengi ile Dikdörtgen Oluşturun
linktitle: Alfa Rengi ile Dikdörtgen Oluşturun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak saydam renkli bir dikdörtgenin nasıl oluşturulacağını öğrenin. Saydamlığı özelleştirmek için adım adım kılavuz.
type: docs
weight: 60
url: /tr/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak alfa renkli bir dikdörtgen oluşturmak için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Bir Belge Nesnesini Örnekleme ve Sayfa Ekleme

Document sınıfının bir örneğini oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 3. Adım: Grafik Nesnesi ve Dikdörtgen Oluşturma

Belirtilen boyutlara sahip bir Grafik nesnesi ve belirli boyutlara sahip bir dikdörtgen oluşturuyoruz.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## 4. Adım: Dikdörtgen için alfa renginin ayarlanması

System.Drawing.Color sınıfının FromArgb yöntemini kullanarak dikdörtgen için bir alfa rengi belirtebiliriz.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Adım 5: Grafik Nesnesine Dikdörtgen Ekleme

Dikdörtgeni Graph nesnesinin şekil koleksiyonuna ekliyoruz.

```csharp
canvas.Shapes.Add(rect);
```

## 6. Adım: Farklı bir alfa rengiyle ikinci bir dikdörtgen oluşturma

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

## 8. Adım: Elde Edilen PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "CreateRectangleWithAlphaColor_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Aspose.PDF for .NET kullanarak Alpha Color ile Dikdörtgen Oluştur için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği örneği
Document doc = new Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
Aspose.Pdf.Page page = doc.Pages.Add();
// Grafik örneği oluştur
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Belirli boyutlara sahip dikdörtgen nesne oluşturun
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//32 bit ARGB değerinden System.Drawing.Color yapısından grafik dolgu rengini ayarlayın
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Grafik örneğinin şekiller koleksiyonuna dikdörtgen nesnesi ekleyin
canvas.Shapes.Add(rect);
// İkinci dikdörtgen nesnesi oluştur
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Sayfa nesnesinin paragraf koleksiyonuna grafik örneği ekleyin
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak alfa renkli bir dikdörtgenin nasıl oluşturulacağını açıkladık. Artık bu bilgiyi, PDF dosyalarınızda saydam renklerle geometrik şekiller oluşturmak için kullanabilirsiniz.

## SSS

#### S: Bu eğitimin amacı nedir?

C: Bu eğitim, Aspose.PDF for .NET kullanarak alfa renkli bir dikdörtgen oluşturma sürecinde size rehberlik etmeyi amaçlamaktadır. Şeffaf renklerle geometrik şekilleri PDF dosyalarınıza nasıl ekleyeceğinizi öğreneceksiniz.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

C: Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ek olarak, temel bir C# programlama anlayışına sahip olunması önerilir.

#### S: PDF dosyasının kaydedileceği dizini nasıl belirleyebilirim?

Y: Sağlanan kaynak kodunda, elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkenini değiştirebilirsiniz.

#### S: Grafik nesnesinin ve Dikdörtgenin amacı nedir?

C: Grafik nesnesi, çizim öğeleri için bir kap görevi görürken, Dikdörtgen, PDF'ye ekleyeceğiniz geometrik şekli temsil eder.

#### S: Dikdörtgen için bir alfa rengini nasıl ayarlayabilirim?

C: kullanarak dikdörtgen için bir alfa rengi belirleyebilirsiniz.`FillColor` mülkiyeti`GraphInfo` nesne ve`Color.FromRgb` ARGB değeri olan bir yöntem.

#### S: Farklı alfa renkleriyle birden çok dikdörtgen oluşturabilir miyim?

C: Evet, eğitimde gösterilen benzer adımları izleyerek farklı alfa renklerine sahip birden çok dikdörtgen oluşturabilirsiniz.

#### S: Alfa renkli dikdörtgenler oluşturduktan sonra ortaya çıkan PDF dosyasını nasıl kaydedebilirim?

 A: Alfa renkli dikdörtgenleri oluşturduktan sonra, ortaya çıkan PDF dosyasını kullanarak kaydedebilirsiniz.`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` Sağlanan kaynak kodundaki satır.