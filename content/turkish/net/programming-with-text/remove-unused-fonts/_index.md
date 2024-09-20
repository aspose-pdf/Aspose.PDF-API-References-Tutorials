---
title: PDF Dosyasındaki Kullanılmayan Yazı Tiplerini Kaldır
linktitle: PDF Dosyasındaki Kullanılmayan Yazı Tiplerini Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarından kullanılmayan yazı tiplerini zahmetsizce nasıl kaldıracağınızı öğrenin. Performansı artırın ve dosya boyutunu azaltın.
type: docs
weight: 300
url: /tr/net/programming-with-text/remove-unused-fonts/
---
## giriiş

Merhaba! Gereksiz yer kaplayan yazı tipleriyle dolu şişkin PDF dosyalarından bıktınız mı? Yalnız değilsiniz! PDF'lerde yazı tipi kullanımını yönetmek, özellikle belgelerinizin temiz ve verimli olmasını istediğinizde, zahmetli olabilir. İyi haber şu ki, .NET için Aspose.PDF ile PDF dosyalarından kullanılmayan yazı tiplerini kolayca kaldırabilir, performansı artırabilir ve dosya boyutunu azaltabilirsiniz. Bu eğitimde, PDF dosya yönetiminizi kolaylaştırabilmeniz için süreci adım adım ele alacağız.

## Ön koşullar

Başlamadan önce, bu eğitimden en iyi şekilde yararlanmak için aşağıdaki ayarların yapıldığından emin olun:

1. Visual Studio Kurulu: .NET kodunuzu çalıştırmak için bir geliştirme ortamına ihtiyacınız olacak. Visual Studio (herhangi bir sürüm) harika bir seçimdir.
2.  Aspose.PDF for .NET: Bu kütüphanenin kurulu olduğundan emin olun. İndirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
3. C# Hakkında Temel Bilgi: Bu örnekte C# kullanacağımız için, dile aşinalık faydalı olacaktır.
4. Bir PDF Dosyası: Hazır bir örnek PDF dosyanız olsun. Kendi dosyanızı oluşturabilir veya mevcut herhangi bir PDF'i kullanabilirsiniz. Sadece adının olduğundan emin olun`ReplaceTextPage.pdf` ve belgeler dizininizde saklanır.
5.  Geçerli Lisans: Ücretsiz denemeyi kullanabilmenize rağmen, tam işlevsellik için geçerli bir lisans önerilir. Geçici bir lisansa ihtiyacınız varsa, bunu edinebilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

## Paketleri İçe Aktar

Artık ön koşullarımız hazır olduğuna göre, gerekli paketleri C# projemize aktaralım. İhtiyacınız olanlar şunlar:

Aspose.PDF Ad Alanı: Bu, PDF dosyalarını işlemek için gereken tüm temel işlevleri sağlar.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Bunları içe aktarmak için, yukarıdaki satırları C# dosyanızın en üstüne ekleyin. Bu, PDF belgelerinizi düzenlemek için kullanacağımız sınıflara ve yöntemlere erişmenizi sağlayacaktır.

## Adım 1: Proje Ortamınızı Kurun

İlk önce ilk şeyler! Visual Studio'da yeni bir Konsol Uygulaması oluşturmanız gerekiyor. Şu adımları izleyin:

- Visual Studio’yu açın.
- Dosya > Yeni > Proje’ye tıklayın.
-  Konsol Uygulamasını (.NET Framework) seçin ve ona bir ad verin (örneğin,`PdfFontCleaner`).
- Oluştur’a tıklayın.

Artık üzerinde çalışabileceğiniz yepyeni bir projeniz var!

## Adım 2: Aspose.PDF Kütüphanesini ekleyin

Sonra, Aspose.PDF kütüphanesini projenize ekleyeceksiniz. Bunu NuGet aracılığıyla yapabilirsiniz:

1. Çözüm Gezgini'nde projenizin üzerine sağ tıklayın.
2. NuGet Paketlerini Yönet'i seçin.
3.  Arama`Aspose.PDF` ve kurun.

## Adım 3: PDF Belgesini Yükleyin

İşlemek istediğiniz belgeyi yükleyelim. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY/"; // Bunu yolunuza güncelleyin
// Kaynak PDF dosyasını yükle
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY/"` PDF dosyanızın saklandığı gerçek yol ile. Bu adım önemlidir çünkü Aspose'un PDF belgenize erişmesine izin verir. 

