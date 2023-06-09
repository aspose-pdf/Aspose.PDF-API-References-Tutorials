---
title: Metin Ara ve Dikdörtgen Çiz
linktitle: Metin Ara ve Dikdörtgen Çiz
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF'de metin aramayı, bulunan metnin etrafına dikdörtgenler çizmeyi ve değiştirilen belgeyi kaydetmeyi öğrenin.
type: docs
weight: 460
url: /tr/net/programming-with-text/search-text-and-draw-rectangle/
---

Bu eğitim, bir PDF belgesinde belirli bir metni aramak, bulunan metnin etrafına bir dikdörtgen çizmek ve değiştirilen belgeyi kaydetmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, süreci adım adım gösterir.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Yer değiştirmek`"SearchAndGetTextFromAll.pdf"` PDF dosyanızın gerçek adıyla.

## 5. Adım: Bir TextFragmentAbsorber Oluşturun

 Oluşturmak`TextFragmentAbsorber` girdi arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Yer değiştirmek`@"[\S]+"` istediğiniz düzenli ifade modeliyle.

## 6. Adım: Normal ifade aramasını etkinleştirin

ayarlayarak normal ifade aramasını etkinleştirin.`TextSearchOptions` emicinin özelliği:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## 7. Adım: Tüm sayfalarda arama yapın

Belgenin tüm sayfaları için emiciyi kabul edin:

```csharp
document.Pages.Accept(textAbsorber);
```

## 8. Adım: Bulunan metnin çevresine bir dikdörtgen çizin

 Oluşturmak`PdfContentEditor` her metin parçasının etrafına bir dikdörtgen çizerek, alınan metin parçaları arasında nesne ve döngü oluşturun:

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

 değiştirdiğinizden emin olun`"SearchTextAndDrawRectangle_out.pdf"` istenen çıktı dosyası adıyla.

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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde belirli bir metni nasıl arayacağınızı, bulunan metnin etrafına bir dikdörtgen çizmeyi ve değiştirilen belgeyi kaydetmeyi başarıyla öğrendiniz. Bu öğretici, projeyi ayarlamaktan gerekli eylemleri gerçekleştirmeye kadar adım adım bir kılavuz sağladı. PDF dosyalarında metni değiştirmek ve dikdörtgenler çizmek için artık bu kodu kendi C# projelerinize dahil edebilirsiniz.