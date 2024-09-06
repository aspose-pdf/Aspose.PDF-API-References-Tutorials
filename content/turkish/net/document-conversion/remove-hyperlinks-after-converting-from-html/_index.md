---
title: Html'den Dönüştürdükten Sonra Köprü Bağlantılarını Kaldır
linktitle: Html'den Dönüştürdükten Sonra Köprü Bağlantılarını Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzda, Aspose.PDF for .NET'i kullanarak HTML belgelerinizi PDF'ye dönüştürdükten sonra köprü metinlerinin nasıl kaldırılacağını öğrenin.
type: docs
weight: 250
url: /tr/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## giriiş

Dijital çağda, HTML belgelerini PDF'ye dönüştürmek yaygın bir görevdir. Ancak bazen okunabilirliği artırmak veya istenmeyen gezinmeyi önlemek gibi çeşitli nedenlerle dönüştürülen PDF'den köprü metinlerini kaldırmak isteyebilirsiniz. Bu eğitimde, bunu .NET için Aspose.PDF kullanarak nasıl başaracağınızı inceleyeceğiz. 

## Ön koşullar

Koda dalmadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. Bu sizin geliştirme ortamınız olacaktır.
2.  .NET için Aspose.PDF: Aspose.PDF kütüphanesine sahip olmanız gerekir. Bunu şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya aşinalık, kodu daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

1. Visual Studio projenizi açın.
2. Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
3.  Arama`Aspose.PDF` ve kurun.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Artık her şeyi ayarladığınıza göre, bir HTML dosyasını PDF'e dönüştürdükten sonra dosyadan köprü metinlerini kaldırma sürecini inceleyelim.

## Adım 1: Belge Dizinini Ayarlayın

İlk önce, belgeler dizininize giden yolu belirtmeniz gerekir. HTML dosyanızın bulunduğu ve çıktı PDF'inin kaydedileceği yer burasıdır.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` HTML dosyanızın saklandığı gerçek yol ile.

## Adım 2: HTML Belgesini Yükleyin

 Daha sonra, HTML belgesini kullanarak yükleyeceksiniz`Document` Aspose.PDF'den bir sınıf. Bu sınıf PDF belgeleriyle kolayca çalışmanızı sağlar.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Burada, adlı HTML dosyasını yüklüyoruz`SampleHtmlFile.html`Bu dosyanın belirttiğiniz dizinde bulunduğundan emin olun.

## Adım 3: Belgeyi Bellek Akışına Kaydet

Açıklamaları işlemeye başlamadan önce, belgeyi bir bellek akışına kaydetmemiz gerekir. Bu adım, belgeyi daha fazla işleme hazırladığı için önemlidir.

```csharp
doc.Save(new MemoryStream());
```

Bu satır belgeyi belleğe kaydeder ve şimdilik onu diske yazmadan üzerinde çalışmamıza olanak tanır.

## Adım 4: Açıklamalar Üzerinde Yineleme Yapın

Şimdi, belgedeki açıklamalar arasında yineleme yapacağız. Açıklamalar, bağlantılar, yorumlar ve vurgulamalar gibi öğelerdir. Özellikle bağlantı açıklamalarıyla ilgileniyoruz.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Bağlantı açıklamasını işle
    }
}
```

Bu döngüde, açıklama türünün bir bağlantı olup olmadığını kontrol ediyoruz. Eğer öyleyse, bir sonraki adımlara geçiyoruz.

## Adım 5: Köprü Bağlantısını Kaldırma Eylemi

Her bağlantı açıklaması için, bir köprü metni eylemi olup olmadığını kontrol etmemiz gerekir. Eğer varsa, köprü metnini URI'sini boş bir dizeye ayarlayarak kaldıracağız.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Bu kod parçacığı, köprü metni eyleminin etkili bir şekilde kaldırılmasını sağlar.

## Adım 6: Metin Parçalarını Emdirin

Sonra, bağlantı açıklamasıyla ilişkili metin parçalarını özümseyeceğiz. Bu, metin görünümünü değiştirmemize olanak tanır.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Burada bir tane yaratıyoruz`TextFragmentAbsorber` ve arama seçeneklerini açıklamanın dikdörtgenine ayarlayın. Bu, bağlantılı metni bulmamıza yardımcı olur.

## Adım 7: Metin Görünümünü Değiştirin

Metin parçalarına sahip olduğumuzda, görünümlerini değiştirebiliriz. Bu durumda, alt çizgiyi kaldıracağız ve metin rengini siyaha değiştireceğiz.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Bu adım, köprü metni stilini kaldırarak metnin okunabilirliğini artırır.

## Adım 8: Açıklamayı Silin

Metni düzenledikten sonra bağlantı açıklamasını belgeden güvenli bir şekilde silebiliriz.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Bu satır, köprü metnini PDF'den kaldırır ve nihai çıktıda artık mevcut olmamasını sağlar.

## Adım 9: Değiştirilen Belgeyi Kaydedin

Son olarak, değiştirilen belgeyi yeni bir PDF dosyasına kaydetmemiz gerekiyor. Bu, sürecimizdeki son adımdır.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Bu satır, köprü metinleri kaldırılmış belgeyi kaydeder ve yeni bir PDF dosyası oluşturur.`RemoveHyperlinksFromText_out.pdf`.

## Çözüm

Ve işte oldu! Aspose.PDF for .NET kullanarak bir HTML belgesini PDF'e dönüştürdükten sonra köprü metinlerini başarıyla kaldırdınız. Bu işlem yalnızca PDF'nizin okunabilirliğini artırmakla kalmaz, aynı zamanda sunduğunuz içerik üzerinde kontrol sahibi olmanızı da sağlar. 

## SSS

### Herhangi bir PDF belgesinden köprü metinlerini kaldırabilir miyim?
Evet, Aspose.PDF for .NET'i kullanarak herhangi bir PDF belgesinden köprü metinlerini kaldırabilirsiniz.

### Aspose.PDF'i kullanmak ücretsiz mi?
 Aspose.PDF ücretsiz deneme sunuyor ancak tüm özellikler için bir lisans satın almanız gerekiyor.[satın alma sayfası](https://purchase.aspose.com/buy).

### Aspose.PDF kullanırken sorunlarla karşılaşırsam ne olur?
 Yardım isteyebilirsiniz[destek forumu](https://forum.aspose.com/c/pdf/10).

### Aspose kullanarak diğer dosya formatlarını PDF'ye dönüştürebilir miyim?
Evet, Aspose PDF'ye dönüştürme için çeşitli dosya formatlarını destekler.

### Aspose.PDF for .NET'i nereden indirebilirim?
 Bunu şuradan indirebilirsiniz:[indirme bağlantısı](https://releases.aspose.com/pdf/net/).