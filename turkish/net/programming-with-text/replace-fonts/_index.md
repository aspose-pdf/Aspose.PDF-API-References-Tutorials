---
title: Yazı Tiplerini Değiştir
linktitle: Yazı Tiplerini Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki yazı tiplerini nasıl değiştireceğinizi öğrenin.
type: docs
weight: 340
url: /tr/net/programming-with-text/replace-fonts/
---

Bu eğitimde, Aspose.PDF for .NET kitaplığı kullanılarak bir PDF belgesindeki belirli yazı tiplerinin nasıl değiştirileceğini açıklayacağız. Bir PDF belgesini yükleme, metin parçalarını arama, değiştirilecek yazı tiplerini belirleme, yazı tiplerini değiştirme ve sağlanan C# kaynak kodunu kullanarak değiştirilen PDF'yi kaydetme sürecini adım adım inceleyeceğiz.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Temel bir C# programlama anlayışı.

## 1. Adım: Belge Dizinini kurun

 Öncelikle, giriş PDF dosyasının bulunduğu dizine giden yolu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyanızın yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF Belgesini Yükleyin

 Ardından, PDF belgesini kullanarak yüklüyoruz.`Document` Aspose.PDF kitaplığından sınıf.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3. Adım: Yazı Tiplerini Arayın ve Değiştirin

 biz bir yaratırız`TextFragmentAbsorber` nesne ve kullanılmayan yazı tiplerini kaldırmak için düzenleme seçeneğini ayarlayın. Ardından, metin parçalarını aramak için PDF belgesinin tüm sayfaları için yutucuyu kabul ediyoruz.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## 4. Adım: Yazı Tiplerini Değiştirin

Emici tarafından tanımlanan tüm metin parçaları arasında geziniyoruz. Bir metin parçasının yazı tipi adı, değiştirilmesi istenen yazı tipiyle eşleşirse, onu yeni yazı tipiyle değiştiririz.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## 5. Adım: Değiştirilmiş PDF'yi kaydedin

Son olarak, değiştirilen PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Yazı Tiplerini Değiştir için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Kaynak PDF dosyasını yükle
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Metin parçalarını arayın ve düzenleme seçeneğini kullanılmayan yazı tiplerini kaldırın olarak ayarlayın
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Tüm sayfalar için emiciyi kabul edin
	pdfDocument.Pages.Accept(absorber);
	//Tüm TextFragments'ta gezinin
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Yazı tipi adı ArialMT ise, yazı tipi adını Arial ile değiştirin
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Güncellenen belgeyi kaydet
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Çözüm

Bu öğreticide, Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesindeki belirli yazı tiplerini nasıl değiştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu çalıştırarak bir PDF belgesi yükleyebilir, metin parçalarını arayabilir, belirli yazı tiplerini belirleyip değiştirebilir ve değiştirilen PDF'yi kaydedebilirsiniz.