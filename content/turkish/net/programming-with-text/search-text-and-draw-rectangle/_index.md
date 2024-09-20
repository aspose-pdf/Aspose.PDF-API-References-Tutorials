---
title: Metin Ara ve Dikdörtgen Çiz
linktitle: Metin Ara ve Dikdörtgen Çiz
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'lerde metin aramayı ve dikdörtgenlerle vurgulamayı öğrenin! Gelişmiş PDF düzenleme becerileri için kolay adım adım eğitim.
type: docs
weight: 460
url: /tr/net/programming-with-text/search-text-and-draw-rectangle/
---
## giriiş

PDF düzenleme becerilerinizi geliştirmek mi istiyorsunuz? PDF dosyalarında belirli bir metni nasıl arayacağınızı ve bir dikdörtgenle nasıl vurgulayacağınızı öğrenmek mi istiyorsunuz? Mükemmel bir rehbere ulaştınız! Bugün, .NET için Aspose.PDF'yi kullanarak bir PDF belgesinde metin aramayı ve etrafına dikdörtgenler çizmeyi nasıl yapacağınızı anlatacağım. Bu makale, netlik ve kullanışlılık düşünülerek tasarlanmış adım adım bir eğitim sunacak ve bu teknikleri takip edip projelerinize uygulayabilmenizi sağlayacaktır. 

## Ön koşullar

Eğitime başlamadan önce, sorunsuz bir iş akışı için ihtiyacınız olanları hazırlayalım:

1. .NET'in Temel Anlayışı: Bu eğitimi etkili bir şekilde takip edebilmek için C# programlama ve .NET framework'üne aşina olmanız gerekir.
   
2. Visual Studio Kurulu: Kodunuzu yazmak ve test etmek için entegre bir geliştirme ortamına (IDE) ihtiyacınız olacak. Visual Studio Community harika bir seçenektir ve ücretsizdir.
   
