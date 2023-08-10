---
title: Tüm Metni Değiştir
linktitle: Tüm Metni Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm metni nasıl değiştireceğinizi öğrenin.
type: docs
weight: 350
url: /tr/net/programming-with-text/replace-text-all/
---

Bu öğreticide, Aspose.PDF kitaplığı .NET kullanılarak bir PDF belgesindeki tüm metnin nasıl değiştirileceğini açıklayacağız. Gerekli C# kaynak koduyla birlikte adım adım bir kılavuz sağlayacağız.

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
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## 3. Adım: Metni Arayın ve Değiştirin

 Oluşturmak`TextFragmentAbsorber` girdi arama ifadesinin tüm örneklerini bulmak için nesne. Metin parçalarını ayıklamak için PDF belgesinin tüm sayfaları için yutucuyu kabul edin.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 4. Adım: Metni Değiştirin

Ayıklanan metin parçaları arasında dolaşın ve metni gerektiği gibi değiştirin. Metni ve yazı tipi, yazı tipi boyutu, ön plan rengi ve arka plan rengi gibi diğer özellikleri güncelleyin.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## 5. Adım: Değiştirilmiş PDF'yi kaydedin

Değiştirilen PDF belgesini belirtilen çıktı dosyasına kaydedin.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Metin Tümünü Değiştir için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
//Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Tüm sayfalar için emiciyi kabul edin
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Ayıklanan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Metni ve diğer özellikleri güncelleyin
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Ortaya çıkan PDF belgesini kaydedin.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu öğreticide, Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesindeki tüm metni nasıl değiştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve verilen C# kodunu çalıştırarak bir PDF belgesi yükleyebilir, istediğiniz metni arayabilir, değiştirebilir ve değiştirilen PDF'yi kaydedebilirsiniz.