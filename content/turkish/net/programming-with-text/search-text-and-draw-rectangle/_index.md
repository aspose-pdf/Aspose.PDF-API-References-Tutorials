---
title: Metin Ara ve Dikdörtgen Çiz
linktitle: Metin Ara ve Dikdörtgen Çiz
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF'de metin aramayı, bulunan metnin etrafına dikdörtgenler çizmeyi ve değiştirilen belgeyi kaydetmeyi öğrenin.
type: docs
weight: 460
url: /tr/net/programming-with-text/search-text-and-draw-rectangle/
---
Bu eğitimde, bir PDF belgesinde belirli bir metni aramak, bulunan metnin etrafına bir dikdörtgen çizmek ve değiştirilen belgeyi kaydetmek için Aspose.PDF for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

## Önkoşullar

Eğiticiye devam etmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- Temel C# programlama dili bilgisi.
- Aspose.PDF for .NET kütüphanesi kuruldu. Bunu Aspose web sitesinden edinebilir veya projenize kurmak için NuGet'i kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın

Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## 3. Adım: Belge dizininin yolunu ayarlayın

 kullanarak belge dizininizin yolunu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: PDF belgesini yükleyin

 PDF belgesini kullanarak yükleyin`Document` sınıf:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Yer değiştirmek`"SearchAndGetTextFromAll.pdf"` PDF dosyanızın gerçek adıyla.

## Adım 5: TextFragmentAbsorber oluşturun

 Oluşturmak`TextFragmentAbsorber` giriş arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Yer değiştirmek`@"[\S]+"` İstediğiniz düzenli ifade modeliyle.

## 6. Adım: Normal ifade aramasını etkinleştirin

 Ayarlayarak normal ifade aramasını etkinleştirin`TextSearchOptions` emicinin özelliği:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## 7. Adım: Tüm sayfalarda arama yapın

Belgenin tüm sayfaları için emiciyi kabul edin:

```csharp
document.Pages.Accept(textAbsorber);
```

## Adım 8: Bulunan metnin etrafına bir dikdörtgen çizin

 Oluşturmak`PdfContentEditor` her metin bölümünün etrafına bir dikdörtgen çizerek, alınan metin parçaları arasında nesne oluşturun ve döngü yapın:

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

## 9. Adım: Değiştirilen belgeyi kaydedin

Değiştirilen belgeyi kaydedin:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Değiştirdiğinizden emin olun`"SearchTextAndDrawRectangle_out.pdf"` İstenilen çıktı dosyası adı ile.

### Aspose.PDF for .NET kullanarak Metin Arama ve Dikdörtgen Çizme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Normal ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinde belirli bir metni nasıl arayacağınızı, bulunan metnin etrafına bir dikdörtgen çizmeyi ve değiştirilen belgeyi nasıl kaydedeceğinizi başarıyla öğrendiniz. Bu eğitimde, projenin kurulumundan gerekli eylemlerin gerçekleştirilmesine kadar adım adım bir kılavuz sağlanmıştır. Artık metni değiştirmek ve PDF dosyalarında dikdörtgenler çizmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "Metin Arama ve Dikdörtgen Çizme" eğitiminin amacı nedir?

C: "Metin Arama ve Dikdörtgen Çizme" eğitimi, kullanıcılara Aspose.PDF kütüphanesini .NET kullanarak bir PDF belgesinde belirli bir metni arama, bulunan metin bölümlerinin etrafına dikdörtgenler çizme ve değiştirilenleri kaydetme sürecinde rehberlik etmeyi amaçlamaktadır. belge. Öğretici, sürecin her adımını göstermek için ayrıntılı talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim, bir PDF belgesindeki belirli bir metnin etrafına dikdörtgenler çizmeye nasıl yardımcı olur?

C: Bu eğitim, bir PDF belgesindeki belirli metin bölümlerinin etrafındaki dikdörtgenlerin nasıl bulunacağı ve çizileceği konusunda kapsamlı bir kılavuz sağlar. Bir proje oluşturma, bir PDF belgesi yükleme, normal ifade aramasını etkinleştirme, bulunan metin bölümlerinin etrafına dikdörtgenler çizme ve değiştirilen PDF'yi kaydetme sürecini gösterir.

#### S: Bu öğreticiyi takip etmek için hangi ön koşullar gereklidir?

C: Eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet'i kullanarak projenize yükleyebilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Tercih ettiğiniz tümleşik geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın. Ardından projenize Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, PDF belgelerini düzenlemek için kitaplığın işlevselliğini kullanmanızı sağlayacaktır.

#### S: Bu öğreticiyi kullanarak belirli bir metnin etrafına dikdörtgenler çizebilir miyim?

C: Evet, eğitim, bir PDF belgesindeki belirli metin bölümlerinin etrafına dikdörtgenler çizmeye odaklanıyor. Düzenli ifadeler kullanarak istenen metnin nasıl bulunacağını, tanımlanan metin bölümlerinin etrafında dikdörtgenlerin nasıl oluşturulacağını ve değiştirilen PDF'nin nasıl kaydedileceğini gösterir.

#### S: Aramak istediğim metni nasıl belirleyebilirim ve etrafına dikdörtgenler çizebilirim?

 C: Aramak istediğiniz metni belirtmek ve etrafına dikdörtgenler çizmek için bir`TextFragmentAbsorber` kullanarak nesneyi seçin ve desenini ayarlayın.`Text` parametre. Varsayılan deseni değiştir`@"[\S]+"` öğreticinin kodunda istediğiniz normal ifade düzeniyle.

#### S: Metin için normal ifade aramasını nasıl etkinleştiririm?

 C: Normal ifade araması, bir`TextSearchOptions` nesne ve değerini ayarlama`true` . Bu nesneyi şuraya atayın:`TextSearchOptions` mülkiyeti`TextFragmentAbsorber` misal. Bu, metin araması sırasında normal ifade modelinin kullanılmasını sağlar.

#### S: Bulunan metnin etrafına nasıl dikdörtgenler çizebilirim?

 C: Metin parçalarını tanımladıktan sonra`TextFragmentAbsorber` , öğretici bu segmentler arasında yineleme yapmak için bir döngü sağlar. Eğitimde, her metin bölümü için, metin bölümünün etrafında, aşağıdakileri kullanarak nasıl bir dikdörtgen oluşturulacağı gösterilmektedir:`DrawBox` yöntemini seçin ve dikdörtgenin görünümünü belirtin.

#### S: Değiştirilen PDF'yi çizilmiş dikdörtgenlerle kaydetme adımları nelerdir?

C: İstediğiniz metin bölümlerinin çevresine dikdörtgenler çizdikten sonra`Document` sınıfın`Save` Değiştirilen belgeyi kaydetme yöntemi. Eğitimin örnek kodu, düzenlenen PDF'nin nasıl kaydedileceğini ve bir başarı mesajının nasıl görüntüleneceğini gösterir.

#### S: Çizilen dikdörtgenlerin görünümünü özelleştirebilir miyim?

 C: Evet, çizilen dikdörtgenlerin görünümünü özelleştirebilirsiniz. Öğreticinin örnek kodunda,`DrawBox` Dikdörtgen oluşturmak için yöntem kullanılır. Çizilen dikdörtgenlerin görünümünü özelleştirmek için renk, stil ve kalınlık gibi özellikleri değiştirebilirsiniz.