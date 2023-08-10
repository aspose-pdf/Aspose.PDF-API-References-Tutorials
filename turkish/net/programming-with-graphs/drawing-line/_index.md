---
title: Çizim Hattı
linktitle: Çizim Hattı
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir sayfa boyunca nasıl çizgi çizeceğinizi öğrenin. Özel hatlar oluşturmak için adım adım kılavuz.
type: docs
weight: 80
url: /tr/net/programming-with-graphs/drawing-line/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir çizgi çizmek için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belge Örneği Oluşturma ve Sayfa Ekleme

Document sınıfının bir örneğini oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## 3. Adım: Sayfa Kenar Boşluklarını Ayarlama

Sayfa kenar boşluklarını her tarafta 0 olarak ayarladık.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Adım 4: Bir Grafik Nesnesi ve İlk Satır Oluşturma

Sayfanın boyutlarına eşit boyutlarda bir Graph nesnesi oluşturuyoruz ve sayfanın sol alt köşesinden sağ üst köşesine doğru giden ilk çizgiyi çiziyoruz.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Adım 5: İkinci çizgiyi çizme

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

## 7. Adım: Elde Edilen PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını belirtilen dizine "DrawingLine_out.pdf" adıyla kaydediyoruz.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Aspose.PDF for .NET kullanan Çizim Çizgisi için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği oluştur
Document pDoc = new Document();
// PDF belgesinin sayfa koleksiyonuna sayfa ekle
Page pg = pDoc.Pages.Add();
// Tüm kenarlarda sayfa kenar boşluğunu 0 olarak ayarla
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Sayfa boyutlarına eşit Genişlik ve Yüksekliğe sahip Grafik nesnesi oluşturun
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Sayfanın Sol Alt köşesinden Sağ Üst köşesine başlayarak ilk satır nesnesini oluştur
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Grafik nesnesinin şekiller koleksiyonuna çizgi ekleyin
graph.Shapes.Add(line);
// Sayfanın Sol Üst köşesinden sayfanın Sağ Alt köşesine çizgi çizin
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Grafik nesnesinin şekiller koleksiyonuna çizgi ekleyin
graph.Shapes.Add(line2);
// Sayfanın paragraf koleksiyonuna Grafik nesnesi ekleyin
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// PDF dosyasını kaydet
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak çizgi çizmeyi anlattık. Artık bu bilgiyi, PDF dosyalarınızda özel çizgilerle geometrik şekiller oluşturmak için kullanabilirsiniz.

### SSS

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET kullanarak çizgi çizme sürecinde size rehberlik etmektir. Bir PDF sayfasında çizgiler oluşturmayı ve bunların görünümünü özelleştirmeyi öğreneceksiniz.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

C: Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Temel C# programlama bilgisi de önerilir.

#### S: PDF dosyasının kaydedileceği dizini nasıl belirleyebilirim?

A: Ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmek için sağlanan kaynak kodundaki "dataDir" değişkenini değiştirin.

#### S: Bir PDF sayfasında nasıl satır oluşturabilirim?

C: Öğretici, sayfanın boyutlarıyla bir Grafik nesnesi oluşturmayı ve ardından buna Çizgi nesneleri eklemeyi gösterir. İstenen çizgileri oluşturmak için Line nesnelerinin koordinatlarını ve özelliklerini değiştirin.

#### S: Çizgilerin görünümünü özelleştirebilir miyim?

C: Evet, Line nesnelerinin özelliklerini değiştirerek çizgilerin görünümünü özelleştirebilirsiniz. Bu, koordinatlarını, rengini, kalınlığını ve diğer grafik niteliklerini değiştirmeyi içerir.

#### S: Çizgileri çizdikten sonra PDF belgesini nasıl kaydedebilirim?

A: Grafik nesnesini Çizgi nesneleri ile sayfaya ekledikten sonra, ortaya çıkan PDF belgesini kullanarak kaydedebilirsiniz.`pDoc.Save(dataDir + "DrawingLine_out.pdf");` Sağlanan kaynak kodundaki satır.

#### S: Farklı açılarda ve yönlerde çizgiler çizebilir miyim?

C: Evet, Grafik içindeki Çizgi nesnelerinin koordinatlarını ve özelliklerini ayarlayarak farklı açılarda ve yönlerde çizgiler çizebilirsiniz.