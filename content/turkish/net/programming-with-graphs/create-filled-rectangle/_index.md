---
title: İçi Dolu Dikdörtgen Oluştur
linktitle: İçi Dolu Dikdörtgen Oluştur
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile içi dolu bir dikdörtgenin nasıl oluşturulacağını öğrenin. Dolgu rengini özelleştirmek için adım adım kılavuz.
type: docs
weight: 50
url: /tr/net/programming-with-graphs/create-filled-rectangle/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak içi dolu bir dikdörtgen oluşturmak için aşağıdaki C# kaynak kodunu adım adım anlatacağız.

Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

## Adım 1: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istediğiniz dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belge Örneği Oluşturma ve Sayfa Ekleme

Document sınıfının bir örneğini oluşturup bu belgeye bir sayfa ekliyoruz.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Adım 3: Grafik Nesnesi Oluşturma ve Sayfaya Ekleme

Belirtilen boyutlara sahip bir Graph nesnesi oluşturup onu sayfanın paragraf koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Adım 4: Dikdörtgen Nesnesi Oluşturun ve Grafiğe Ekleyin

Belirtilen boyutlara sahip bir Rectangle nesnesi oluşturup onu grafiğin şekil koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## 5. Adım: Dolgu rengini ayarlama

GraphInfo nesnesinin FillColor özelliğini kullanarak dikdörtgenin dolgu rengini belirleyebiliriz.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Adım 6: Ortaya Çıkan PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "CreateFilledRectangle_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Aspose.PDF for .NET kullanarak Dolgulu Dikdörtgen Oluşturma için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği oluştur
Document doc = new Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
// Grafik örneği oluştur
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Sayfa örneğinin paragraf koleksiyonuna grafik nesnesi ekleme
page.Paragraphs.Add(graph);
// Dikdörtgen örneği oluştur
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Grafik nesnesi için dolgu rengini belirtin
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Grafik nesnesinin şekiller koleksiyonuna dikdörtgen nesnesi ekleme
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak içi dolu bir dikdörtgenin nasıl oluşturulacağını anlattık. Artık bu bilgiyi PDF dosyalarınızda özel dolgu renkleriyle geometrik şekiller oluşturmak için kullanabilirsiniz.

## SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET'i kullanarak içi dolu bir dikdörtgen oluşturma sürecinde size rehberlik etmek ve PDF dosyalarınıza dolgu renkleri ile özel geometrik şekiller eklemenizi sağlamaktır.

#### S: Başlamadan önce hangi önkoşullar gereklidir?

C: Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ek olarak, C# programlama konusunda temel bir anlayışa sahip olmanız tavsiye edilir.

#### S: PDF dosyasının kaydedileceği dizini nasıl belirlerim?

C: Sağlanan kaynak kodunda, elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkenini değiştirebilirsiniz.

#### S: Graph nesnesinin amacı nedir?

C: Graph nesnesi çizim öğeleri için bir kap görevi görür. Belirtilen boyutlarla oluşturularak sayfanın paragraf koleksiyonuna eklenir.

#### S: PDF belgesine içi dolu bir dikdörtgeni nasıl ekleyebilirim?

C: Dolu bir dikdörtgen eklemek için, belirtilen boyutlara ve dolgu rengine sahip Rectangle sınıfının bir örneğini oluşturun ve bunu grafiğin şekil koleksiyonuna ekleyin.

#### S: Dikdörtgenin boyutlarını ve dolgu rengini özelleştirebilir miyim?

 C: Evet, dikdörtgenin boyutlarını ve dolgu rengini, aktarılan parametreleri değiştirerek özelleştirebilirsiniz.`Aspose.Pdf.Drawing.Rectangle` yapıcı ve FillColor özelliğini ayarlama.

#### S: Dolu dikdörtgeni oluşturduktan sonra ortaya çıkan PDF dosyasını nasıl kaydederim?

 C: Dolu dikdörtgeni oluşturduktan sonra ortaya çıkan PDF dosyasını`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` Sağlanan kaynak kodundaki satır.