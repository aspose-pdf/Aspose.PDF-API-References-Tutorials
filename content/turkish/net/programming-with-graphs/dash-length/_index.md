---
title: Çizgi Uzunluğu
linktitle: Çizgi Uzunluğu
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF ile çizgi uzunluğunun nasıl ayarlanacağını öğrenin. Çizgi desenlerini özelleştirmek için adım adım kılavuz.
type: docs
weight: 70
url: /tr/net/programming-with-graphs/dash-length/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak çizgi uzunluğunu ayarlamak için aşağıdaki C# kaynak kodunu adım adım inceleyeceğiz.

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
Page page = doc.Pages.Add();
```

## Adım 3: Bir Grafik Nesnesi Oluşturma ve Sayfaya Ekleme

Belirtilen boyutlarda bir Graph nesnesi oluşturup sayfanın paragraf koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Adım 4: Bir Çizgi Nesnesi Oluşturma ve Yapılandırma

Belirtilen koordinatlarla bir Line nesnesi oluşturuyoruz ve çizgilerin rengini ve uzunluğunu yapılandırıyoruz.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Adım 5: Grafik Nesnesine Çizgi Ekleme

Çizgiyi Graph nesnesinin şekil koleksiyonuna ekliyoruz.

```csharp
canvas.Shapes.Add(line);
```

## Adım 6: Ortaya Çıkan PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "DashLength_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### .NET için Aspose.PDF kullanılarak Dash Uzunluğu için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneğini örneklendir
Document doc = new Document();
// Belge nesnesinin sayfa koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
// Belirli boyutlara sahip Çizim nesnesi oluşturun
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Sayfa örneğinin paragraf koleksiyonuna çizim nesnesi ekle
page.Paragraphs.Add(canvas);
// Çizgi nesnesi oluştur
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Çizgi nesnesi için renk ayarla
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Satır nesnesi için çizgi dizisini belirtin
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Çizgi örneği için çizgi aşamasını ayarlayın
line.GraphInfo.DashPhase = 1;
// Çizim nesnesinin şekiller koleksiyonuna çizgi ekle
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// PDF belgesini kaydet
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak çizgi uzunluğunun nasıl ayarlanacağını açıkladık. Şimdi bu bilgiyi kullanarak PDF dosyalarınızda özel çizgi desenlerine sahip çizgiler oluşturabilirsiniz.

## SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitimin amacı, .NET için Aspose.PDF kullanarak çizgiler için çizgi uzunluğunu ayarlama sürecinde size rehberlik etmektir. PDF dosyalarınızda özel çizgi desenlerine sahip çizgilerin nasıl oluşturulacağını öğreneceksiniz.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

A: Başlamadan önce Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. C# programlamanın temel bir anlayışına sahip olmanız da önerilir.

#### S: PDF dosyasını kaydedeceğim dizini nasıl belirlerim?

A: Elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için verilen kaynak kodundaki "dataDir" değişkenini değiştirin.

#### S: Özel çizgi desenlerine sahip bir çizgi nasıl oluştururum?

 A: Eğitimde, bir Line nesnesi oluşturma ve rengini, çizgi dizisini ve çizgi aşamasını yapılandırma gösterilmektedir.`GraphInfo` nesne. İstenilen çizgi desenini elde etmek için bu ayarları değiştirin.

#### S: Çizginin rengini özelleştirebilir miyim?

 A: Evet, çizginin rengini ayarlayarak özelleştirebilirsiniz.`Color` mülkiyeti`GraphInfo` Satır ile ilişkili nesne.

#### S: Tire uzunluğunu ayarladıktan sonra PDF belgesini nasıl kaydedebilirim?

 A: Line nesnesini istediğiniz çizgi deseniyle yapılandırdıktan sonra, ortaya çıkan PDF belgesini kullanarak kaydedebilirsiniz.`doc.Save(dataDir + "DashLength_out.pdf");` Sağlanan kaynak kodundaki satır.