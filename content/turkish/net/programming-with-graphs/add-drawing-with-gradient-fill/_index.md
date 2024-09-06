---
title: Gradyan Dolgulu Çizim Ekle
linktitle: Gradyan Dolgulu Çizim Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile degrade dolgulu bir çizimin nasıl ekleneceğini öğrenin. Çekici PDF belgeleri oluşturmak için adım adım eğitim.
type: docs
weight: 20
url: /tr/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak grafiklerle programlamaya degrade dolgulu bir çizim eklemek için aşağıdaki C# kaynak kodunu adım adım inceleyeceğiz.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Adım 4: Dikdörtgen Nesnesi Oluşturun ve Grafiğe Ekleyin

Belirtilen ölçülerde bir Dikdörtgen nesnesi oluşturup grafiğin şekil koleksiyonuna ekliyoruz.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Adım 5: Gradyan Dolgusunu Yapılandırma

Dikdörtgen için degrade dolgusunu GradientAxialShading sınıfını kullanarak yapılandırıyoruz.

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

Bu, kırmızıdan maviye, (0, 0) noktasından (300, 300) noktasına doğru bir degrade dolgusu oluşturur.

## Adım 6: PDF Dosyasını Kaydetme

Son olarak ortaya çıkan PDF dosyasını "AddDrawingWithGradientFill_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### .NET için Aspose.PDF kullanarak Gradient Fill ile Çizim Ekleme için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
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

Bu eğitimde, Aspose.PDF for .NET kullanarak grafiklerle programlamaya degrade dolgulu bir çizimin nasıl ekleneceğini adım adım açıkladık. Şimdi bu bilgiyi kullanarak özel tasarımlar ve degrade dolgularla çekici PDF belgeleri oluşturabilirsiniz.

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitimin amacı, Aspose.PDF for .NET kullanarak grafiklerle programlamaya degrade dolgulu bir çizim ekleme sürecinde size rehberlik etmektir.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

A: Başlamadan önce, Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Ek olarak, C# programlama konusunda temel bir anlayışa sahip olmanız önerilir.

#### S: PDF dosyasını kaydedeceğim dizini nasıl belirlerim?

A: Sağlanan kaynak kodunda, "dataDir" değişkeninin değerini, sonuçta elde edilen PDF dosyasını kaydetmek istediğiniz dizini belirtecek şekilde değiştirebilirsiniz.

#### S: Graph nesnesinin amacı nedir?

A: Graph nesnesi çizim öğeleri için bir kapsayıcı görevi görür. Belirtilen boyutlarla oluşturulur ve sayfanın paragraf koleksiyonuna eklenir.

#### S: Bir şekil için degrade dolgusunu nasıl yapılandırabilirim?

A: Gradyan dolgusunu yapılandırmak için, GradientAxialShading sınıfını kullanarak bir şeklin GraphInfo'sunun FillColor özelliğini ayarlayabilirsiniz. Bu, gradyanın başlangıç ve bitiş noktalarını ve aralarında geçiş yapılacak renkleri tanımlamanıza olanak tanır.

#### S: Degrade dolgunun renklerini ve yönünü özelleştirebilir miyim?

C: Evet, Renk nesnelerini ayarlayarak ve GradientAxialShading'in başlangıç ve bitiş noktalarını belirterek degrade dolgusunun renklerini ve yönünü özelleştirebilirsiniz.

#### S: Eğitimin son adımı nedir?

A: Son adım, ortaya çıkan PDF dosyasının "AddDrawingWithGradientFill_out.pdf" adıyla belirtilen dizine kaydedilmesini içerir.

#### S: Örnek kaynak kodu mevcut mu?

C: Evet, eğitimde anlatılan adımları uygulamak için referans olarak kullanabileceğiniz örnek bir kaynak kodu sağlanmaktadır.

#### S: Dikdörtgenlerin dışında diğer şekillere degrade dolgu uygulayabilir miyim?

A: Evet, diğer şekillere de gradyan dolgusu uygulayabilirsiniz. İşlem, GradientAxialShading sınıfını kullanarak şeklin GraphInfo'sunun FillColor özelliğini yapılandırmayı içerir.