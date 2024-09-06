---
title: Kelimeleri Sil
linktitle: Kelimeleri Sil
second_title: Aspose.PDF for .NET API Referansı
description: Bu kapsamlı adım adım kılavuzla Aspose.PDF for .NET kullanarak bir PDF'deki kelimeleri nasıl çizeceğinizi öğrenin. Belge düzenleme becerilerinizi geliştirin.
type: docs
weight: 150
url: /tr/net/annotations/strikeoutwords/
---
## giriiş

Hiç bir PDF'deki belirli bir metni, onu çizerek vurgulamanız gerektiğini fark ettiniz mi? Belgeleri inceliyor, metni işaretliyor veya yalnızca belirli bölümleri vurgulamanız gerekiyorsa, kelimeleri çizmek değerli bir araç olabilir. Bu eğitimde, .NET için Aspose.PDF'yi kullanarak tam olarak bunu nasıl yapacağınızı inceleyeceğiz. Bu kapsamlı kılavuz, her adımda size yol gösterecek ve bu özelliği .NET uygulamalarınızda etkili bir şekilde uygulamak için gereken tüm bilgilere sahip olmanızı sağlayacaktır. 

## Ön koşullar

Koda geçmeden önce, bu eğitimi takip edebilmeniz için karşılamanız gereken birkaç ön koşul var:

