---
title: Gradyan Dolgulu Çizim Ekle
linktitle: Gradyan Dolgulu Çizim Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile degrade dolgulu bir çizimi nasıl ekleyeceğinizi öğrenin. Çekici PDF belgeleri oluşturmak için adım adım öğretici.
type: docs
weight: 20
url: /tr/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak grafiklerle programlamaya degrade dolgulu bir çizim eklemek için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Adım 4: Dikdörtgen Nesnesi Oluşturun ve Grafiğe Ekleyin

Belirtilen boyutlara sahip bir Dikdörtgen nesnesi oluşturuyoruz ve onu grafiğin şekil koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Adım 5: Degrade Dolguyu Yapılandırma

GradientAxialShading sınıfını kullanarak dikdörtgen için degrade dolguyu yapılandırıyoruz.

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

## 6. Adım: PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "AddDrawingWithGradientFill_out.pdf" adıyla belirtilen dizine kaydediyoruz.

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

Bu eğitimde, Aspose.PDF for .NET kullanarak grafiklerle programlamaya degrade dolgulu bir çizimin nasıl ekleneceğini adım adım açıkladık. Artık bu bilgiyi, özel tasarımlara ve degrade dolgulara sahip çekici PDF belgeleri oluşturmak için kullanabilirsiniz.

### SSS

#### S: Bu eğitimin amacı nedir?

C: Bu eğitim, Aspose.PDF for .NET kullanarak grafiklerle programlamaya degrade dolgulu bir çizim ekleme sürecinde size rehberlik etmeyi amaçlamaktadır.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

C: Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ek olarak, temel bir C# programlama anlayışına sahip olunması önerilir.

#### S: PDF dosyasının kaydedileceği dizini nasıl belirleyebilirim?

Y: Sağlanan kaynak kodunda, elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkeninin değerini değiştirebilirsiniz.

#### S: Grafik nesnesinin amacı nedir?

C: Grafik nesnesi, çizim öğeleri için bir kap görevi görür. Belirtilen boyutlarda oluşturulur ve sayfanın paragraf koleksiyonuna eklenir.

#### S: Bir şekil için degrade dolguyu nasıl yapılandırabilirim?

C: Degrade dolguyu yapılandırmak için GradientAxialShading sınıfını kullanarak bir şeklin GraphInfo özelliğinin FillColor özelliğini ayarlayabilirsiniz. Bu, degradenin başlangıç ve bitiş noktalarını ve aralarında geçiş yapılacak renkleri tanımlamanıza olanak tanır.

#### S: Degrade dolgunun renklerini ve yönünü özelleştirebilir miyim?

C: Evet, Color nesnelerini ayarlayarak ve GradientAxialShading'in başlangıç ve bitiş noktalarını belirleyerek degrade dolgunun renklerini ve yönünü özelleştirebilirsiniz.

#### S: Eğitimin son adımı nedir?

C: Son adım, ortaya çıkan PDF dosyasını "AddDrawingWithGradientFill_out.pdf" adıyla belirtilen dizine kaydetmeyi içerir.

#### S: Örnek bir kaynak kodu var mı?

Y: Evet, öğretici, açıklanan adımları uygulamak için referans olarak kullanabileceğiniz örnek bir kaynak kodu sağlar.

#### S: Degrade dolguyu dikdörtgenlerin yanı sıra başka şekillere de uygulayabilir miyim?

C: Evet, diğer şekillere de degrade dolgu uygulayabilirsiniz. İşlem, GradientAxialShading sınıfını kullanarak şeklin GraphInfo özelliğinin FillColor özelliğini yapılandırmayı içerir.