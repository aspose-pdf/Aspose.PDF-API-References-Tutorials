---
title: Degrade Dolgulu Çizim Ekle
linktitle: Degrade Dolgulu Çizim Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile degrade dolgulu çizim eklemeyi öğrenin. Çekici PDF belgeleri oluşturmak için adım adım eğitim.
type: docs
weight: 20
url: /tr/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak grafik programlamaya degrade dolgulu bir çizim eklemek için aşağıdaki C# kaynak kodunu adım adım anlatacağız.

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

## Adım 3: Grafik Nesnesi Oluşturma ve Sayfaya Ekleme

Belirtilen boyutlara sahip bir Graph nesnesi oluşturup onu sayfanın paragraf koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Adım 4: Dikdörtgen Nesnesi Oluşturun ve Grafiğe Ekleyin

Belirtilen boyutlara sahip bir Rectangle nesnesi oluşturup onu grafiğin şekil koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Adım 5: Degrade Dolguyu Yapılandırma

GradientAxialShading sınıfını kullanarak dikdörtgenin degrade dolgusunu yapılandırıyoruz.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Bu, kırmızıdan maviye, (0, 0) noktasından (300, 300) noktasına kadar bir degrade dolgu oluşturur.

## Adım 6: PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "AddDrawingWithGradientFill_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Aspose.PDF for .NET kullanarak Degrade Dolgulu Çizim Ekleme için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak grafiklerle programlamaya degrade dolgulu bir çizimin nasıl ekleneceğini adım adım açıkladık. Artık bu bilgiyi özel tasarımlar ve degrade dolgular içeren çekici PDF belgeleri oluşturmak için kullanabilirsiniz.

### SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitim, Aspose.PDF for .NET kullanarak grafiklerle programlamaya degrade dolgulu bir çizim ekleme sürecinde size rehberlik etmeyi amaçlamaktadır.

#### S: Başlamadan önce hangi önkoşullar gereklidir?

C: Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ek olarak, C# programlama konusunda temel bir anlayışa sahip olmanız tavsiye edilir.

#### S: PDF dosyasının kaydedileceği dizini nasıl belirlerim?

C: Sağlanan kaynak kodunda, elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkeninin değerini değiştirebilirsiniz.

#### S: Graph nesnesinin amacı nedir?

C: Graph nesnesi çizim elemanları için bir kap görevi görür. Belirtilen boyutlarla oluşturularak sayfanın paragraf koleksiyonuna eklenir.

#### S: Bir şekil için degrade dolguyu nasıl yapılandırabilirim?

C: Degrade dolguyu yapılandırmak için GradientAxialShading sınıfını kullanarak bir şeklin GraphInfo'sunun FillColor özelliğini ayarlayabilirsiniz. Bu, degradenin başlangıç ve bitiş noktalarını ve aralarında geçiş yapılacak renkleri tanımlamanıza olanak tanır.

#### S: Degrade dolgunun renklerini ve yönünü özelleştirebilir miyim?

C: Evet, Renk nesnelerini ayarlayarak ve GradientAxialShading'in başlangıç ve bitiş noktalarını belirterek degrade dolgunun renklerini ve yönünü özelleştirebilirsiniz.

#### S: Eğitimin son adımı nedir?

C: Son adım, ortaya çıkan PDF dosyasını "AddDrawingWithGradientFill_out.pdf" adıyla belirtilen dizine kaydetmeyi içerir.

#### S: Örnek bir kaynak kodu mevcut mu?

C: Evet, öğretici, açıklanan adımları uygulamak için referans olarak kullanabileceğiniz örnek bir kaynak kodu sağlar.

#### S: Dikdörtgenlerin yanı sıra diğer şekillere de degrade dolgu uygulayabilir miyim?

C: Evet, degrade dolguyu diğer şekillere de uygulayabilirsiniz. İşlem, GradientAxialShading sınıfını kullanarak şeklin GraphInfo'sunun FillColor özelliğinin yapılandırılmasını içerir.