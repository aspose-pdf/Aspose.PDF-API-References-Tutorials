---
title: PDF Dosyasına Çizgi Nesnesi Ekle
linktitle: PDF Dosyasına Çizgi Nesnesi Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir PDF dosyasına nasıl özel çizgi nesnesi ekleyeceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-graphs/add-line-object/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir çizgi nesnesi eklemek için aşağıdaki C# kaynak kodunu adım adım anlatacağız.

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

## Adım 3: Grafik Nesnesi Oluşturma ve bunu sayfaya ekleme

Belirtilen boyutlara sahip bir Graph nesnesi oluşturup onu sayfanın paragraf koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Adım 4: Çizgi Nesnesi Oluşturun ve Grafiğe Ekleyin

Belirtilen koordinatlarla bir Line nesnesi oluşturup onu grafiğin şekil koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Adım 5: Hat Kurulumu

Çizgi tipi ve çizgi fazı gibi çizgiye ilişkin özellikleri belirleyebiliriz.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Adım 6: PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "AddLineObject_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Aspose.PDF for .NET kullanarak Satır Nesnesi Ekleme için örnek kaynak kodu 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Grafik nesnesi için dolgu rengini belirtin
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Grafik nesnesinin şekiller koleksiyonuna dikdörtgen nesnesi ekleme
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir çizgi nesnesinin nasıl ekleneceğini adım adım açıkladık. Artık bu bilgiyi uygulamalarınızda özel çizgiler içeren PDF belgeleri oluşturmak için kullanabilirsiniz.

### PDF dosyasına çizgi nesnesi eklemek için SSS

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, PDF belgelerinizi geliştirmek için Aspose.PDF for .NET kullanarak bir çizgi nesnesi ekleme sürecinde size rehberlik etmektir.

#### S: Başlamadan önce hangi önkoşullar gereklidir?

C: Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ek olarak, C# programlama konusunda temel bir anlayışa sahip olmanız tavsiye edilir.

#### S: PDF dosyasının kaydedileceği dizini nasıl belirlerim?

C: Sağlanan kaynak kodunda, elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkenini değiştirebilirsiniz.

#### S: Graph nesnesinin amacı nedir?

C: Graph nesnesi çizim elemanları için bir kap görevi görür. Belirtilen boyutlarla oluşturularak sayfanın paragraf koleksiyonuna eklenir.

#### S: PDF belgesine nasıl çizgi nesnesi ekleyebilirim?

C: Bir çizgi nesnesi eklemek için, belirtilen koordinatlara sahip Line sınıfının bir örneğini oluşturun ve bunu grafiğin şekil koleksiyonuna ekleyin.

#### S: Çizginin görünümünü özelleştirebilir miyim?

C: Evet, Çizgi nesnesinin GraphInfo özelliğini kullanarak çizgi türü ve çizgi aşaması gibi özellikleri ayarlayarak çizginin görünümünü özelleştirebilirsiniz.

#### S: Çizgi dizisini ve çizgi aşamasını belirtmenin amacı nedir?

C: Çizgi dizisi ve çizgi aşaması özellikleri, belirli desenlere sahip kesikli veya noktalı çizgiler oluşturmanıza olanak tanır.

#### S: Çizgi nesnesini ekledikten sonra PDF dosyasını nasıl kaydedebilirim?

 C: Çizgi nesnesini ekledikten sonra ortaya çıkan PDF dosyasını`doc.Save(dataDir + "AddLineObject_out.pdf");` Sağlanan kaynak kodundaki satır.

#### S: Örnek bir kaynak kodu mevcut mu?

C: Evet, eğitimde açıklanan adımları uygulamak için başvurabileceğiniz örnek bir kaynak kodu bulunmaktadır.