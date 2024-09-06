---
title: Dolu Dikdörtgen Oluştur
linktitle: Dolu Dikdörtgen Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF ile dolu bir dikdörtgenin nasıl oluşturulacağını öğrenin. Dolgu rengini özelleştirmek için adım adım kılavuz.
type: docs
weight: 50
url: /tr/net/programming-with-graphs/create-filled-rectangle/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak dolu bir dikdörtgen oluşturmak için aşağıdaki C# kaynak kodunu adım adım inceleyeceğiz.

Başlamadan önce Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Ayrıca C# programlamanın temel bilgisine sahip olun.

## Adım 1: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istediğiniz dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Bir Belge Örneği Oluşturma ve Bir Sayfa Ekleme

Document sınıfının bir örneğini oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Adım 3: Bir Grafik Nesnesi Oluşturma ve Sayfaya Ekleme

Belirtilen boyutlarda bir Graph nesnesi oluşturup sayfanın paragraf koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Adım 4: Dikdörtgen Nesnesi Oluşturun ve Grafiğe Ekleyin

Belirtilen ölçülerde bir Dikdörtgen nesnesi oluşturup grafiğin şekil koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Adım 5: Dolgu rengini ayarlama

Dikdörtgenin dolgu rengini GraphInfo nesnesinin FillColor özelliğini kullanarak belirleyebiliriz.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Adım 6: Ortaya Çıkan PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "CreateFilledRectangle_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### .NET için Aspose.PDF kullanarak Dolu Dikdörtgen Oluşturma için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği oluştur
Document doc = new Document();
// PDF dosyasının sayfa sayfa koleksiyonunu ekle
Page page = doc.Pages.Add();
// Grafik örneği oluştur
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Sayfa örneğinin paragraf koleksiyonuna grafik nesnesi ekle
page.Paragraphs.Add(graph);
// Dikdörtgen örneği oluştur
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Grafik nesnesi için dolgu rengini belirtin
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Grafik nesnesinin şekiller koleksiyonuna dikdörtgen nesnesi ekle
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak dolu bir dikdörtgenin nasıl oluşturulacağını açıkladık. Artık bu bilgiyi kullanarak PDF dosyalarınızda özel dolgu renklerine sahip geometrik şekiller oluşturabilirsiniz.

## SSS

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET kullanarak dolu bir dikdörtgen oluşturma sürecinde size rehberlik ederek, PDF dosyalarınıza dolgu renkleriyle özel geometrik şekiller eklemenizi sağlamaktır.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

A: Başlamadan önce, Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Ek olarak, C# programlama konusunda temel bir anlayışa sahip olmanız önerilir.

#### S: PDF dosyasını kaydedeceğim dizini nasıl belirlerim?

A: Sağlanan kaynak kodunda, sonuçta elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkenini değiştirebilirsiniz.

#### S: Graph nesnesinin amacı nedir?

A: Graph nesnesi çizim öğeleri için bir kapsayıcı görevi görür. Belirtilen boyutlarla oluşturulur ve sayfanın paragraf koleksiyonuna eklenir.

#### S: PDF belgesine nasıl dolu dikdörtgen ekleyebilirim?

A: Dolu bir dikdörtgen eklemek için, belirtilen boyutlar ve dolgu rengiyle Rectangle sınıfının bir örneğini oluşturun ve bunu grafiğin şekil koleksiyonuna ekleyin.

#### S: Dikdörtgenin boyutlarını ve dolgu rengini özelleştirebilir miyim?

 A: Evet, dikdörtgenin boyutlarını ve dolgu rengini, geçirilen parametreleri değiştirerek özelleştirebilirsiniz.`Aspose.Pdf.Drawing.Rectangle` yapıcı ve FillColor özelliğini ayarlama.

#### S: Dolu dikdörtgeni oluşturduktan sonra ortaya çıkan PDF dosyasını nasıl kaydederim?

 A: Dolu dikdörtgeni oluşturduktan sonra, ortaya çıkan PDF dosyasını kullanarak kaydedebilirsiniz.`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` Sağlanan kaynak kodundaki satır.