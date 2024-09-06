---
title: PDF Dosyasında Metin Segmentleri Sayfasını Ara
linktitle: PDF Dosyasında Metin Segmentleri Sayfasını Ara
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasında bir sayfadaki metin parçalarını nasıl arayacağınızı ve özelliklerini nasıl alacağınızı öğrenin.
type: docs
weight: 470
url: /tr/net/programming-with-text/search-text-segments-page/
---
Bu eğitim, PDF dosyasının bir sayfasındaki belirli metin bölümlerini aramak ve özelliklerini almak için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

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
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Yer değiştirmek`"SearchTextSegmentsPage.pdf"` PDF dosyanızın gerçek adıyla.

## Adım 5: Bir TextFragmentAbsorber Oluşturun

 Bir tane oluştur`TextFragmentAbsorber` Giriş arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Yer değiştirmek`"text"` İstediğiniz arama ifadesiyle.

## Adım 6: Belirli bir sayfa için emiciyi kabul edin

Belgenin istenilen sayfası için emiciyi kabul edin:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Yer değiştirmek`2` İstenilen sayfa numarasıyla (1 tabanlı dizin).

## Adım 7: Çıkarılan metin parçalarını alın

 Çıkarılan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Adım 8: Metin bölümleri arasında döngü oluşturun

Alınan metin parçaları arasında dolaşın ve özelliklerine erişin:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Gerekirse her metin parçasında daha fazla işlem gerçekleştirmek için döngü içindeki kodu değiştirin.

### .NET için Aspose.PDF kullanarak Arama Metni Segmentleri Sayfası için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Tüm sayfalar için emiciyi kabul et
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin bir sayfasında belirli metin parçalarını aramayı başarıyla öğrendiniz. Bu eğitim, belgeyi yüklemekten çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu kendi C# projelerinize dahil ederek PDF dosyalarında gelişmiş metin parçası aramaları yapabilirsiniz.

### SSS

#### S: "PDF Dosyasında Metin Segmentleri Sayfasını Arama" eğitiminin amacı nedir?

A: "PDF Dosyasında Metin Segmentleri Sayfasını Ara" öğreticisi, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesinin belirli bir sayfasındaki belirli metin segmentlerini nasıl arayacağınıza dair kapsamlı bir kılavuz sunar. Bir proje kurma, bir PDF belgesi yükleme, metin segmentlerini arama ve C# kodu kullanarak özelliklerini alma sürecini kapsar.

#### S: Bu eğitim PDF belgesinde belirli metin parçalarını aramada nasıl yardımcı oluyor?

A: Bu eğitim, bir PDF belgesinin belirli bir sayfasındaki belirli metin parçalarını bulma ve çıkarma sürecini gösterir. Sağlanan adımları ve kod örneklerini izleyerek, kullanıcılar istenen metin parçalarını etkili bir şekilde arayabilir ve özellikleri hakkında bilgi alabilir.

#### S: Bu eğitimi takip etmek için hangi ön koşullar gereklidir?

A: Eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet kullanarak projenize yükleyebilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Başlamak için, tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Bu, PDF belgelerini aramak ve bunlarla çalışmak için kitaplığın özelliklerini kullanmanızı sağlayacaktır.

#### S: Bu eğitimi kullanarak PDF'in herhangi bir sayfasındaki belirli metin bölümlerini arayabilir miyim?

C: Evet, bu eğitim, bir PDF belgesinin seçili bir sayfasında belirli metin segmentlerinin nasıl aranacağına dair talimatlar sağlar. Kullanıcılara bir proje kurma, bir PDF yükleme ve istenen metin segmentlerinin özelliklerini bulmak ve almak için Aspose.PDF kitaplığını kullanma konusunda rehberlik eder.

#### S: Bu eğitimde aramak istediğim metni nasıl belirleyebilirim?

 A: Aramak istediğiniz metni belirtmek için bir`TextFragmentAbsorber` nesneyi seçin ve arama parametresini kullanarak ayarlayın`Text` özellik. Varsayılanı değiştirin`"text"` İstediğiniz arama ifadesiyle eğitimin koduna yazın.

#### S: Çıkarılan metin parçalarının özelliklerini nasıl alabilirim?

Kabul ettikten sonra`TextFragmentAbsorber` PDF'nin belirli bir sayfası için, çıkarılan metin parçalarını kullanarak alabilirsiniz`TextFragments` emici nesnenin özelliği. Bu, her biri birden fazla metin parçası içeren bir metin parçaları koleksiyonuna erişim sağlar.

#### S: Her metin parçasında ek eylemler gerçekleştirmek için kodu özelleştirebilir miyim?

A: Kesinlikle. Eğitimin örnek kodu, alınan metin segmentleri arasında yineleme yapmak için bir döngü sağlar. Projenizin gereksinimlerine göre, her metin segmentinde ek eylemler gerçekleştirmek için bu döngü içindeki kodu özelleştirebilirsiniz.

#### S: Metin parçalarını çıkardıktan sonra değiştirilen PDF belgesini nasıl kaydederim?

A: Bu eğitim öncelikli olarak metin parçalarını aramaya ve özelliklerini almaya odaklanır. PDF'de değişiklik yapmayı düşünüyorsanız, belgeyi özel ihtiyaçlarınıza göre nasıl düzenleyip kaydedeceğinizi öğrenmek için diğer Aspose.PDF belgelerine başvurabilirsiniz.