---
title: Çizgi Çizimi
linktitle: Çizgi Çizimi
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF'i kullanarak bir sayfaya çizgi çizmeyi öğrenin. Özel çizgiler oluşturmaya yönelik adım adım kılavuz.
type: docs
weight: 80
url: /tr/net/programming-with-graphs/drawing-line/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir çizgi çizmek için aşağıdaki C# kaynak kodunu adım adım inceleyeceğiz.

Başlamadan önce Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Ayrıca C# programlamanın temel bilgisine sahip olun.

## Adım 1: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istediğiniz dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Bir Belge Örneği Oluşturma ve Bir Sayfa Ekleme

Document sınıfının bir örneğini oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Adım 3: Sayfa Kenar Boşluklarını Ayarlama

Sayfa kenar boşluklarını her tarafta 0 olarak ayarladık.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Adım 4: Bir Grafik Nesnesi ve İlk Satırı Oluşturma

Sayfanın boyutlarına eşit boyutlarda bir Graph nesnesi oluşturuyoruz ve sayfanın sol alt köşesinden sağ üst köşesine giden ilk çizgiyi çiziyoruz.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Adım 5: İkinci çizgiyi çizin

İkinci çizgiyi sayfanın sol üst köşesinden sağ alt köşesine doğru çiziyoruz.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Adım 6: Grafik Nesnesini Sayfaya Ekleme

Graph nesnesini sayfanın paragraf koleksiyonuna ekliyoruz.

```csharp
pg.Paragraphs.Add(graph);
```

## Adım 7: Ortaya Çıkan PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "DrawingLine_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### .NET için Aspose.PDF kullanarak Çizgi Çizimi için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği oluştur
Document pDoc = new Document();
// PDF belgesinin sayfa sayfa koleksiyonunu ekle
Page pg = pDoc.Pages.Add();
// Sayfa kenar boşluğunu tüm kenarlarda 0 olarak ayarla
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Genişliği ve Yüksekliği sayfa boyutlarına eşit olan Grafik nesnesi oluşturun
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Sayfanın Sol Alt köşesinden Sağ Üst köşesine kadar ilk satır nesnesini oluşturun
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Grafik nesnesinin şekiller koleksiyonuna çizgi ekle
graph.Shapes.Add(line);
// Sayfanın sol üst köşesinden sayfanın sağ alt köşesine çizgi çizin
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Grafik nesnesinin şekiller koleksiyonuna çizgi ekle
graph.Shapes.Add(line2);
// Sayfanın paragraf koleksiyonuna Grafik nesnesi ekle
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// PDF dosyasını kaydet
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir çizginin nasıl çizileceğini açıkladık. Artık bu bilgiyi kullanarak PDF dosyalarınızda özel çizgilerle geometrik şekiller oluşturabilirsiniz.

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitimin amacı, .NET için Aspose.PDF kullanarak çizgi çizme sürecinde size rehberlik etmektir. Bir PDF sayfasında çizgilerin nasıl oluşturulacağını ve görünümlerinin nasıl özelleştirileceğini öğreneceksiniz.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

A: Başlamadan önce, Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Temel C# programlama bilgisi de önerilir.

#### S: PDF dosyasını kaydedeceğim dizini nasıl belirlerim?

A: Elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için verilen kaynak kodundaki "dataDir" değişkenini değiştirin.

#### S: PDF sayfasında çizgiler nasıl oluşturulur?

A: Eğitim, sayfanın boyutlarıyla bir Grafik nesnesi oluşturmayı ve ardından ona Çizgi nesneleri eklemeyi gösterir. İstenilen çizgileri oluşturmak için Çizgi nesnelerinin koordinatlarını ve özelliklerini değiştirin.

#### S: Çizgilerin görünümünü özelleştirebilir miyim?

A: Evet, Çizgi nesnelerinin özelliklerini değiştirerek çizgilerin görünümünü özelleştirebilirsiniz. Bu, koordinatlarını, rengini, kalınlığını ve diğer grafiksel niteliklerini değiştirmeyi içerir.

#### S: Çizgileri çizdikten sonra PDF belgesini nasıl kaydedebilirim?

 A: Sayfaya Çizgi nesneleriyle Grafik nesnesini ekledikten sonra, ortaya çıkan PDF belgesini kullanarak kaydedebilirsiniz.`pDoc.Save(dataDir + "DrawingLine_out.pdf");` Sağlanan kaynak kodundaki satır.

#### S: Farklı açılarda ve yönlerde çizgiler çizebilir miyim?

C: Evet, Grafik içerisindeki Çizgi nesnelerinin koordinatlarını ve özelliklerini ayarlayarak farklı açılarda ve yönlerde çizgiler çizebilirsiniz.