3. .NET için Aspose.PDF: Projenizde Aspose.PDF kütüphanesinin kurulu olması gerekir. İndirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/) veya bir düşünün[geçici lisans](https://purchase.aspose.com/temporary-license/) Genişletilmiş özellikler için.
   
4.  Örnek PDF Belgesi: Bu eğitim için, şu adla örnek bir PDF dosyasına ihtiyacınız olacak:`SearchAndGetTextFromAll.pdf` proje dizininizde saklanır. 

## Paketleri İçe Aktar

Başlamak için öncelikle gerekli paketleri .NET projenize aktarmanız gerekir. Şu adımları izleyin:

### Visual Studio'yu açın

Visual Studio'yu başlatın ve yeni bir Konsol Uygulaması oluşturun veya PDF işlevlerini uygulamak istediğiniz mevcut bir uygulamayı kullanın.

### Aspose.PDF'yi Projenize Ekleyin

1. Çözüm Gezgini’nde projenizin üzerine sağ tıklayın.
2. "NuGet Paketlerini Yönet" seçeneğini seçin.
3.  Arama`Aspose.PDF` ve en son sürümü yükleyin.

Bunu yaparak, gerçekleştirmek üzere olduğunuz tüm muhteşem PDF düzenlemeleri için zemin hazırlamış olursunuz.

## Ad Alanlarını İçe Aktar

Program dosyanızın en üstünde, Aspose kitaplığından ilgili ad alanlarını içe aktarmak isteyeceksiniz:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Bu, görevleriniz için Aspose.PDF kütüphanesindeki sınıflara ve yöntemlere erişimi kolaylaştırır.


Artık her şeyi ayarladığınıza göre, PDF'te metin arama ve etrafına dikdörtgen çizme sürecini yönetilebilir adımlara bölelim.

## Adım 1: Belgeniz için Yolu Ayarlayın

 İlk olarak PDF dosyanızın yolunu ayarlayın. Değiştirdiğinizden emin olun`YOUR DOCUMENT DIRECTORY` gerçek yolunuzla`SearchAndGetTextFromAll.pdf` saklanır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesini açın

 Sonra, şunun bir örneğini oluşturun:`Document` PDF'nizi yüklemek için sınıf:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Bu kod satırı belirttiğiniz PDF dosyasını açar ve dosya üzerinde daha fazla değişiklik yapmanıza olanak tanır.

## Adım 3: Bir Metin Emici Oluşturun

 Şimdi, bu belge içinde metin aramanın bir yoluna ihtiyacınız olacak. Bunun için şunu kullanırız:`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Düzenli ifade`@"[\S]+"` PDF'deki boşluk olmayan herhangi bir dizeyle eşleşecek şekilde tasarlanmıştır. 

## Adım 4: Metin Arama Seçeneklerini Yapılandırın

Daha sonra metin arama seçeneklerini ayarlamanız gerekir:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Burada,`true` parametresi aramanın büyük/küçük harfe duyarlı olacağı anlamına gelir. Bunu şu şekilde ayarlayabilirsiniz:`false` eğer büyük/küçük harfe duyarlı olmayan bir arama istiyorsanız.

## Adım 5: Belgedeki Metin Emiciyi Kabul Edin

 Seninle`TextFragmentAbsorber` ve arama seçenekleri hazır, şimdi belgeden metni özümseme zamanı:

```csharp
document.Pages.Accept(textAbsorber);
```

Bu yöntem, belirtilen desene uyan metin parçalarını bulmak için PDF'nizdeki her sayfayı inceler.

## Adım 6: Bir PdfContentEditor Oluşturun

 Belgeye şekiller çizmek için şunlara ihtiyacınız olacak:`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Bu editör PDF içeriğini kolayca düzenlemenize ve değiştirmenize olanak tanır.

## Adım 7: Bulunan Metin Parçalarında Döngü

Şimdi, bulunan metin parçaları arasında dolaşarak etraflarına dikdörtgenler çizmek isteyeceksiniz:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Bu döngü, her metin parçası ve bunların bölümleri üzerinde yineleme yaparak bir`DrawBox` dikdörtgen çizim yöntemi.

## Adım 8: DrawBox Yöntemini Tanımlayın

 Tanımlamanız gerekiyor`DrawBox` dikdörtgen çizim mantığını ele alacak yöntem. İşte basit bir uygulama:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Metin segmentine göre dikdörtgen boyutlarını hesaplayın
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Hesaplanan değerleri kullanarak bir dikdörtgen çizin
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Bu yöntem, segmentin sınırlayıcı dikdörtgenine göre dikdörtgenin konumunu ve boyutunu belirler ve onu çizmek için editörü kullanır.

## Adım 9: Değiştirilen Belgeyi Kaydedin

Bulunan metnin etrafına dikdörtgenler çizdikten sonra, değiştirilen belgeyi kaydedebilirsiniz:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Orijinal belgenizin üzerine yazılmasını önlemek için yeni dosyanızın farklı bir adla kaydedildiğinden emin olun.

## Adım 10: Onay Mesajı

Son olarak, işlemin başarılı olduğunu bildirmek için konsola bir onay mesajı yazdırın:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

Ve işte karşınızda! PDF'de metin aramak ve dikdörtgenlerle vurgulamak için bir betik başarıyla oluşturdunuz.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak PDF düzenleme yeteneklerinizi büyük ölçüde geliştirebilecek güçlü bir becerinin kilidini açtınız. Sadece birkaç basit adımla, belgenizdeki herhangi bir metni arayabilir ve görsel olarak vurgulayabilir, PDF belgelerinizi daha etkileşimli ve yönetilebilir hale getirebilirsiniz. Bu aracı gerçekten kendinize ait kılmak için farklı regex desenleri ve renk seçenekleriyle denemeler yapmaktan çekinmeyin!

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, PDF belgelerini programlı olarak oluşturmak, düzenlemek ve dönüştürmek için kapsamlı bir yol sağlayan bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
Evet, Aspose kütüphanenin işlevlerini test etmek için kullanabileceğiniz ücretsiz bir deneme sunuyor. Kontrol edin[Burada](https://releases.aspose.com/).

### Aspose.PDF for .NET ile hangi programlama dilini kullanmam gerekiyor?
Aspose.PDF for .NET, C# ve diğer .NET dilleriyle kullanılmak üzere tasarlanmıştır.

### Aspose.PDF konusunda nasıl yardım alabilirim?
 Herhangi bir sorun veya sorunuzla ilgili yardım almak için Aspose destek forumunu ziyaret edebilirsiniz. Destek bulun[Burada](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF for .NET'i nereden indirebilirim?
 Kütüphaneyi Aspose web sitesinden indirebilirsiniz.[Burada](https://releases.aspose.com/pdf/net/).