---
title: Çizgi Uzunluğu
linktitle: Çizgi Uzunluğu
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile tirelerin uzunluğunu nasıl ayarlayacağınızı öğrenin. Çizgi desenlerini özelleştirmek için adım adım kılavuz.
type: docs
weight: 70
url: /tr/net/programming-with-graphs/dash-length/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak tirelerin uzunluğunu ayarlamak için aşağıdaki C# kaynak kodunu adım adım anlatacağız.

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
Page page = doc.Pages.Add();
```

## Adım 3: Grafik Nesnesi Oluşturma ve bunu sayfaya ekleme

Belirtilen boyutlara sahip bir Graph nesnesi oluşturup onu sayfanın paragraf koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Adım 4: Çizgi Nesnesi Oluşturma ve Yapılandırma

Belirlenen koordinatlara sahip bir Line nesnesi oluşturup çizgilerin rengini ve uzunluğunu yapılandırıyoruz.

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

## Adım 6: Ortaya Çıkan PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "DashLength_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Aspose.PDF for .NET kullanarak Çizgi Uzunluğu için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneğini oluştur
Document doc = new Document();
// Belge nesnesinin sayfa koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
// Belirli boyutlara sahip Çizim nesnesi oluşturma
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Sayfa örneğinin paragraf koleksiyonuna çizim nesnesi ekleme
page.Paragraphs.Add(canvas);
// Çizgi nesnesi oluştur
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Çizgi nesnesinin rengini ayarla
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Çizgi nesnesi için çizgi dizisini belirtin
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

Bu eğitimde Aspose.PDF for .NET kullanarak tire uzunluğunun nasıl ayarlanacağını açıkladık. Artık bu bilgiyi PDF dosyalarınızda özel çizgi desenlerine sahip çizgiler oluşturmak için kullanabilirsiniz.

## SSS

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET'i kullanarak çizgilerdeki tirelerin uzunluğunu ayarlama sürecinde size rehberlik etmektir. PDF dosyalarınızda özel çizgi desenlerine sahip çizgiler oluşturmayı öğreneceksiniz.

#### S: Başlamadan önce hangi önkoşullar gereklidir?

C: Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. C# programlamaya ilişkin temel bir anlayış da önerilir.

#### S: PDF dosyasının kaydedileceği dizini nasıl belirlerim?

C: Ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmek için sağlanan kaynak koddaki "dataDir" değişkenini değiştirin.

#### S: Özel çizgi desenlerine sahip bir çizgiyi nasıl oluşturabilirim?

 C: Öğretici, bir Line nesnesi oluşturmayı ve bu nesnenin rengini, çizgi dizisini ve çizgi aşamasını yapılandırmayı gösterir.`GraphInfo` nesne. İstenilen çizgi desenini elde etmek için bu ayarları değiştirin.

#### S: Çizginin rengini özelleştirebilir miyim?

 C: Evet, çizginin rengini ayarlayarak özelleştirebilirsiniz.`Color` mülkiyeti`GraphInfo` Çizgiyle ilişkili nesne.

#### S: Çizgi uzunluğunu ayarladıktan sonra PDF belgesini nasıl kaydedebilirim?

 C: Çizgi nesnesini istenen çizgi deseniyle yapılandırdıktan sonra, elde edilen PDF belgesini kullanarak kaydedebilirsiniz.`doc.Save(dataDir + "DashLength_out.pdf");` Sağlanan kaynak kodundaki satır.