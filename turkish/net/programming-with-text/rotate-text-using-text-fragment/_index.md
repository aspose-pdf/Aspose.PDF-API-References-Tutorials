---
title: Metin Parçasını Kullanarak Metni Döndürme
linktitle: Metin Parçasını Kullanarak Metni Döndürme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki metin parçalarını kullanarak metni döndürmeyi öğrenin.
type: docs
weight: 390
url: /tr/net/programming-with-text/rotate-text-using-text-fragment/
---

Bu eğitim, metin parçalarını kullanarak metni döndürmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, süreci adım adım gösterir.

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

## 5. Adım: Metin parçaları oluşturun

 Birden çok oluştur`TextFragment` metinlerini ve özelliklerini ayarlayın ve sayfadaki konumlarını belirtin:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Metni, konumları ve diğer özellikleri istediğiniz gibi ayarlayın.

## 6. Adım: Bir TextBuilder oluşturun ve metin parçalarını ekleyin

 Oluşturmak`TextBuilder` kullanarak nesne`pdfPage` ve metin parçalarını PDF sayfasına ekleyin:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## 7. Adım: PDF belgesini kaydedin

 Değiştirilen PDF belgesini kullanarak bir dosyaya kaydedin.`Save` yöntem:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 değiştirdiğinizden emin olun`"TextFragmentTests_Rotated1_out.pdf"` istenen çıktı dosyası adıyla.

### Aspose.PDF for .NET kullanarak Metin Parçası Kullanarak Metni Döndürmek için örnek kaynak kodu 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini başlat
Document pdfDocument = new Document();
// Belirli bir sayfayı al
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Metin parçası oluştur
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Metin özelliklerini ayarla
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Döndürülmüş metin parçası oluştur
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Metin özelliklerini ayarla
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Döndürülmüş metin parçası oluştur
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Metin özelliklerini ayarla
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// TextBuilder nesnesi oluştur
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Metin parçasını PDF sayfasına ekleyin
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Belgeyi kaydet
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki metin parçalarını kullanarak metni döndürmeyi başarıyla öğrendiniz. Bu öğretici, belgeyi oluşturmaktan değiştirilen sürümü kaydetmeye kadar adım adım bir kılavuz sağladı. Artık PDF dosyalarındaki metin dönüşünü değiştirmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.