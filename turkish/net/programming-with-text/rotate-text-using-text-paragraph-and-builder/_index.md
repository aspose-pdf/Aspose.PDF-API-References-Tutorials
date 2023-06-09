---
title: Metin Paragrafını ve Oluşturucuyu Kullanarak Metni Döndürme
linktitle: Metin Paragrafını ve Oluşturucuyu Kullanarak Metni Döndürme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde metin paragrafı ve oluşturucu kullanarak metni döndürmeyi öğrenin.
type: docs
weight: 410
url: /tr/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---

Bu eğitim, metin paragrafları ve oluşturucular kullanarak metni döndürmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, süreci adım adım gösterir.

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
using Aspose.Pdf.Text.TextBuilder;
```

## 3. Adım: PDF belgesini oluşturun

 Başlat`Document` yeni bir PDF belgesi oluşturmak için nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Bir sayfa ekleyin

 kullanarak belgeden belirli bir sayfa alın`Pages.Add()` yöntem:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 5. Adım: Metin paragrafları oluşturun ve döndürün

 Oluşturmak`for` farklı dönüşlere sahip birden fazla metin paragrafı oluşturmak için döngü:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Konum ve dönüş değerlerini gereksinimlerinize göre ayarlayın.

## 6. Adım: Metin parçaları oluşturun ve yapılandırın

 Birden çok oluştur`TextFragment`nesneleri, metinlerini ve özelliklerini ayarlayın:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
```

Metni ve diğer özellikleri istediğiniz gibi ayarlayın.

## 7. Adım: Paragrafa metin parçaları ekleyin

 kullanarak oluşturulan metin parçalarını paragrafa ekleyin.`AppendLine` yöntem:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## 8. Adım: Bir TextBuilder oluşturun ve paragrafı ekleyin

 Oluşturmak`TextBuilder` kullanarak nesne`pdfPage` ve metin paragrafını PDF sayfasına ekleyin:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## 9. Adım: PDF belgesini kaydedin

 Değiştirilen PDF belgesini kullanarak bir dosyaya kaydedin.`Save` yöntem:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 değiştirdiğinizden emin olun`"TextFragmentTests_Rotated4_out.pdf"` istenen çıktı dosyası adıyla.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde metin paragrafları ve oluşturucular kullanarak metni döndürmeyi başarıyla öğrendiniz. Bu öğretici, belgeyi oluşturmaktan değiştirilen sürümü kaydetmeye kadar adım adım bir kılavuz sağladı. Artık PDF dosyalarındaki metin dönüşünü değiştirmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### Metin Paragrafı Kullanarak Metin Döndürme ve Aspose.PDF for .NET kullanan Builder için örnek kaynak kodu 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini başlat
Document pdfDocument = new Document();
// Belirli bir sayfayı al
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Rotasyon belirt
	paragraph.Rotation = i * 90 + 45;
	// Metin parçası oluştur
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// Metin parçası oluştur
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Metin parçası oluştur
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// Metin özelliklerini ayarla
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Metin parçası oluştur
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// Metin özelliklerini ayarla
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// TextBuilder nesnesi oluştur
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// Metin parçasını PDF sayfasına ekleyin
	textBuilder.AppendParagraph(paragraph);
}
// Belgeyi kaydet
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```