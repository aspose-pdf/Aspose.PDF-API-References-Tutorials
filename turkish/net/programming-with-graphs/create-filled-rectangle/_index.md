---
title: Dolu Dikdörtgen Oluştur
linktitle: Dolu Dikdörtgen Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile içi dolu bir dikdörtgen oluşturmayı öğrenin. Dolgu rengini özelleştirmek için adım adım kılavuz.
type: docs
weight: 50
url: /tr/net/programming-with-graphs/create-filled-rectangle/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak içi dolu bir dikdörtgen oluşturmak için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

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

## Adım 4: Dikdörtgen Nesnesi Oluşturun ve Grafiğe Ekleyin

Belirtilen boyutlara sahip bir Dikdörtgen nesnesi oluşturuyoruz ve onu grafiğin şekil koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## 5. Adım: Dolgu rengini ayarlama

GraphInfo nesnesinin FillColor özelliğini kullanarak dikdörtgenin dolgu rengini belirtebiliriz.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## 6. Adım: Elde Edilen PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "CreateFilledRectangle_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Aspose.PDF for .NET kullanarak Dolu Dikdörtgen Oluşturma için örnek kaynak kodu 

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
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Grafik nesnesi için dolgu rengi belirleyin
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Grafik nesnesinin şekiller koleksiyonuna dikdörtgen nesnesi ekleyin
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak dolu bir dikdörtgenin nasıl oluşturulacağını açıkladık. Artık bu bilgiyi, PDF dosyalarınızda özel dolgu renkleri ile geometrik şekiller oluşturmak için kullanabilirsiniz.
