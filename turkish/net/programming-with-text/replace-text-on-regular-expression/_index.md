---
title: Normal İfadedeki Metni Değiştir
linktitle: Texton Normal İfadesini Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki normal ifadeye dayalı metni nasıl değiştireceğinizi öğrenin.
type: docs
weight: 360
url: /tr/net/programming-with-text/replace-text-on-regular-expression/
---

Bu eğitimde, Aspose.PDF kitaplığı .NET kullanılarak bir PDF belgesindeki normal ifadeye dayalı olarak metnin nasıl değiştirileceğini açıklayacağız. Gerekli C# kaynak koduyla birlikte adım adım bir kılavuz sağlayacağız.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- C# programlamanın temel anlayışı.

## 1. Adım: Belge Dizinini kurun

 Giriş PDF dosyasının bulunduğu dizine giden yolu ayarlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir`PDF dosyanızın yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF Belgesini Yükleyin

 kullanarak PDF belgesini yükleyin.`Document` Aspose.PDF kitaplığından sınıf.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## 3. Adım: Normal İfadeyi Kullanarak Metin Arayın ve Değiştirin

 Oluşturmak`TextFragmentAbsorber` nesnesini seçin ve kalıpla eşleşen tüm cümleleri bulmak için normal ifade kalıbını belirtin. Normal ifade kullanımını etkinleştirmek için metin arama seçeneğini ayarlayın.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 gibi
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## 4. Adım: Metni Değiştirin

Ayıklanan metin parçaları arasında dolaşın ve metni gerektiği gibi değiştirin. Metni ve yazı tipi, yazı tipi boyutu, ön plan rengi ve arka plan rengi gibi diğer özellikleri güncelleyin.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## 5. Adım: Değiştirilmiş PDF'yi kaydedin

Değiştirilen PDF belgesini belirtilen çıktı dosyasına kaydedin.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Texton Normal İfadeyi Değiştir için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Normal ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 gibi
// Normal ifade kullanımını belirtmek için metin arama seçeneğini ayarlayın
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Tek bir sayfa için emiciyi kabul edin
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Ayıklanan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Metni ve diğer özellikleri güncelleyin
	textFragment.Text = "New Phrase";
	// Bir nesnenin örneğine ayarlayın.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kitaplığını kullanarak bir PDF belgesindeki normal ifadeye dayalı olarak metni nasıl değiştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu yürüterek bir PDF belgesi yükleyebilir, normal bir ifade kullanarak metin arayabilir, değiştirebilir ve değiştirilen PDF'yi kaydedebilirsiniz.