## Adım 4: Metin Parçası Emicisini Ayarlayın

Sonra, PDF'den kullanılmayan fontları tanımlamamıza ve kaldırmamıza yardımcı olacak bir işlemci ayarlayacağız. Bunu yapmak için kod şu şekilde:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorber);
```

 Bu kod satırı bir`TextFragmentAbsorber` kullanılmayan yazı tiplerini kaldırmak üzere yapılandırılmış nesne. Çağrılarak`doc.Pages.Accept(absorber)`, Aspose'a belgedeki tüm sayfaları incelemesini ve metin parçalarını tanımlamasını söylüyoruz.

## Adım 5: Metin Parçaları Üzerinde Gezinin ve Yazı Tiplerini Değiştirin

Metin parçalarını tanımladıktan sonra, bunlar arasında yineleme yapmanın ve kullanılmayan yazı tiplerini değiştirmenin zamanı geldi. Bu kodu ekleyin:

```csharp
//Tüm TextFragments'ı yineleyin
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

 Bu döngüde her birinin yazı tipini değiştireceksiniz`TextFragment` "Arial, Bold"a. İhtiyaçlarınıza uygun herhangi bir yazı tipini seçebilirsiniz. Gerçek sihir burada gerçekleşir, çünkü PDF'in temiz, iyi tanımlanmış bir yazı tipiyle kalmasını sağlar.

## Adım 6: Güncellenen Belgeyi Kaydedin

Gerekli değişiklikleri yaptığımıza göre, güncellenen PDF'i kaydedelim! Aşağıdaki kodu ekleyin:

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
// Güncellenen belgeyi kaydet
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
```

 Burada, adında yeni bir dosya oluşturuyoruz`RemoveUnusedFonts_out.pdf` aynı dizinde. Bu size orijinal PDF'nizin bir yedeğini verirken, yine de size akıcı bir sürüm sağlar.

## Adım 7: İstisnaları Yönetin

Son olarak, hata işlemeyi dahil etmek her zaman iyi bir fikirdir. İşte kodunuzu sarmak için basit bir try-catch bloğu:

```csharp
try
{
    // ... (önceki kod)
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30-day temporary license from https://satınalma.aspose.com.");
}
```

Bu, işlem sırasında oluşan herhangi bir istisnayı yakalayacak ve kullanıcı dostu hata mesajları sağlayacaktır. Kullanıcılarınızı geçerli bir Aspose lisansına ihtiyaç duyma gibi gereksinimler konusunda bilgilendirmeniz önemlidir.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak PDF dosyasından kullanılmayan fontları nasıl kaldıracağınızı başarıyla öğrendiniz. Yukarıda özetlenen adımları izleyerek PDF dosyalarınızı daha yalın ve düzenli hale getirebilir, daha verimli ve kullanıcı dostu olmalarını sağlayabilirsiniz. Belge işleme yeteneklerinizi daha da geliştirmek için Aspose.PDF'nin diğer işlevlerini keşfetmeyi unutmayın!

## SSS

### Bu görev için Aspose.PDF'nin ücretsiz sürümünü kullanabilir miyim?
Evet, ücretsiz denemeyi kullanabilirsiniz ancak optimum performans için tam lisans önerilir.

### Değiştirilebilecek bir şey yoksa yazı tiplerine ne olur?
Yedek bir yazı tipi bulunamazsa, metin doğru görüntülenmeyebilir; bu nedenle yaygın olarak bulunan bir yazı tipi seçtiğinizden emin olun.

### Geçici ehliyet nasıl alınır?
 Geçici lisans talebinde bulunabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### Kullanılmayan yazı tiplerini kaldırmak belgenin görünümünü etkiler mi?
Hangi yazı tiplerinin kaldırıldığı ve metin parçalarının nasıl değiştirildiğine bağlı olarak bu mümkün olabilir; test yapılması önerilir.

### Kullanılmayan fontları kaldırmanın alternatif bir yöntemi var mı?
Bu amaç için Aspose.PDF for .NET oldukça verimlidir, ancak diğer kütüphaneler veya araçlar da benzer işlevler sunabilir.