---
title: PDF Dosyasına Satır Nesnesi Ekle
linktitle: PDF Dosyasına Satır Nesnesi Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasına özel satır nesnesinin nasıl ekleneceğini öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-graphs/add-line-object/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir satır nesnesi eklemek için aşağıdaki C# kaynak kodunu adım adım inceleyeceğiz.

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

## Adım 4: Çizgi Nesnesi Oluşturun ve Grafiğe Ekleyin

Belirtilen koordinatlarla bir Çizgi nesnesi oluşturuyoruz ve bunu grafiğin şekil koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Adım 5: Hat Kurulumu

Çizgi için tire türü ve tire aşaması gibi özellikler belirleyebiliriz.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Adım 6: PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "AddLineObject_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### .NET için Aspose.PDF kullanarak Satır Nesnesi Ekleme için örnek kaynak kodu 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Grafik nesnesi için dolgu rengini belirtin
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Grafik nesnesinin şekiller koleksiyonuna dikdörtgen nesnesi ekle
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir çizgi nesnesinin nasıl ekleneceğini adım adım açıkladık. Artık bu bilgiyi uygulamalarınızda özel çizgilerle PDF belgeleri oluşturmak için kullanabilirsiniz.

### PDF dosyasına satır nesnesi eklemeyle ilgili SSS

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, PDF belgelerinizi geliştirmek için Aspose.PDF for .NET kullanarak bir çizgi nesnesi ekleme sürecinde size rehberlik etmektir.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

A: Başlamadan önce Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Ayrıca, C# programlama konusunda temel bir anlayışa sahip olmanız önerilir.

#### S: PDF dosyasını kaydedeceğim dizini nasıl belirlerim?

A: Sağlanan kaynak kodunda, sonuçta elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkenini değiştirebilirsiniz.

#### S: Graph nesnesinin amacı nedir?

A: Graph nesnesi çizim öğeleri için bir kapsayıcı görevi görür. Belirtilen boyutlarla oluşturulur ve sayfanın paragraf koleksiyonuna eklenir.

#### S: PDF belgesine çizgi nesnesi nasıl ekleyebilirim?

A: Bir çizgi nesnesi eklemek için, belirtilen koordinatlara sahip Çizgi sınıfının bir örneğini oluşturun ve bunu grafiğin şekil koleksiyonuna ekleyin.

#### S: Çizginin görünümünü özelleştirebilir miyim?

C: Evet, Çizgi nesnesinin GraphInfo özelliğini kullanarak çizgi türü ve çizgi aşaması gibi özellikleri ayarlayarak çizginin görünümünü özelleştirebilirsiniz.

#### S: Dash dizisinin ve dash aşamasının belirtilmesinin amacı nedir?

A: Çizgi dizisi ve çizgi aşaması özellikleri, belirli desenlere sahip kesikli veya noktalı çizgiler oluşturmanıza olanak tanır.

#### S: Satır nesnesini ekledikten sonra PDF dosyasını nasıl kaydedebilirim?

 A: Satır nesnesini ekledikten sonra, ortaya çıkan PDF dosyasını kullanarak kaydedebilirsiniz.`doc.Save(dataDir + "AddLineObject_out.pdf");` Sağlanan kaynak kodundaki satır.

#### S: Örnek kaynak kodu mevcut mu?

C: Evet, eğitimde anlatılan adımları uygulamak için başvurabileceğiniz örnek bir kaynak kodu bulunmaktadır.