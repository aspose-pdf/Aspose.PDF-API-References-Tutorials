---
title: Çizgi Uzunluğu
linktitle: Çizgi Uzunluğu
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile kısa çizgilerin uzunluğunu nasıl ayarlayacağınızı öğrenin. Çizgi desenlerini özelleştirmek için adım adım kılavuz.
type: docs
weight: 70
url: /tr/net/programming-with-graphs/dash-length/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak kısa çizgilerin uzunluğunu ayarlamak için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

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
Page page = doc.Pages.Add();
```

## 3. Adım: Bir Grafik Nesnesi Oluşturma ve Sayfaya Ekleme

Belirtilen boyutlara sahip bir Grafik nesnesi oluşturuyoruz ve onu sayfanın paragraf koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Adım 4: Çizgi Nesnesi Oluşturma ve Yapılandırma

Belirtilen koordinatlara sahip bir Line nesnesi oluşturuyoruz ve çizgilerin rengini ve uzunluğunu yapılandırıyoruz.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Adım 5: Çizgiyi Grafik Nesnesine Ekleme

Çizgiyi Graph nesnesinin şekil koleksiyonuna ekliyoruz.

```csharp
canvas.Shapes.Add(line);
```

## 6. Adım: Elde Edilen PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını belirtilen dizine "DashLength_out.pdf" adıyla kaydediyoruz.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Aspose.PDF for .NET kullanan Tire Uzunluğu için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği örneği
Document doc = new Document();
// Belge nesnesinin sayfa koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
// Belirli boyutlara sahip Çizim nesnesi oluşturun
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Sayfa örneğinin paragraf koleksiyonuna çizim nesnesi ekleyin
page.Paragraphs.Add(canvas);
// Satır nesnesi oluştur
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Çizgi nesnesi için renk ayarla
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Satır nesnesi için kısa çizgi dizisini belirtin
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Line örneği için kısa çizgi aşamasını ayarlayın
line.GraphInfo.DashPhase = 1;
// Çizim nesnesinin şekiller koleksiyonuna çizgi ekleme
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// PDF belgesini kaydet
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak kısa çizgilerin uzunluğunun nasıl ayarlanacağını açıkladık. Artık bu bilgiyi, PDF dosyalarınızda özel çizgi desenleriyle çizgiler oluşturmak için kullanabilirsiniz.
