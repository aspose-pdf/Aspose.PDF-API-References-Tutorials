---
title: Metin Ara ve Dikdörtgen Çiz
linktitle: Metin Ara ve Dikdörtgen Çiz
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'i kullanarak PDF'te metin aramayı, bulunan metnin etrafına dikdörtgenler çizmeyi ve değiştirilmiş belgeyi kaydetmeyi öğrenin.
type: docs
weight: 460
url: /tr/net/programming-with-text/search-text-and-draw-rectangle/
---
Bu eğitim, bir PDF belgesinde belirli bir metni aramak, bulunan metnin etrafına bir dikdörtgen çizmek ve değiştirilmiş belgeyi kaydetmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

## Ön koşullar

Eğitime başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi.
- .NET kütüphanesi için Aspose.PDF yüklendi. Bunu Aspose web sitesinden edinebilir veya projenize yüklemek için NuGet'i kullanabilirsiniz.

## Adım 1: Projeyi kurun

Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve .NET için Aspose.PDF kitaplığına bir başvuru ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Adım 3: Belge dizinine giden yolu ayarlayın

 Belge dizininize giden yolu kullanarak ayarlayın`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: PDF belgesini yükleyin

 PDF belgesini kullanarak yükleyin`Document` sınıf:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Yer değiştirmek`"SearchAndGetTextFromAll.pdf"` PDF dosyanızın gerçek adıyla.

## Adım 5: Bir TextFragmentAbsorber Oluşturun

 Bir tane oluştur`TextFragmentAbsorber` Giriş arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Yer değiştirmek`@"[\S]+"` İstediğiniz düzenli ifade kalıbıyla.

## Adım 6: Düzenli ifade aramasını etkinleştirin

 Düzenli ifade aramasını etkinleştirmek için şu ayarı yapın:`TextSearchOptions` emicinin özelliği:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Adım 7: Tüm sayfalarda arama yapın

Belgenin tüm sayfaları için emiciyi kabul edin:

```csharp
document.Pages.Accept(textAbsorber);
```

## Adım 8: Bulunan metnin etrafına bir dikdörtgen çizin

 Bir tane oluştur`PdfContentEditor` nesne ve döngü, alınan metin parçaları arasında dolaşarak her metin parçasının etrafına bir dikdörtgen çizer:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Adım 9: Değiştirilen belgeyi kaydedin

Değiştirilen belgeyi kaydedin:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Değiştirdiğinizden emin olun`"SearchTextAndDrawRectangle_out.pdf"` İstenilen çıktı dosya adı ile.

### .NET için Aspose.PDF kullanarak Arama Metni ve Çizim Dikdörtgeni için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Düzenli ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Bir PDF belgesinde belirli bir metni aramayı, bulunan metnin etrafına bir dikdörtgen çizmeyi ve değiştirilmiş belgeyi Aspose.PDF for .NET kullanarak kaydetmeyi başarıyla öğrendiniz. Bu eğitim, projeyi kurmaktan gerekli eylemleri gerçekleştirmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu kendi C# projelerinize dahil ederek metni düzenleyebilir ve PDF dosyalarında dikdörtgenler çizebilirsiniz.

### SSS

#### S: "Metin Ara ve Dikdörtgen Çiz" eğitiminin amacı nedir?

A: "Metin Ara ve Dikdörtgen Çiz" öğreticisinin amacı, kullanıcıları .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesi içinde belirli bir metni arama, bulunan metin parçalarının etrafına dikdörtgenler çizme ve değiştirilmiş belgeyi kaydetme sürecinde yönlendirmektir. Öğretici, sürecin her adımını göstermek için ayrıntılı talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim, bir PDF belgesinde belirli bir metnin etrafına dikdörtgen çizmeye nasıl yardımcı olur?

A: Bu eğitim, bir PDF belgesindeki belirli metin parçalarının etrafına dikdörtgenler yerleştirme ve çizme konusunda kapsamlı bir kılavuz sunar. Bir proje kurma, bir PDF belgesi yükleme, düzenli ifade aramasını etkinleştirme, bulunan metin parçalarının etrafına dikdörtgenler çizme ve değiştirilmiş PDF'yi kaydetme sürecini gösterir.

#### S: Bu eğitimi takip etmek için hangi ön koşullar gereklidir?

A: Eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet kullanarak projenize yükleyebilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın. Ardından, projenize Aspose.PDF for .NET kitaplığına bir referans ekleyin. Bu, PDF belgelerini düzenlemek için kitaplığın işlevselliğini kullanmanızı sağlayacaktır.

#### S: Bu eğitimi kullanarak belirli bir metnin etrafına dikdörtgenler çizebilir miyim?

C: Evet, eğitim bir PDF belgesindeki belirli metin bölümlerinin etrafına dikdörtgenler çizmeye odaklanır. Düzenli ifadeler kullanarak istenen metni nasıl bulacağınızı, tanımlanan metin bölümlerinin etrafına dikdörtgenler nasıl oluşturacağınızı ve değiştirilmiş PDF'i nasıl kaydedeceğinizi gösterir.

#### S: Aramak istediğim metni nasıl belirleyebilirim ve etrafına dikdörtgenler nasıl çizebilirim?

 A: Aramak istediğiniz metni belirtmek ve etrafına dikdörtgenler çizmek için bir`TextFragmentAbsorber` nesneyi seçin ve desenini kullanarak ayarlayın`Text` parametre. Varsayılan deseni değiştir`@"[\S]+"` İstediğiniz düzenli ifade kalıbını kullanarak eğitimin koduna yazın.

#### S: Metin için düzenli ifade aramasını nasıl etkinleştiririm?

 A: Düzenli ifade araması, bir`TextSearchOptions` nesne ve değerini ayarlama`true` Bu nesneyi şuraya atayın:`TextSearchOptions` mülkiyeti`TextFragmentAbsorber` örnek. Bu, metin araması sırasında düzenli ifade deseninin kullanılmasını sağlar.

#### S: Bulunan metnin etrafına nasıl dikdörtgen çizebilirim?

 A: Metin bölümlerini kullanarak tanımladıktan sonra`TextFragmentAbsorber` , öğretici bu segmentler arasında yineleme yapmak için bir döngü sağlar. Her metin segmenti için öğretici, bunun etrafında bir dikdörtgenin nasıl oluşturulacağını gösterir.`DrawBox` yöntemini kullanın ve dikdörtgenin görünümünü belirtin.

#### S: Çizilmiş dikdörtgenlerle düzenlenmiş PDF'i kaydetmek için hangi adımlar izlenmelidir?

A: İstenilen metin parçalarının etrafına dikdörtgenler çizdikten sonra,`Document` sınıfın`Save` Değiştirilen belgeyi kaydetme yöntemi. Eğitimin örnek kodu, düzenlenen PDF'nin nasıl kaydedileceğini ve bir başarı mesajının nasıl görüntüleneceğini gösterir.

#### S: Çizilen dikdörtgenlerin görünümünü özelleştirebilir miyim?

 A: Evet, çizilen dikdörtgenlerin görünümünü özelleştirebilirsiniz. Eğitimin örnek kodunda,`DrawBox` yöntemi dikdörtgenler oluşturmak için kullanılır. Çizilen dikdörtgenlerin görünümünü özelleştirmek için renk, stil ve kalınlık gibi özellikleri değiştirebilirsiniz.