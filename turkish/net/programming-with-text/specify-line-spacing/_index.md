---
title: Satır Aralığını Belirtin
linktitle: Satır Aralığını Belirtin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde satır aralığını nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 510
url: /tr/net/programming-with-text/specify-line-spacing/
---

Bu öğretici, Aspose.PDF for .NET kullanılarak bir PDF belgesinde satır aralığının nasıl belirleneceğini açıklar. Sağlanan C# kaynak kodu, süreci adım adım gösterir.

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
using System.IO;
```

## 3. Adım: Belge dizinine giden yolu ayarlayın

 kullanarak belge dizininize giden yolu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Giriş PDF dosyasını yükleyin

 kullanarak giriş PDF dosyasını yükleyin.`Document` sınıf:

```csharp
Document doc = new Document();
```

## 5. Adım: TextFormattingOptions oluşturun

 Oluşturmak`TextFormattingOptions` nesne ve satır aralığı modunu şu şekilde ayarlayın:`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## 6. Adım: Bir TextFragment Oluşturun

 Oluşturmak`TextFragment` nesne ve metin içeriğini belirtin:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## 7. Adım: Yazı tipi dosyasını yükleyin (isteğe bağlı)

 Metin için belirli bir yazı tipi kullanmak istiyorsanız, TrueType yazı tipi dosyasını bir`FileStream` nesne:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Yer değiştirmek`"HPSimplified.TTF"`gerçek yazı tipi dosyası adıyla.

## Adım 8: Metin konumunu ve satır aralığını belirtin

 Metin parçası için konumu ayarlayın ve`TextFormattingOptions` için`TextState.FormattingOptions` mülk:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## 9. Adım: Metni belgeye ekleyin

 Metin parçasını bir belgeye ekleyerek belgeye ekleyin.`TextBuilder` veya doğrudan bir sayfanın`Paragraphs` Toplamak:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## 10. Adım: Ortaya çıkan PDF belgesini kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 değiştirdiğinizden emin olun`"SpecifyLineSpacing_out.pdf"` istenen çıktı dosyası adıyla.

### Aspose.PDF for .NET kullanarak Satır Aralığını Belirtin için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Giriş PDF dosyasını yükle
Document doc = new Document();
//LineSpacingMode.FullSize ile TextFormattingOptions oluşturun
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Belgenin ilk sayfası için metin oluşturucu nesnesi oluştur
//TextBuilder textBuilder = yeni TextBuilder(doc.Pages[1]);
// Örnek dizeyle metin parçası oluştur
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// TrueType yazı tipini akış nesnesine yükleyin
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Metin dizesi için yazı tipi adını ayarlayın
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Metin Parçası için konumu belirtin
		textFragment.Position = new Position(100, 600);
		//Geçerli parçanın TextFormattingOptions öğesini önceden tanımlı olarak ayarlayın (bu, LineSpacingMode.FullSize'a işaret eder)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Metni, PDF dosyasının üzerine yerleştirilebilmesi için TextBuilder'a ekleyin
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Ortaya çıkan PDF belgesini kaydet
	doc.Save(dataDir);
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde satır aralığını nasıl belirteceğinizi başarıyla öğrendiniz. Bu öğretici, projeyi ayarlamaktan değiştirilen belgeyi kaydetmeye kadar adım adım bir kılavuz sağladı. PDF dosyalarındaki metnin satır aralığını özelleştirmek için artık bu kodu kendi C# projelerinize dahil edebilirsiniz.