---
title: PDF Dosyasındaki Kullanılmayan Yazı Tiplerini Kaldır
linktitle: PDF Dosyasındaki Kullanılmayan Yazı Tiplerini Kaldır
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki kullanılmayan yazı tiplerini nasıl kaldıracağınızı öğrenin.
type: docs
weight: 300
url: /tr/net/programming-with-text/remove-unused-fonts/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF dosyasındaki kullanılmayan fontların nasıl kaldırılacağını açıklayacağız. Bir PDF yükleme, kullanılmayan yazı tiplerini belirleyip kaldırma ve güncellenen PDF'yi sağlanan C# kaynak kodunu kullanarak kaydetme sürecini adım adım gerçekleştireceğiz.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temel anlayışı.

## 1. Adım: Belge Dizinini Ayarlayın

 Öncelikle PDF dosyalarınızın bulunduğu dizinin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyalarınızın yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynak PDF'yi yükleyin

 Daha sonra kaynak PDF belgesini kullanarak yüklüyoruz.`Document` Aspose.PDF kütüphanesinden sınıf.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3. Adım: Kullanılmayan Yazı Tiplerini Belirleyin ve Kaldır

 Biz bir yaratıyoruz`TextFragmentAbsorber` ile nesne`TextEditOptions` parametre şu şekilde ayarlandı:`TextEditOptions.FontReplace.RemoveUnusedFonts` . Bu seçenek, PDF belgesindeki kullanılmayan yazı tiplerini belirleyip kaldırmamıza olanak tanır. Daha sonra tüm işlemleri yineliyoruz`TextFragments` ve yazı tipini istediğiniz yazı tipine ayarlayın.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## 4. Adım: Güncellenmiş PDF'yi kaydedin

Son olarak güncellenen PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

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
	// Tüm TextFragments'leri yineleyin
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

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak kullanılmayan yazı tiplerini bir PDF belgesinden nasıl kaldıracağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve verilen C# kodunu çalıştırarak bir PDF yükleyebilir, kullanılmayan yazı tiplerini tanımlayıp kaldırabilir ve güncellenmiş PDF'yi kaydedebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasındaki Kullanılmayan Yazı Tiplerini Kaldırma" eğitiminin amacı nedir?

C: "PDF Dosyasındaki Kullanılmayan Fontları Kaldırma" eğitimi, bir PDF belgesinden kullanılmayan fontları kaldırmak için .NET için Aspose.PDF kütüphanesinin nasıl kullanılacağını açıklar. Eğitim, PDF yükleme, kullanılmayan yazı tiplerini belirleyip kaldırma ve güncellenmiş PDF'yi kaydetme sürecinde size yol gösterir.

#### S: Kullanılmayan yazı tiplerini neden bir PDF belgesinden kaldırmak isteyeyim?

C: Kullanılmayan yazı tiplerini bir PDF belgesinden kaldırmak, dosya boyutunun küçültülmesine ve belgenin daha iyi performans için optimize edilmesine yardımcı olabilir. Bu, özellikle belgenin içeriğinde kullanılmayan gömülü yazı tiplerini içeren PDF'lerle çalışırken kullanışlıdır.

#### S: Belge dizinini nasıl ayarlarım?

C: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyalarınızın bulunduğu dizinin yolunu içeren değişken.

#### S: Aspose.PDF kütüphanesini kullanarak kullanılmayan yazı tiplerini bir PDF belgesinden nasıl kaldırabilirim?

C: Eğitim, süreç boyunca size adım adım rehberlik eder:

1.  PDF belgesini kullanarak açın.`Document` sınıf.
2.  Oluşturmak`TextFragmentAbsorber` ile nesne`TextEditOptions` ayarlanır`FontReplace.RemoveUnusedFonts`.
3. Kullanılmayan yazı tiplerini belirlemek ve PDF'den kaldırmak için emiciyi kabul edin.
4.  Her şeyi yineleyin`TextFragments` ve yazı tipini istediğiniz yazı tipine ayarlayın.
5. Güncellenen PDF belgesini kaydedin.

####  Soru: Programın amacı nedir?`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 C:`TextEditOptions.FontReplace.RemoveUnusedFonts` parametre talimat verir`TextFragmentAbsorber` Kullanılmayan yazı tiplerini belirlemek ve PDF belgesinden kaldırmak için.

#### S: Kullanılmayan yazı tiplerini kendi seçtiğim bir yazı tipiyle değiştirebilir miyim?

C: Evet, kullanılmayan yazı tiplerini seçtiğiniz bir yazı tipiyle değiştirmek için kodu değiştirebilirsiniz. Sağlanan örnek kodda, yerine "Arial, Bold" yazı tipi kullanılmıştır.

####  S: Nasıl`TextFragmentAbsorber` work to remove unused fonts?

 C:`TextFragmentAbsorber` ile yapılandırılmıştır`TextEditOptions.FontReplace.RemoveUnusedFonts` PDF'nin metin parçaları içindeki kullanılmayan yazı tiplerini tanımlayan parametre. Emilimden sonra, tekrarlayabilirsiniz.`TextFragments` ve yazı tiplerini istediğiniz yedek yazı tiplerine ayarlayın.

#### S: Sağlanan kodu çalıştırmanın beklenen sonucu nedir?

C: Öğreticiyi takip ederek ve sağlanan C# kodunu çalıştırarak, kullanılmayan yazı tiplerini giriş PDF belgesinden kaldıracak ve güncellenmiş sürümü çıktı PDF dosyası olarak kaydedeceksiniz.

#### S: Yazı tiplerini yalnızca belirli sayfalardan veya alanlardan kaldıracak şekilde kodu değiştirebilir miyim?

C: Sağlanan kod, kullanılmayan yazı tiplerini PDF belgesinin tamamından kaldırmaya odaklanmaktadır. Yazı tipinin kaldırılması için belirli sayfaları veya bölgeleri hedeflemek istiyorsanız, yaklaşımı değiştirmeniz ve bu alanlarda kullanılmayan yazı tiplerini belirlemek için daha karmaşık bir mantık kullanmanız gerekir.