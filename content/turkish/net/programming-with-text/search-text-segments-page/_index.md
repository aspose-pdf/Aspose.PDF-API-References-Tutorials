---
title: PDF Dosyasında Metin Segmentleri Sayfasını Ara
linktitle: PDF Dosyasında Metin Segmentleri Sayfasını Ara
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasındaki bir sayfada metin bölümlerini nasıl arayacağınızı ve bunların özelliklerini nasıl alacağınızı öğrenin.
type: docs
weight: 470
url: /tr/net/programming-with-text/search-text-segments-page/
---
Bu eğitimde Aspose.PDF for .NET'in, PDF dosyasının bir sayfasındaki belirli metin bölümlerini aramak ve bunların özelliklerini almak için nasıl kullanılacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

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

## 3. Adım: Belge dizininin yolunu ayarlayın

 kullanarak belge dizininizin yolunu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: PDF belgesini yükleyin

 PDF belgesini kullanarak yükleyin`Document` sınıf:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Yer değiştirmek`"SearchTextSegmentsPage.pdf"` PDF dosyanızın gerçek adıyla.

## Adım 5: TextFragmentAbsorber oluşturun

 Oluşturmak`TextFragmentAbsorber` giriş arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Yer değiştirmek`"text"` İstediğiniz arama ifadesiyle.

## 6. Adım: Belirli bir sayfa için emiciyi kabul edin

Belgenin istenen sayfası için emiciyi kabul edin:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Yer değiştirmek`2` İstenilen sayfa numarasıyla (1 tabanlı dizin).

## 7. Adım: Çıkarılan metin bölümlerini alın

 Çıkarılan metin bölümlerini kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 8. Adım: Metin bölümleri arasında döngü yapın

Alınan metin bölümleri arasında dolaşın ve özelliklerine erişin:

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

Gerekirse her metin bölümünde daha fazla eylem gerçekleştirmek için döngü içindeki kodu değiştirin.

### Aspose.PDF for .NET kullanarak Metin Segmentlerini Arama Sayfası için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Tüm sayfalar için emiciyi kabul edin
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü yapın
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinin sayfasında belirli metin bölümlerini nasıl arayacağınızı başarıyla öğrendiniz. Bu eğitimde, belgenin yüklenmesinden çıkarılan metin bölümlerine erişmeye kadar adım adım bir kılavuz sağlanmıştır. Artık PDF dosyalarında gelişmiş metin segmenti aramaları gerçekleştirmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasında Metin Segmentleri Sayfasında Arama" öğreticisinin amacı nedir?

C: "PDF Dosyasında Metin Segmentleri Sayfasını Ara" eğitimi, bir PDF belgesinin belirli bir sayfasında belirli metin segmentlerini aramak için .NET için Aspose.PDF kütüphanesinin nasıl kullanılacağı hakkında kapsamlı bir kılavuz sağlar. Bir proje oluşturma, bir PDF belgesi yükleme, metin bölümlerini arama ve C# kodunu kullanarak bunların özelliklerini alma sürecini kapsar.

#### S: Bu eğitim, bir PDF belgesinde belirli metin bölümlerini aramaya nasıl yardımcı olur?

C: Bu eğitimde, bir PDF belgesinin belirli bir sayfasındaki belirli metin bölümlerini bulma ve çıkarma işlemi gösterilmektedir. Kullanıcılar sağlanan adımları ve kod örneklerini takip ederek istenen metin bölümlerini etkili bir şekilde arayabilir ve bunların özellikleri hakkında bilgi alabilir.

#### S: Bu öğreticiyi takip etmek için hangi ön koşullar gereklidir?

C: Eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet'i kullanarak projenize yükleyebilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Başlamak için tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, kitaplığın PDF belgelerini arama ve bunlarla çalışma özelliklerini kullanmanızı sağlayacaktır.

#### S: Bu öğreticiyi bir PDF'nin herhangi bir sayfasındaki belirli metin bölümlerini aramak için kullanabilir miyim?

C: Evet, bu eğitimde bir PDF belgesinin seçilen sayfasında belirli metin bölümlerinin nasıl aranacağıyla ilgili talimatlar verilmektedir. Kullanıcılara bir proje kurma, PDF yükleme ve Aspose.PDF kütüphanesini kullanarak istenen metin bölümlerinin özelliklerini bulup alma konusunda rehberlik eder.

#### S: Bu eğitimde aramak istediğim metni nasıl belirtebilirim?

 C: Aramak istediğiniz metni belirtmek için bir`TextFragmentAbsorber` kullanarak nesneyi seçin ve arama parametresini ayarlayın.`Text` mülk. Varsayılanı değiştir`"text"` öğreticinin kodunda istediğiniz arama ifadesini girin.

#### S: Çıkarılan metin bölümlerinin özelliklerini nasıl alabilirim?

Kabul ettikten sonra`TextFragmentAbsorber` PDF'nin belirli bir sayfası için, çıkarılan metin bölümlerini kullanarak`TextFragments` soğurucu nesnenin özelliği. Bu, her biri birden fazla metin parçası içeren bir metin parçaları koleksiyonuna erişim sağlar.

#### S: Kodu, her metin bölümünde ek eylemler gerçekleştirecek şekilde özelleştirebilir miyim?

C: Kesinlikle. Öğreticinin örnek kodu, alınan metin bölümlerinin yinelenmesi için bir döngü sağlar. Proje gereksinimlerinize göre her metin segmentinde ek eylemler gerçekleştirmek için bu döngü içindeki kodu özelleştirebilirsiniz.

#### S: Metin bölümlerini çıkardıktan sonra değiştirilen PDF belgesini nasıl kaydedebilirim?

C: Bu eğitim öncelikle metin bölümlerini aramaya ve bunların özelliklerini almaya odaklanıyor. PDF'de değişiklik yapmayı düşünüyorsanız, belgeyi özel ihtiyaçlarınıza göre nasıl değiştireceğinizi ve kaydedeceğinizi öğrenmek için diğer Aspose.PDF belgelerine başvurabilirsiniz.