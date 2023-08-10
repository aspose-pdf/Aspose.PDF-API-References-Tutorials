---
title: Metin Değiştirmeyi Kullanarak İçeriği Yeniden Düzenleme
linktitle: Metin Değiştirmeyi Kullanarak İçeriği Yeniden Düzenleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile metin değiştirmeyi kullanarak bir PDF belgesindeki içeriği nasıl yeniden düzenleyeceğinizi öğrenin.
type: docs
weight: 270
url: /tr/net/programming-with-text/rearrange-contents-using-text-replacement/
---

Bu eğitimde, Aspose.PDF for .NET kitaplığı ile metin değiştirmeyi kullanarak bir PDF belgesindeki içeriğin nasıl yeniden düzenleneceğini açıklayacağız. Sağlanan C# kaynak kodunu kullanarak bir PDF yükleme, belirli metin parçalarını arama, metni değiştirme ve değiştirilen PDF'yi kaydetme sürecini adım adım inceleyeceğiz.

## Gereksinimler

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Temel bir C# programlama anlayışı.

## 1. Adım: Belge Dizinini kurun

 Öncelikle, PDF dosyalarınızın bulunduğu dizinin yolunu belirlemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyalarınızın yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Kaynak PDF'yi yükleyin

 Ardından, kaynak PDF belgesini kullanarak yüklüyoruz.`Document` Aspose.PDF kitaplığından sınıf.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## 3. Adım: Metin Parçalarını Arayın ve Değiştirin

 biz bir yaratırız`TextFragmentAbsorber` Belirli metin parçalarını aramak için düzenli ifadeye sahip nesne. Ardından, metin parçalarını yineliyoruz, yazı tipini, boyutunu, rengini özelleştiriyoruz ve metni değiştiriyoruz.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## 4. Adım: Değiştirilmiş PDF'yi kaydedin

Son olarak, değiştirilen PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Metin Değiştirme Kullanarak İçeriği Yeniden Düzenlemek için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Kaynak PDF dosyasını yükle
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	//Düzenli ifade ile TextFragment Absorber nesnesi oluşturun
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Her TextFragment'i değiştirin
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Değiştirilen metin parçasının yazı tipini ayarla
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Yazı tipi boyutunu ayarla
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Metni, yer tutucudan daha büyük bir dizeyle değiştirin
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Ortaya çıkan PDF'yi kaydet
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kitaplığı ile metin değiştirmeyi kullanarak bir PDF belgesindeki içeriği nasıl yeniden düzenleyeceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu yürüterek belirli metin parçalarını arayabilir, görünümlerini özelleştirebilir ve bir PDF belgesindeki metni değiştirebilirsiniz.