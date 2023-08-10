---
title: Metin Segmentleri Sayfasında Ara
linktitle: Metin Segmentleri Sayfasında Ara
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir sayfada metin parçalarını nasıl arayacağınızı ve bunların özelliklerini nasıl alacağınızı öğrenin.
type: docs
weight: 470
url: /tr/net/programming-with-text/search-text-segments-page/
---

Bu eğitim, Aspose.PDF for .NET'in bir PDF belgesinin bir sayfasındaki belirli metin bölümlerini aramak ve bunların özelliklerini almak için nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, süreci adım adım gösterir.

## Önkoşullar

Öğreticiye devam etmeden önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Aspose.PDF for .NET kitaplığı yüklendi. Aspose web sitesinden edinebilir veya projenize yüklemek için NuGet'i kullanabilirsiniz.

## 1. Adım: Projeyi kurun

Tercih ettiğiniz tümleşik geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinine giden yolu ayarlayın

 kullanarak belge dizininize giden yolu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: PDF belgesini yükleyin

 kullanarak PDF belgesini yükleyin.`Document` sınıf:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Yer değiştirmek`"SearchTextSegmentsPage.pdf"` PDF dosyanızın gerçek adıyla.

## 5. Adım: Bir TextFragmentAbsorber Oluşturun

 Oluşturmak`TextFragmentAbsorber` girdi arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Yer değiştirmek`"text"` istediğiniz arama ifadesi ile.

## 6. Adım: Emiciyi belirli bir sayfa için kabul edin

Dokümanın istenen sayfası için emiciyi kabul edin:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Yer değiştirmek`2` istenen sayfa numarasıyla (1 tabanlı dizin).

## 7. Adım: Ayıklanan metin parçalarını alın

 Ayıklanan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 8. Adım: Metin bölümleri arasında geçiş yapın

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

Gerekirse her bir metin parçasında başka eylemler gerçekleştirmek için döngü içindeki kodu değiştirin.

### Aspose.PDF for .NET kullanarak Metin Segmentlerini Ara Sayfası için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
//Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Tüm sayfalar için emiciyi kabul edin
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Ayıklanan metin parçalarını alın
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin bir sayfasında belirli metin bölümlerinin nasıl aranacağını başarıyla öğrendiniz. Bu öğretici, belgeyi yüklemekten çıkarılan metin bölümlerine erişmeye kadar adım adım bir kılavuz sağladı. PDF dosyalarında gelişmiş metin segmenti aramaları yapmak için artık bu kodu kendi C# projelerinize dahil edebilirsiniz.