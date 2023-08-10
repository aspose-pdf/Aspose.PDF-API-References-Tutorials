---
title: Normal İfade Ara
linktitle: Normal İfade Ara
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde düzenli ifadeler kullanarak metin aramayı ve metin almayı öğrenin.
type: docs
weight: 440
url: /tr/net/programming-with-text/search-regular-expression/
---

Bu öğretici, bir PDF belgesindeki normal ifadeyle eşleşen metni aramak ve almak için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, süreci adım adım gösterir.

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

## 3. Adım: PDF belgesini yükleyin

 PDF belge dizininizin yolunu ayarlayın ve belgeyi kullanarak yükleyin.`Document` sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Normal ifadeyle arama yapın

 Oluşturmak`TextFragmentAbsorber` nesne ve kalıpla eşleşen tüm ifadeleri bulmak için normal ifade kalıbını ayarlayın:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 gibi
```

 Yer değiştirmek`"\\d{4}-\\d{4}"` istediğiniz düzenli ifade modeliyle.

## 5. Adım: Metin arama seçeneklerini ayarlayın

 Oluşturmak`TextSearchOptions` nesne ve onu şu şekilde ayarlayın:`TextSearchOptions` mülkiyeti`TextFragmentAbsorber` normal ifade kullanımını etkinleştirmek için nesne:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## 6. Adım: Tüm sayfalarda arama yapın

Belgenin tüm sayfaları için emiciyi kabul edin:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 7. Adım: Ayıklanan metin parçalarını alın

Ayıklanan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 8. Adım: Metin parçaları arasında geçiş yapın

Alınan metin parçaları arasında dolaşın ve özelliklerine erişin:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Her bir metin parçasında başka eylemler gerçekleştirmek için döngü içindeki kodu değiştirebilirsiniz.

### Aspose.PDF for .NET kullanarak Normal İfade Arama için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Normal ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 gibi
// Normal ifade kullanımını belirtmek için metin arama seçeneğini ayarlayın
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Tüm sayfalar için emiciyi kabul edin
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ayıklanan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki normal ifadeyle eşleşen metni nasıl arayacağınızı ve alacağınızı başarıyla öğrendiniz. Bu öğretici, belgeyi yüklemekten çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağladı. Artık PDF dosyalarında gelişmiş metin aramaları yapmak için bu kodu kendi C# projelerinize dahil edebilirsiniz.