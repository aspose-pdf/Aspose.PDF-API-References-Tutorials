---
title: PDF Dosyasında Metin Sayfasını Ara ve Al
linktitle: PDF Dosyasında Metin Sayfasını Ara ve Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki belirli bir sayfadaki metni nasıl arayacağınızı ve alacağınızı öğrenin.
type: docs
weight: 430
url: /tr/net/programming-with-text/search-and-get-text-page/
---
Bu eğitim, PDF dosyasındaki belirli bir sayfadan metin aramak ve almak için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

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

## Adım 3: PDF belgesini yükleyin

 PDF belge dizininize giden yolu ayarlayın ve belgeyi kullanarak yükleyin`Document` sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: Bir sayfadan metin arayın ve çıkarın

 Bir tane oluştur`TextFragmentAbsorber`Belirli bir sayfadaki girdi arama ifadesinin tüm örneklerini bulma nesnesi:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Yer değiştirmek`"Figure"` Aramak istediğiniz gerçek metinle birlikte.

## Adım 5: Belirli bir sayfada arama yapın

Belgenin belirli bir sayfası için emiciyi kabul edin:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Adım 6: Çıkarılan metin parçalarını alın

Çıkarılan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Adım 7: Metin parçaları ve segmentleri arasında döngü oluşturun

getd metin parçaları ve bunların bölümleri arasında dolaşın ve bunların özelliklerine erişin:

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

Döngü içindeki kodu, her metin parçası üzerinde daha fazla işlem gerçekleştirecek şekilde değiştirebilirsiniz.

### .NET için Aspose.PDF kullanarak Arama ve Metin Alma Sayfası için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Tüm sayfalar için emiciyi kabul et
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin belirli bir sayfasından metin aramayı ve almayı başarıyla öğrendiniz. Bu eğitim, belgeyi yüklemekten çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağladı. Artık şunları dahil edebilirsiniz:

### SSS

#### S: "Metin Arama ve Alma Sayfası" eğitiminin amacı nedir?

A: "Metin Arama ve Alma Sayfası" öğreticisi, .NET için Aspose.PDF kütüphanesinin PDF dosyasındaki belirli bir sayfadan metin aramak ve almak için nasıl kullanılacağını göstermek için tasarlanmıştır. Öğretici, işlemi göstermek için ayrıntılı talimatlar ve örnek C# kodu sağlar.

#### S: Bu eğitim PDF belgesindeki belirli bir sayfadan metin çıkarmada nasıl yardımcı olur?

A: Bu eğitim, Aspose.PDF kütüphanesini kullanarak bir PDF belgesinin belirli bir sayfasından metin çıkarma sürecinde size rehberlik eder. Gerekli adımları özetler ve seçili sayfada belirtilen bir metin ifadesini aramak ve ilişkili metin bölümlerini almak için C# kodu sağlar.

#### S: Bu eğitimi takip etmek için ön koşullar nelerdir?

A: Bu eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya projenize entegre etmek için NuGet'i kullanabilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Başlamak için, tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve .NET için Aspose.PDF kitaplığına bir referans ekleyin. Bu, kitaplığın yeteneklerini projenizde kullanmanızı sağlayacaktır.

#### S: PDF belgesinin belirli bir sayfasında metin arayabilir miyim?

A: Evet, bu eğitim, bir PDF belgesinin belirli bir sayfasında metin aramanın nasıl yapılacağını gösterir.`TextFragmentAbsorber` Seçilen sayfada belirli bir metin ifadesinin örneklerini bulmak için kullanılan sınıf.

#### S: Belirli sayfadan çıkarılan metin parçalarına nasıl ulaşabilirim?

 A: Belirtilen sayfada metni aradıktan sonra, çıkarılan metin parçalarına şu şekilde ulaşabilirsiniz:`TextSegments` mülkiyeti`TextFragment` nesne. Bu özellik, bir koleksiyona erişim sağlar`TextSegment` Çıkarılan metni ve ilgili bilgileri içeren nesneler.

#### S: Çıkarılan metin parçalarından hangi bilgileri alabilirim?

A: Çıkarılan metin parçalarından metin içeriği, konum (X ve Y koordinatları), yazı tipi bilgileri (ad, boyut, renk vb.) ve daha fazlası dahil olmak üzere çeşitli ayrıntıları alabilirsiniz. Eğitimin örnek kodu, her metin parçası için bu ayrıntılara nasıl erişileceğini ve yazdırılacağını gösterir.

#### S: Çıkarılan metin parçaları üzerinde özel eylemler gerçekleştirebilir miyim?

A: Elbette. Çıkarılan metin segmentlerine sahip olduğunuzda, her segmentte ek eylemler gerçekleştirmek için döngü içindeki kodu özelleştirebilirsiniz. Bu, çıkarılan metni kaydetmeyi, metin desenlerini analiz etmeyi veya biçimlendirme değişiklikleri uygulamayı içerebilir.