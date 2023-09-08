---
title: PDF Dosyasındaki Yazı Tiplerini Değiştir
linktitle: PDF Dosyasındaki Yazı Tiplerini Değiştir
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki yazı tiplerini nasıl değiştireceğinizi öğrenin.
type: docs
weight: 340
url: /tr/net/programming-with-text/replace-fonts/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF dosyasındaki belirli yazı tiplerinin nasıl değiştirileceğini açıklayacağız. Bir PDF belgesi yükleme, metin parçalarını arama, değiştirilecek yazı tiplerini belirleme, yazı tiplerini değiştirme ve değiştirilen PDF'yi sağlanan C# kaynak kodunu kullanarak kaydetme sürecini adım adım gerçekleştireceğiz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temel anlayışı.

## 1. Adım: Belge Dizinini Ayarlayın

 Öncelikle, giriş PDF dosyasının bulunduğu dizinin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyanızın yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesini Yükleyin

 Daha sonra, PDF belgesini kullanarak yüklüyoruz.`Document` Aspose.PDF kütüphanesinden sınıf.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3. Adım: Yazı Tiplerini Arayın ve Değiştirin

 Biz bir yaratıyoruz`TextFragmentAbsorber`nesneyi seçin ve kullanılmayan yazı tiplerini kaldırmak için düzenleme seçeneğini ayarlayın. Ardından, metin parçalarını aramak için PDF belgesinin tüm sayfaları için emiciyi kabul ediyoruz.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## 4. Adım: Yazı Tiplerini Değiştirin

Emici tarafından tanımlanan tüm metin parçalarının üzerinden geçiyoruz. Bir metin parçasının yazı tipi adı, değiştirilmesi istenen yazı tipiyle eşleşiyorsa onu yeni yazı tipiyle değiştiririz.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## 5. Adım: Değiştirilen PDF'yi kaydedin

Son olarak değiştirilen PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Yazı Tiplerini Değiştirme için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Kaynak PDF dosyasını yükle
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Metin parçalarını arayın ve kullanılmayan yazı tiplerini kaldırmak için düzenleme seçeneğini ayarlayın
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Tüm sayfalar için emiciyi kabul edin
	pdfDocument.Pages.Accept(absorber);
	// Tüm TextFragments'ler arasında geçiş yapın
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

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesindeki belirli yazı tiplerini nasıl değiştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve verilen C# kodunu çalıştırarak bir PDF belgesi yükleyebilir, metin parçalarını arayabilir, belirli yazı tiplerini tanımlayıp değiştirebilir ve değiştirilen PDF'yi kaydedebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasındaki Yazı Tiplerini Değiştirme" eğitiminin amacı nedir?

C: "PDF Dosyasındaki Fontları Değiştirme" eğitimi, bir PDF belgesindeki belirli fontları değiştirmek için Aspose.PDF for .NET kütüphanesinin nasıl kullanılacağını gösterir. Bir PDF belgesinin nasıl yükleneceği, metin parçalarının nasıl aranacağı, değiştirilecek yazı tiplerinin nasıl belirleneceği, yazı tiplerinin nasıl değiştirileceği ve değiştirilen PDF'nin nasıl kaydedileceği konusunda adım adım kılavuz sağlar.

#### S: Bir PDF belgesindeki yazı tiplerini neden değiştirmek isteyeyim?

C: Metnin görünümünü standartlaştırmak veya belgenin farklı cihazlar ve platformlar arasındaki uyumluluğunu geliştirmek istediğinizde, PDF belgesindeki yazı tiplerini değiştirmek gerekli olabilir. Tutarlı tipografi ve biçimlendirme sağlamanıza olanak tanır.

#### S: Belge dizinini nasıl ayarlarım?

C: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` giriş PDF dosyanızın bulunduğu dizinin yolunu içeren değişken.

#### S: Bir PDF belgesindeki belirli yazı tiplerini nasıl değiştiririm?

C: Eğitim, süreç boyunca size adım adım rehberlik eder:

1.  PDF belgesini kullanarak yükleyin`Document` sınıf.
2.  Oluşturmak`TextFragmentAbsorber` nesneyi seçin ve kullanılmayan yazı tiplerini kaldırmak için düzenleme seçeneğini ayarlayın. Metin parçalarını aramak için tüm sayfalar için emiciyi kabul edin.
3. Tanımlanan metin parçaları arasında gezinin. Bir metin parçasının yazı tipi adı değiştirmek istediğiniz yazı tipiyle eşleşiyorsa onu yeni yazı tipiyle değiştirin.

####  S: Kullanmanın amacı nedir?`TextFragmentAbsorber` with font replacement options?

 C:`TextFragmentAbsorber` yazı tipi değiştirme seçenekleriyle metin parçalarını bulmanıza ve aynı anda kullanılmayan yazı tiplerini kaldırmanıza olanak tanır. Değiştirilen yazı tiplerinin PDF'ye ek kaynak olarak eklenmemesini sağlamak için bu önemlidir.

#### S: Değiştirilecek belirli yazı tiplerini nasıl tanımlarım?

C: Emici tarafından tanımlanan metin parçaları arasında geçiş yaparak her bir metin parçası için yazı tipi bilgisine erişebilirsiniz. Font adı değiştirmek istediğiniz fontla eşleşiyorsa değiştirme işlemini gerçekleştirebilirsiniz.

#### S: Değiştirilecek yazı tipi bir metin parçasında bulunamazsa ne olur?

C: Değiştirilecek yazı tipi bir metin parçasında bulunamazsa, metin parçasının yazı tipi değişmeden kalır. Değiştirme yalnızca yazı tipi adı eşleştiğinde gerçekleşir.

#### S: Bu eğitimde yazı tiplerini değiştirmeyle ilgili bir sınırlama var mı?

C: Bu eğitim, metin parçalarındaki belirli yazı tiplerini değiştirmeye odaklanmaktadır. Ek açıklamalar veya form alanları gibi başka bağlamlardaki yazı tiplerini değiştirmeniz gerekiyorsa yaklaşımı buna göre genişletmeniz gerekir.

#### S: Sağlanan kodu çalıştırmanın beklenen sonucu nedir?

C: Öğreticiyi takip ederek ve verilen C# kodunu çalıştırarak, PDF belgesindeki belirli yazı tiplerini değiştireceksiniz. Belirlediğiniz kriterlere göre belirlenen yazı tipleri, belirttiğiniz yeni yazı tipiyle değiştirilecektir.

#### S: Bu yaklaşımı tüm PDF belgesindeki yazı tiplerini değiştirmek için kullanabilir miyim?

C: Evet, tüm metin parçalarından geçerek ve yazı tipi değiştirme mantığını uygulayarak kodu, PDF belgesinin tamamındaki yazı tiplerini değiştirecek şekilde uyarlayabilirsiniz.