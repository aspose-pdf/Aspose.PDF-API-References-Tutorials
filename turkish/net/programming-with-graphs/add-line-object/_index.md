---
title: Satır Nesnesi Ekle
linktitle: Satır Nesnesi Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasına nasıl özel çizgi nesnesi ekleyeceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-graphs/add-line-object/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir çizgi nesnesi eklemek için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belge Örneği Oluşturma ve Sayfa Ekleme

Document sınıfının bir örneğini oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3. Adım: Bir Grafik Nesnesi Oluşturma ve Sayfaya Ekleme

Belirtilen boyutlara sahip bir Grafik nesnesi oluşturuyoruz ve onu sayfanın paragraf koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Adım 4: Çizgi Nesnesi Oluşturun ve Grafiğe Ekleyin

Belirtilen koordinatlara sahip bir Line nesnesi oluşturuyoruz ve onu grafiğin şekil koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Adım 5: Hat Kurulumu

Çizgi tipi ve çizgi fazı gibi çizgi için özellikler belirleyebiliriz.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 6. Adım: PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını belirtilen dizine "AddLineObject_out.pdf" adıyla kaydediyoruz.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Aspose.PDF for .NET kullanarak Add Line Object için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği oluştur
Document doc = new Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
// Grafik örneği oluştur
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Sayfa örneğinin paragraf koleksiyonuna grafik nesnesi ekleyin
page.Paragraphs.Add(graph);
// Dikdörtgen örneği oluştur
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Grafik nesnesi için dolgu rengi belirleyin
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Grafik nesnesinin şekiller koleksiyonuna dikdörtgen nesnesi ekleyin
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir çizgi nesnesinin nasıl ekleneceğini adım adım açıkladık. Artık bu bilgiyi, uygulamalarınızda özel çizgiler içeren PDF belgeleri oluşturmak için kullanabilirsiniz.
