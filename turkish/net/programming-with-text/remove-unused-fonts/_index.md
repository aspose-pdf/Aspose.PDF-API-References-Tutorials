---
title: Kullanılmayan Yazı Tiplerini Kaldır
linktitle: Kullanılmayan Yazı Tiplerini Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak kullanılmayan yazı tiplerini bir PDF belgesinden nasıl kaldıracağınızı öğrenin.
type: docs
weight: 300
url: /tr/net/programming-with-text/remove-unused-fonts/
---

Bu öğreticide, kullanılmayan yazı tiplerinin Aspose.PDF for .NET kütüphanesini kullanarak bir PDF belgesinden nasıl kaldırılacağını açıklayacağız. PDF yükleme, kullanılmayan yazı tiplerini belirleyip kaldırma ve sağlanan C# kaynak kodunu kullanarak güncellenmiş PDF'yi kaydetme sürecini adım adım inceleyeceğiz.

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3. Adım: Kullanılmayan Yazı Tiplerini Belirleyin ve Kaldırın

 biz bir yaratırız`TextFragmentAbsorber` ile nesne`TextEditOptions` parametre ayarlandı`TextEditOptions.FontReplace.RemoveUnusedFonts` Bu seçenek, PDF belgesindeki kullanılmayan yazı tiplerini belirlememize ve kaldırmamıza olanak tanır. Daha sonra tüm işlemleri yineliyoruz.`TextFragments` ve yazı tipini istediğiniz yazı tipine ayarlayın.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## 4. Adım: Güncellenmiş PDF'yi kaydedin

Son olarak, güncellenmiş PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Kullanılmayan Yazı Tiplerini Kaldırmak için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Kaynak PDF dosyasını yükle
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Tüm TextFragments boyunca yineleyin
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Güncellenen belgeyi kaydet
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Çözüm

Bu öğreticide, kullanılmayan yazı tiplerini Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesinden nasıl kaldıracağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu yürüterek bir PDF yükleyebilir, kullanılmayan yazı tiplerini belirleyip kaldırabilir ve güncellenmiş PDF'yi kaydedebilirsiniz.