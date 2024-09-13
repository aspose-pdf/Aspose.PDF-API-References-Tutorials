---
title: PDF Dosyasındaki Yazı Tiplerini Değiştir
linktitle: PDF Dosyasındaki Yazı Tiplerini Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki yazı tiplerinin nasıl değiştirileceğini öğrenin.
type: docs
weight: 340
url: /tr/net/programming-with-text/replace-fonts/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF dosyasındaki belirli yazı tiplerinin nasıl değiştirileceğini açıklayacağız. Bir PDF belgesini yükleme, metin parçalarını arama, değiştirilecek yazı tiplerini tanımlama, yazı tiplerini değiştirme ve sağlanan C# kaynak kodunu kullanarak değiştirilmiş PDF'yi kaydetme adım adım sürecini ele alacağız.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temellerini anlamak.

## Adım 1: Belge Dizinini Ayarlayın

 İlk olarak, giriş PDF dosyanızın bulunduğu dizine giden yolu ayarlamanız gerekir. Değiştir`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyanızın yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesini Yükleyin

 Daha sonra PDF belgesini kullanarak yüklüyoruz`Document` Aspose.PDF kütüphanesinden sınıf.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Adım 3: Yazı Tiplerini Ara ve Değiştir

 Biz bir tane yaratıyoruz`TextFragmentAbsorber` nesneyi seçin ve kullanılmayan yazı tiplerini kaldırmak için düzenleme seçeneğini ayarlayın. Ardından, metin parçalarını aramak için PDF belgesinin tüm sayfaları için emiciyi kabul ederiz.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Adım 4: Yazı Tiplerini Değiştirin

Absorber tarafından tanımlanan tüm metin parçalarını dolaşıyoruz. Bir metin parçasının font adı, değiştirilecek istenen fontla eşleşiyorsa, onu yeni fontla değiştiririz.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Adım 5: Değiştirilen PDF'yi kaydedin

Son olarak değiştirdiğimiz PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### .NET için Aspose.PDF kullanarak Yazı Tiplerini Değiştirmek için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Kaynak PDF dosyasını yükle
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Metin parçalarını arayın ve düzenleme seçeneğini kullanılmayan yazı tiplerini kaldır olarak ayarlayın
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Tüm sayfalar için emiciyi kabul et
	pdfDocument.Pages.Accept(absorber);
	// Tüm TextFragments'ı dolaş
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Yazı tipi adı ArialMT ise yazı tipi adını Arial ile değiştirin
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

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesindeki belirli yazı tiplerini nasıl değiştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu çalıştırarak bir PDF belgesi yükleyebilir, metin parçalarını arayabilir, belirli yazı tiplerini tanımlayıp değiştirebilir ve değiştirilmiş PDF'yi kaydedebilirsiniz.

### SSS

#### S: "PDF Dosyasındaki Yazı Tiplerini Değiştirme" eğitiminin amacı nedir?

A: "PDF Dosyasındaki Yazı Tiplerini Değiştir" öğreticisi, bir PDF belgesindeki belirli yazı tiplerini değiştirmek için .NET için Aspose.PDF kitaplığının nasıl kullanılacağını gösterir. PDF belgesinin nasıl yükleneceğine, metin parçalarının nasıl aranacağına, değiştirilecek yazı tiplerinin nasıl tanımlanacağına, yazı tiplerinin nasıl değiştirileceğine ve değiştirilen PDF'in nasıl kaydedileceğine dair adım adım bir kılavuz sağlar.

#### S: Neden bir PDF belgesindeki yazı tiplerini değiştirmek isteyebilirim?

A: Bir PDF belgesindeki yazı tiplerini değiştirmek, metnin görünümünü standartlaştırmak veya belgenin farklı cihazlar ve platformlar arasındaki uyumluluğunu iyileştirmek istediğinizde gerekli olabilir. Tutarlı tipografi ve biçimlendirme sağlamanıza olanak tanır.

#### S: Belge dizinini nasıl ayarlarım?

A: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` Girdi PDF dosyanızın bulunduğu dizinin yolunu içeren değişken.

#### S: PDF belgesinde belirli yazı tiplerini nasıl değiştirebilirim?

A: Eğitim, sizi adım adım süreçte yönlendirir:

1.  PDF belgesini kullanarak yükleyin`Document` sınıf.
2.  Bir tane oluştur`TextFragmentAbsorber` nesneyi seçin ve kullanılmayan yazı tiplerini kaldırmak için düzenleme seçeneğini ayarlayın. Metin parçalarını aramak için tüm sayfalar için emiciyi kabul edin.
3. Tanımlanan metin parçaları arasında gezinin. Bir metin parçasının yazı tipi adı değiştirmek istediğiniz yazı tipiyle eşleşiyorsa, yeni yazı tipiyle değiştirin.

####  S: Kullanım amacı nedir?`TextFragmentAbsorber` with font replacement options?

 A:`TextFragmentAbsorber` yazı tipi değiştirme seçenekleriyle metin parçalarını bulmanızı ve aynı anda kullanılmayan yazı tiplerini kaldırmanızı sağlar. Bu, değiştirilen yazı tiplerinin PDF'de ek kaynak olarak eklenmemesini sağlamak için önemlidir.

#### S: Değiştirilecek belirli yazı tiplerini nasıl belirlerim?

A: Absorber tarafından tanımlanan metin parçaları arasında gezinerek, her metin parçası için font bilgisine erişebilirsiniz. Font adı, değiştirmek istediğiniz fontla eşleşiyorsa, değiştirmeyi gerçekleştirebilirsiniz.

#### S: Değiştirilecek yazı tipi bir metin parçasında bulunmazsa ne olur?

A: Değiştirilecek yazı tipi bir metin parçasında bulunmazsa, metin parçasının yazı tipi değişmeden kalır. Değiştirme yalnızca yazı tipi adı eşleşirse gerçekleşir.

#### S: Bu eğitimde yazı tiplerini değiştirme konusunda bir sınırlama var mı?

A: Bu eğitim, metin parçalarındaki belirli yazı tiplerini değiştirmeye odaklanır. Açıklamalar veya form alanları gibi diğer bağlamlardaki yazı tiplerini değiştirmeniz gerekirse, yaklaşımı buna göre genişletmeniz gerekir.

#### S: Verilen kodun yürütülmesinin beklenen sonucu nedir?

A: Öğreticiyi takip ederek ve sağlanan C# kodunu çalıştırarak PDF belgesindeki belirli yazı tiplerini değiştireceksiniz. Belirlediğiniz ölçütlerle tanımlanan yazı tipleri, belirttiğiniz yeni yazı tipiyle değiştirilecektir.

#### S: Bu yaklaşımı kullanarak PDF belgesinin tamamındaki yazı tiplerini değiştirebilir miyim?

C: Evet, tüm metin parçalarını dolaşarak ve yazı tipi değiştirme mantığını uygulayarak, kodu PDF belgesinin tamamındaki yazı tiplerini değiştirecek şekilde uyarlayabilirsiniz.