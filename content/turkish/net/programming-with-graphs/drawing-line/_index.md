---
title: Çizim Çizgisi
linktitle: Çizim Çizgisi
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak sayfa boyunca nasıl çizgi çizeceğinizi öğrenin. Özel çizgiler oluşturmaya yönelik adım adım kılavuz.
type: docs
weight: 80
url: /tr/net/programming-with-graphs/drawing-line/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir çizgi çizmek için aşağıdaki C# kaynak kodunu size adım adım anlatacağız.

Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

## Adım 1: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istediğiniz dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belge Örneği Oluşturma ve Sayfa Ekleme

Document sınıfının bir örneğini oluşturup bu belgeye bir sayfa ekliyoruz.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## 3. Adım: Sayfa Kenar Boşluklarını Ayarlama

Sayfa kenar boşluklarını her tarafta 0 olarak ayarladık.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Adım 4: Grafik Nesnesi ve İlk Satır Oluşturma

Sayfanın boyutlarına eşit boyutlarda bir Graph nesnesi oluşturup sayfanın sol alt köşesinden sağ üst köşesine giden ilk çizgiyi çiziyoruz.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Adım 5: İkinci çizgiyi çizme

Sayfanın sol üst köşesinden sağ alt köşesine doğru giden ikinci çizgiyi çiziyoruz.

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

### Aspose.PDF for .NET kullanarak Çizgi Çizimi için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği oluştur
Document pDoc = new Document();
// PDF belgesinin sayfa koleksiyonuna sayfa ekle
Page pg = pDoc.Pages.Add();
// Sayfa kenar boşluğunu tüm kenarlarda 0 olarak ayarla
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Genişlik ve Yükseklik sayfa boyutlarına eşit olan Grafik nesnesi oluşturun
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Sayfanın Sol Alt köşesinden Sağ Üst köşesine kadar ilk satır nesnesini oluşturun
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Grafik nesnesinin şekiller koleksiyonuna çizgi ekleme
graph.Shapes.Add(line);
// Sayfanın Sol Üst köşesinden Sayfanın Sağ Alt köşesine doğru çizgi çizin
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Grafik nesnesinin şekiller koleksiyonuna çizgi ekleme
graph.Shapes.Add(line2);
// Sayfanın paragraf koleksiyonuna Grafik nesnesi ekleme
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// PDF dosyasını kaydet
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak nasıl çizgi çizileceğini anlattık. Artık bu bilgiyi PDF dosyalarınızda özel çizgilerle geometrik şekiller oluşturmak için kullanabilirsiniz.

### SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı Aspose.PDF for .NET kullanarak çizgi çizme sürecinde size rehberlik etmektir. Bir PDF sayfasında çizgiler oluşturmayı ve görünümlerini nasıl özelleştireceğinizi öğreneceksiniz.

#### S: Başlamadan önce hangi önkoşullar gereklidir?

C: Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Temel C# programlama bilgisi de önerilir.

#### S: PDF dosyasının kaydedileceği dizini nasıl belirlerim?

C: Ortaya çıkan PDF dosyasını kaydetmek istediğiniz dizini belirtmek için sağlanan kaynak koddaki "dataDir" değişkenini değiştirin.

#### S: PDF sayfasında nasıl çizgiler oluşturabilirim?

C: Öğretici, sayfanın boyutlarına sahip bir Graph nesnesi oluşturmayı ve ardından buna Line nesneleri eklemeyi gösterir. İstediğiniz çizgileri oluşturmak için Çizgi nesnelerinin koordinatlarını ve özelliklerini değiştirin.

#### S: Çizgilerin görünümünü özelleştirebilir miyim?

C: Evet, Çizgi nesnelerinin özelliklerini değiştirerek çizgilerin görünümünü özelleştirebilirsiniz. Buna koordinatların, renklerin, kalınlıkların ve diğer grafiksel niteliklerin değiştirilmesi de dahildir.

#### S: Çizgileri çizdikten sonra PDF belgesini nasıl kaydedebilirim?

C: Çizgi nesnelerini içeren Grafik nesnesini sayfaya ekledikten sonra, elde edilen PDF belgesini kullanarak kaydedebilirsiniz.`pDoc.Save(dataDir + "DrawingLine_out.pdf");` Sağlanan kaynak kodundaki satır.

#### S: Farklı açı ve yönlerde çizgiler çizebilir miyim?

C: Evet, Grafik içindeki Çizgi nesnelerinin koordinatlarını ve özelliklerini ayarlayarak farklı açı ve yönelimlerde çizgiler çizebilirsiniz.