---
title: PDF Dosyasındaki Kullanılmayan Yazı Tiplerini Kaldır
linktitle: PDF Dosyasındaki Kullanılmayan Yazı Tiplerini Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki kullanılmayan yazı tiplerinin nasıl kaldırılacağını öğrenin.
type: docs
weight: 300
url: /tr/net/programming-with-text/remove-unused-fonts/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF dosyasındaki kullanılmayan fontların nasıl kaldırılacağını açıklayacağız. PDF yükleme, kullanılmayan fontları belirleme ve kaldırma ve güncellenen PDF'yi sağlanan C# kaynak kodunu kullanarak kaydetme adım adım sürecini ele alacağız.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temellerini anlamak.

## Adım 1: Belge Dizinini Ayarlayın

 İlk olarak, PDF dosyalarınızın bulunduğu dizine giden yolu ayarlamanız gerekir. Değiştir`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyalarınızın yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynak PDF'yi yükleyin

 Daha sonra, kaynak PDF belgesini kullanarak yüklüyoruz`Document` Aspose.PDF kütüphanesinden sınıf.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Adım 3: Kullanılmayan Yazı Tiplerini Belirleyin ve Kaldırın

 Biz bir tane yaratıyoruz`TextFragmentAbsorber` nesne ile`TextEditOptions` parametre ayarlandı`TextEditOptions.FontReplace.RemoveUnusedFonts` . Bu seçenek, PDF belgesinde kullanılmayan yazı tiplerini belirlememize ve kaldırmamıza olanak tanır. Daha sonra tüm`TextFragments` ve yazı tipini istediğiniz bir yazı tipine ayarlayın.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Adım 4: Güncellenen PDF'yi Kaydedin

Son olarak güncellenen PDF dokümanını belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### .NET için Aspose.PDF kullanarak Kullanılmayan Yazı Tiplerini Kaldırmak için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Kaynak PDF dosyasını yükle
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Tüm TextFragments'ı yineleyin
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

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF belgesinden kullanılmayan fontları nasıl kaldıracağınızı öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan C# kodunu çalıştırarak bir PDF yükleyebilir, kullanılmayan fontları belirleyip kaldırabilir ve güncellenmiş PDF'i kaydedebilirsiniz.

### SSS

#### S: "PDF Dosyasındaki Kullanılmayan Fontları Kaldırma" eğitiminin amacı nedir?

A: "PDF Dosyasındaki Kullanılmayan Yazı Tiplerini Kaldır" öğreticisi, .NET için Aspose.PDF kütüphanesinin PDF belgesinden kullanılmayan yazı tiplerini kaldırmak için nasıl kullanılacağını açıklar. Öğretici, bir PDF yükleme, kullanılmayan yazı tiplerini belirleme ve kaldırma ve güncellenmiş PDF'yi kaydetme sürecinde size rehberlik eder.

#### S: Kullanılmayan yazı tiplerini bir PDF belgesinden neden kaldırmak isteyebilirim?

A: PDF belgesinden kullanılmayan yazı tiplerini kaldırmak, dosya boyutunu azaltmaya ve belgeyi daha iyi performans için optimize etmeye yardımcı olabilir. Bu, özellikle belgenin içeriğinde gerçekten kullanılmayan gömülü yazı tipleri içeren PDF'lerle uğraşırken faydalıdır.

#### S: Belge dizinini nasıl ayarlarım?

A: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyalarınızın bulunduğu dizinin yolunu içeren değişken.

#### S: Aspose.PDF kütüphanesini kullanarak PDF belgesinden kullanılmayan yazı tiplerini nasıl kaldırabilirim?

A: Eğitim, sizi adım adım süreçte yönlendirir:

1.  PDF belgesini kullanarak açın`Document` sınıf.
2.  Bir tane oluştur`TextFragmentAbsorber` nesne ile`TextEditOptions` ayarlandı`FontReplace.RemoveUnusedFonts`.
3. Kullanılmayan yazı tiplerini PDF'den belirlemek ve kaldırmak için emiciyi kabul edin.
4.  Tümünü tekrarla`TextFragments` ve yazı tipini istediğiniz bir yazı tipine ayarlayın.
5. Güncellenen PDF belgesini kaydedin.

####  S: Amacı nedir?`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A:`TextEditOptions.FontReplace.RemoveUnusedFonts` parametre talimat verir`TextFragmentAbsorber`PDF belgesindeki kullanılmayan yazı tiplerini belirlemek ve kaldırmak için.

#### S: Kullanılmayan fontları kendi seçtiğim bir fontla değiştirebilir miyim?

A: Evet, kullanılmayan yazı tiplerini istediğiniz bir yazı tipiyle değiştirmek için kodu değiştirebilirsiniz. Sağlanan örnek kodda, "Arial, Bold" yazı tipi bir değiştirme olarak kullanılmıştır.

####  S: Nasıl?`TextFragmentAbsorber` work to remove unused fonts?

 A:`TextFragmentAbsorber` ile yapılandırılmıştır`TextEditOptions.FontReplace.RemoveUnusedFonts` PDF'nin metin parçalarındaki kullanılmayan yazı tiplerini tanımlayan parametre. Emilimden sonra, yineleme yapabilirsiniz`TextFragments` ve yazı tiplerini istedikleri yedek yazı tipleriyle değiştirebilirler.

#### S: Verilen kodun yürütülmesinin beklenen sonucu nedir?

C: Eğitimi takip ederek ve verilen C# kodunu çalıştırarak, kullanılmayan fontları giriş PDF belgesinden kaldıracak ve güncellenmiş sürümü çıkış PDF dosyası olarak kaydedeceksiniz.

#### S: Kodu yalnızca belirli sayfalardan veya alanlardan yazı tiplerini kaldıracak şekilde değiştirebilir miyim?

A: Sağlanan kod, kullanılmayan yazı tiplerini tüm PDF belgesinden kaldırmaya odaklanır. Yazı tipi kaldırma için belirli sayfaları veya bölgeleri hedeflemek istiyorsanız, yaklaşımı değiştirmeniz ve bu alanlarda kullanılmayan yazı tiplerini tanımlamak için daha karmaşık bir mantık kullanmanız gerekir.