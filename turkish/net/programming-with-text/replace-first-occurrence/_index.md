---
title: İlk Oluşumu Değiştir
linktitle: İlk Oluşumu Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki metnin ilk geçişini nasıl değiştireceğinizi öğrenin.
type: docs
weight: 330
url: /tr/net/programming-with-text/replace-first-occurrence/
---

Bu eğitimde, Aspose.PDF kitaplığı .NET kullanılarak bir PDF belgesindeki belirli bir metnin ilk geçtiği yerin nasıl değiştirileceğini açıklayacağız. Bir PDF belgesini açma, arama ifadesinin ilk geçtiği yeri bulma, metni değiştirme, özellikleri güncelleme ve sağlanan C# kaynak kodunu kullanarak değiştirilen PDF'yi kaydetme sürecini adım adım inceleyeceğiz.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Temel bir C# programlama anlayışı.

## 1. Adım: Belge Dizinini kurun

 Öncelikle, giriş PDF dosyasının bulunduğu dizine giden yolu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyanızın yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesini Açın

 Ardından, PDF belgesini kullanarak açıyoruz.`Document` Aspose.PDF kitaplığından sınıf.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3. Adım: Arama İfadesinin İlk Oluşumunu Bulun

 biz bir yaratırız`TextFragmentAbsorber`arama ifadesinin tüm örneklerini bulmak için PDF belgesinin tüm sayfaları için nesneyi seçin ve kabul edin.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 4. Adım: Metni Değiştirin

Arama ifadesi PDF belgesinde bulunursa, metin parçasının ilk geçtiği yeri alır ve özelliklerini yeni metin ve biçimlendirme ile güncelleriz.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## 5. Adım: Değiştirilmiş PDF'yi kaydedin

Son olarak, değiştirilen PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Change First Occurrence için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Tüm sayfalar için emiciyi kabul edin
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ayıklanan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// Metnin ilk geçtiği yeri alın ve değiştirin
	TextFragment textFragment = textFragmentCollection[1];
	// Metni ve diğer özellikleri güncelleyin
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## Çözüm

Bu öğreticide, Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesindeki belirli bir metnin ilk geçtiği yeri nasıl değiştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu yürüterek bir PDF belgesi açabilir, bir arama ifadesinin ilk geçtiği yeri bulabilir, metni değiştirebilir, özellikleri güncelleyebilir ve değiştirilen PDF'yi kaydedebilirsiniz.