1.  Aspose.PDF for .NET Kütüphanesi: Aspose.PDF for .NET kütüphanesinin yüklü olduğundan emin olun.[buradan indirin](https://releases.aspose.com/pdf/net/).

2. .NET Framework: Makinenizde .NET Framework'ün yüklü olduğundan emin olun. Bu eğitim .NET uygulamaları için tasarlanmıştır.

3. Geliştirme Ortamı: Kodunuzu yazmak ve çalıştırmak için Visual Studio gibi bir IDE'ye ihtiyacınız olacak.

4. PDF Belgesi: Üzerinde çalışmak istediğiniz bir örnek PDF dosyası hazırlayın. Bu, metni çizeceğimiz belge olacak.

5. Temel C# Bilgisi: Bu eğitimdeki adımları anlamak ve uygulamak için C# programlamaya aşinalık gereklidir.

## Paketleri İçe Aktar

Kodlamaya başlamadan önce, .NET projemize gerekli ad alanlarını içe aktarmamız gerekiyor. Bu, Aspose.PDF kullanarak PDF dosyalarını işlemek için gereken sınıflara ve yöntemlere erişmemizi sağlayacaktır.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Bu ad alanları, PDF belgeleriyle çalışmak, metinleri işlemek ve üstü çizili metin gibi açıklamalar eklemek için önemlidir.

Bu bölümde, bir PDF belgesinde kelimeleri silme sürecini basit, yönetilebilir adımlara böleceğiz. Her adım, her şeyin nasıl çalıştığını anlamanızı sağlamak için ayrıntılı bir açıklama ile birlikte sunulacaktır.

## Adım 1: PDF Belgesini Yükleyin

İlk adım, düzenlemek istediğiniz PDF belgesini yüklemektir. Bu belge, belirli kelimeleri veya ifadeleri sileceğiniz belge olacaktır.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini açın
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Bu değişken belge dizininize giden yolu tutar. Değiştir`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın bulunduğu gerçek yol ile.
- `Document` : :`Document` sınıfı bir PDF belgesini temsil eder. Dosya yolunu oluşturucusuna geçirerek, PDF dosyasını işleme için açarız.

## Adım 2: Belirli Metni Bulmak İçin Bir TextFragment Absorber Oluşturun

 Daha sonra, bir örnek oluşturacağız`TextFragmentAbsorber` PDF belgesinde belirli bir metin parçasını aramak için. Bu, silmek istediğimiz metni bulmamızı sağlar.

```csharp
// Belirli bir metin parçasını aramak için TextFragment Absorber örneği oluşturun
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Bu sınıf, PDF belgesindeki belirli metin parçalarını bulmak ve bunlarla çalışmak için kullanılır. Bu örnekte, "Estoque" kelimesini arıyoruz. "Estoque" kelimesini, belgenizde bulmak istediğiniz kelime veya ifadeyle değiştirin.

## Adım 3: PDF Belgesinin Sayfalarında Gezinin

 Artık bizim`TextFragmentAbsorber`Belirtilen metni bulmak için PDF belgesinin her sayfasını yinelememiz gerekiyor.

```csharp
// PDF belgesinin sayfaları arasında gezinin
for (int i = 1; i <= document.Pages.Count; i++)
{
    // PDF belgesinin geçerli sayfasını al
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: Bu döngü PDF belgesinin her sayfasını yineler.
- `document.Pages[i]`: İşlenmekte olan geçerli sayfayı alır.
- `page.Accept(textFragmentAbsorber)` : Bu yöntem,`TextFragmentAbsorber` geçerli sayfaya, belirtilen metni arayarak.

## Adım 4: Metin Parçalarını Toplayın ve İşleyin

Sayfalar arasında dolaştıktan sonra bulduğumuz metin parçalarını toplayacağız ve daha sonraki işlemler için hazırlayacağız.

```csharp
// Emilen metin parçalarından oluşan bir koleksiyon oluşturun
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Bu koleksiyon, belgede bulunan tüm metin parçalarını depolar. Metni silmek için bir sonraki adımda bu koleksiyonu kullanacağız.

## Adım 5: Metin Parçalarını Tekrarlayın ve Bunları Çıkarın

Bu adımda, koleksiyonumuzdaki her metin parçasının üzerinden geçeceğiz ve ona üstü çizili bir açıklama uygulayacağız.

```csharp
// Metin parçalarının koleksiyonu üzerinde yineleme yapın
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // TextFragment nesnesinin dikdörtgen boyutlarını alın
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // StrikeOut Açıklama örneğini örneklendir
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Üstü çizili açıklamanın özelliklerini ayarlayın
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Açıklamayı metin parçasının sayfasının açıklamalar koleksiyonuna ekleyin
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Bu satır geçerli metin parçasını alır.
- `Aspose.Pdf.Rectangle`:Metin parçasının dikdörtgen boyutlarını hesaplayarak üstü çizili kısmın nereye uygulanacağını belirliyoruz.
- `StrikeOutAnnotation`: Bu sınıf üstü çizili açıklamayı temsil eder. Bunu hesaplanan dikdörtgen ve geçerli sayfa ile örnekliyoruz.
- `strikeOut.Opacity`: Bu özellik üstü çizili yazının opaklığını ayarlayarak %80 oranında görünür olmasını sağlar.
- `strikeOut.Color`Çizginin rengini kırmızı olarak ayarladık. Bunu istediğiniz herhangi bir renge değiştirebilirsiniz.
- `textFragment.Page.Annotations.Add(strikeOut)`: Bu, sayfaya üstü çizili açıklama ekler.

## Adım 6: Değiştirilen PDF Belgesini Kaydedin

Son adım, değiştirilmiş PDF belgesini üstü çizili olarak kaydetmektir.

```csharp
// Güncellenen PDF belgesini kaydedin
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Bu, değiştirilen belge için yeni bir dosya adı oluşturur. Orijinal dosya değişmeden kalır.
- `document.Save(dataDir)`: PDF belgesini üstü çizili olarak belirtilen yere kaydeder.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki belirli kelimeleri başarıyla sildiniz. Bu adım adım kılavuzu izleyerek artık metni vurgulayarak veya silerek PDF belgelerini özelleştirebilir, daha dinamik hale getirebilir ve ihtiyaçlarınıza göre uyarlayabilirsiniz. İster yasal belgelere not ekleyin, ister raporlar hazırlayın veya sadece metni incelemek için işaretleyin, bu eğitim size bunu verimli bir şekilde yapmanız için gereken becerileri kazandırdı.

## SSS

### Üstü çizili yazının rengini değiştirebilir miyim?

 Evet, rengi değiştirerek değiştirebilirsiniz.`strikeOut.Color`özellik. Örneğin, bunu şu şekilde ayarlayabilirsiniz:`Aspose.Pdf.Color.Blue` mavi bir strikeout için.

### Birden fazla kelimeyi aynı anda silmek mümkün müdür?

 Kesinlikle!`TextFragmentAbsorber` belgedeki herhangi bir kelime veya ifadeyi aramak için kullanılabilir. Üstü çiziliyi, yineleme yaparak birden fazla örneğe uygulayabilirsiniz`TextFragmentCollection`.

### Yalnızca belirli sayfalardaki metni çizmek istersem ne olur?

 Sayfalar arasında yineleme yapan döngüyü yalnızca değiştirmek istediğiniz sayfaları içerecek şekilde değiştirebilirsiniz. Örneğin,`for (int i = 1; i <= 3; i++)` Sadece ilk üç sayfanın üzeri çizilecektir.

### Çizgi kalınlığını nasıl ayarlayabilirim?

 Çizgi kalınlığını, çizgi kalınlığını değiştirerek ayarlayabilirsiniz.`Border` mülkiyeti`StrikeOutAnnotation`Bu, vuruş görünümünün özelleştirilmesine olanak tanır.

### Belgeyi kaydettikten sonra çizili metni geri almanın bir yolu var mı?

Belge kaydedildikten sonra, üstü çizili metin kalıcıdır. Üstü çizili metin olmadan orijinal metni saklamanız gerekiyorsa, herhangi bir değişiklik uygulamadan önce orijinal belgenin bir yedeğini kaydetmeyi düşünün.