---
title: PDF Dosyasında Metin Sayfasını Arayın ve Alın
linktitle: PDF Dosyasında Metin Sayfasını Arayın ve Alın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasındaki belirli bir sayfadaki metni nasıl arayacağınızı ve alacağınızı öğrenin.
type: docs
weight: 430
url: /tr/net/programming-with-text/search-and-get-text-page/
---
Bu eğitimde Aspose.PDF for .NET'in PDF dosyasındaki belirli bir sayfada metin aramak ve almak için nasıl kullanılacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

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
```

## 3. Adım: PDF belgesini yükleyin

 PDF belge dizininizin yolunu ayarlayın ve belgeyi kullanarak yükleyin.`Document` sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Bir sayfadaki metni arayın ve çıkarın

 Oluşturmak`TextFragmentAbsorber`Belirli bir sayfada giriş arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Yer değiştirmek`"Figure"` aramak istediğiniz gerçek metinle birlikte.

## 5. Adım: Belirli bir sayfada arama yapın

Belgenin belirli bir sayfası için emiciyi kabul edin:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Adım 6: Çıkarılan metin parçalarını alın

Çıkarılan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 7. Adım: Metin parçaları ve bölümleri arasında döngü yapın

Alınan metin parçaları ve bunların bölümleri arasında dolaşın ve özelliklerine erişin:

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

Her metin segmentinde daha fazla eylem gerçekleştirmek için döngü içindeki kodu değiştirebilirsiniz.

### Aspose.PDF for .NET kullanarak Arama ve Alma Metin Sayfası için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Tüm sayfalar için emiciyi kabul edin
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü yapın
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinin belirli bir sayfasında nasıl metin arayacağınızı ve metin alacağınızı başarıyla öğrendiniz. Bu eğitimde, belgenin yüklenmesinden çıkarılan metin bölümlerine erişmeye kadar adım adım bir kılavuz sağlanmıştır. Artık dahil edebilirsiniz

### SSS'ler

#### S: "Metin Ara ve Al Sayfası" öğreticisinin amacı nedir?

C: "Metin Ara ve Al Sayfası" eğitimi, bir PDF dosyası içindeki belirli bir sayfadaki metni aramak ve almak için Aspose.PDF kütüphanesinin .NET için nasıl kullanılacağını göstermek üzere tasarlanmıştır. Öğreticide, işlemi göstermek için ayrıntılı talimatlar ve örnek C# kodu sağlanır.

#### S: Bu eğitim, bir PDF belgesindeki belirli bir sayfadan metin çıkarmaya nasıl yardımcı olur?

C: Bu eğitim, Aspose.PDF kütüphanesini kullanarak bir PDF belgesinin belirli bir sayfasından metin çıkarma sürecinde size rehberlik eder. Gerekli adımların ana hatlarını çizer ve seçilen sayfada belirli bir metin ifadesini aramak ve ilişkili metin bölümlerini almak için C# kodunu sağlar.

#### S: Bu eğitimi takip etmenin önkoşulları nelerdir?

C: Bu eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya projenize entegre etmek için NuGet'i kullanabilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Başlamak için tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, projenizde kütüphanenin yeteneklerini kullanmanızı sağlayacaktır.

#### S: PDF belgesinin belirli bir sayfasında metin arayabilir miyim?

C: Evet, bu eğitimde bir PDF belgesinin belirli bir sayfasında nasıl metin aranacağı gösterilmektedir. Şunu kullanmayı içerir:`TextFragmentAbsorber` Seçilen sayfada belirli bir metin ifadesinin örneklerini bulmak için sınıf.

#### S: Belirli bir sayfadan çıkarılan metin bölümlerine nasıl erişirim?

 C: Belirlenen sayfada metni aradıktan sonra, çıkarılan metin bölümlerine`TextSegments` mülkiyeti`TextFragment` nesne. Bu özellik aşağıdakilerin bir koleksiyonuna erişim sağlar:`TextSegment` ayıklanan metni ve ilgili bilgileri içeren nesneler.

#### S: Çıkarılan metin parçalarından hangi bilgileri alabilirim?

C: Çıkarılan metin parçalarından metin içeriği, konum (X ve Y koordinatları), yazı tipi bilgileri (ad, boyut, renk vb.) ve daha fazlası dahil olmak üzere çeşitli ayrıntıları alabilirsiniz. Öğreticinin örnek kodu, her metin bölümü için bu ayrıntılara nasıl erişileceğini ve yazdırılacağını gösterir.

#### S: Çıkarılan metin bölümleri üzerinde özel eylemler gerçekleştirebilir miyim?

C: Kesinlikle. Ayıklanan metin bölümlerini aldıktan sonra, her bölüm üzerinde ek eylemler gerçekleştirmek için döngü içindeki kodu özelleştirebilirsiniz. Bu, çıkarılan metnin kaydedilmesini, metin kalıplarının analiz edilmesini veya biçimlendirme değişikliklerinin uygulanmasını içerebilir.