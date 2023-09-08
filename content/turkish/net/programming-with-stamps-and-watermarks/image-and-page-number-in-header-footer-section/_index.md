---
title: Üst Bilgi Alt Bilgi Bölümündeki Resim ve Sayfa Numarası
linktitle: Üst Bilgi Alt Bilgi Bölümündeki Resim ve Sayfa Numarası
second_title: .NET API Referansı için Aspose.PDF
description: Aspose ile bir PDF belgesinin üstbilgisine ve altbilgisine nasıl resim ve sayfa numarası ekleyeceğinizi öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinin üstbilgi ve altbilgi bölümüne nasıl resim ve sayfa numarası ekleyeceğiniz konusunda size adım adım rehberlik edeceğiz. Bir sayfa oluşturmak, üstbilgi ve altbilgiyi ayarlamak, üstbilgiye resim eklemek ve belge altbilgisi PDF'sine sayfa numarasıyla birlikte metin eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.

## Adım 2: PDF Belgesini ve Sayfasını Oluşturma

İlk adım, PDF belgesinde yeni bir Belge nesnesi ve bir sayfa oluşturmaktır. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir Belge nesnesi oluşturun
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Belgede bir sayfa oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();
```

Yukarıdaki kod, PDF belgesinde yeni bir Belge nesnesi ve boş bir sayfa oluşturur.

## 3. Adım: Resimli başlığı ekleme

Artık sayfa oluşturulduğuna göre resim içeren bir başlık bölümü ekleyebiliriz. İşte nasıl:

```csharp
// Başlık bölümü oluşturma
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Sayfa başlığını ayarlayın
page. Header = header;

// Bir Görüntü nesnesi oluşturma
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Görüntü yolunu ayarla
image1.File = dataDir + "aspose-logo.jpg";

// Görüntüyü PDF belgesinin sayfa başlığına ekleyin
header.Paragraphs.Add(image1);
```

Yukarıdaki kod bir başlık bölümü oluşturur, bu bölümle sayfa başlığını ayarlar ve başlığa bir resim ekler.

## Adım 4: Sayfa numarasını içeren alt bilgiyi ekleme

Artık başlık eklendiğine göre sayfa numarası içeren bir alt bilgi bölümü ekleyebiliriz. İşte nasıl:

```csharp
// Altbilgi bölümü oluşturma
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// PDF belgesinin altbilgisini tanımlayın
page. Footer = footer;

// TextFragment nesnesi oluşturma
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Sayfa numarasını içeren metni PDF belgesinin alt bilgisine ekleyin
footer.Paragraphs.Add(txt);
```

Yukarıdaki kod bir altbilgi bölümü oluşturur, bu bölümün bulunduğu sayfanın altbilgisini ayarlar ve "Sayfa: ($p / $P )" metnini içeren bir TextFragment ekler.

  sayfa numarasını görüntüler.

## Adım 5: Değiştirilen PDF belgesini kaydetme

Üstbilgi ve altbilgi eklendikten sonra değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanılarak Üst Bilgi Alt Bilgi bölümündeki Görüntü ve Sayfa Numarası için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Belge nesnesinde bir sayfa oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();

// Belgenin Başlık Bölümünü Oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// PDF dosyasının başlığını ayarlayın
page.Header = header;

// Sayfada bir resim nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Görüntü dosyasının yolunu ayarlayın
image1.File = dataDir + "aspose-logo.jpg";

// Pdf dosyasının Başlık sayfasına resim ekleyin
header.Paragraphs.Add(image1);

//Belgenin Alt Bilgi Bölümü Oluşturma
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// PDF dosyasının altbilgisini ayarlayın
page.Footer = footer;

// Metin nesnesi oluşturma
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Pdf dosyasının Başlık bölümüne metin ekleyin
footer.Paragraphs.Add(txt);

// Pdf dosyasını kaydedin
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin üstbilgi ve altbilgi bölümüne nasıl resim ve sayfa numarası ekleyeceğinizi öğrendiniz. Artık PDF belgelerinizdeki üstbilgi ve altbilgiyi özelleştirmek için bu yöntemi kullanabilirsiniz.

### SSS'ler

#### S: PDF belgesinin üstbilgi ve altbilgi bölümüne resim ve sayfa numarası eklemenin amacı nedir?

C: Bir PDF belgesinin üstbilgi ve altbilgi bölümüne bir resim ve sayfa numarası eklemek, belgenin görsel çekiciliğini, markasını ve gezinme öğelerini geliştirebilir. Bir resim bir logoyu, filigranı veya herhangi bir grafik öğesini temsil edebilir; sayfa numarası ise kullanıcıların ilerlemelerini takip etmelerine ve belirli sayfaları bulmalarına yardımcı olur.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin üstbilgisine ve altbilgisine resim ve sayfa numarası eklemede nasıl yardımcı olur?

C: Sağlanan kod, bir PDF belgesinin nasıl oluşturulacağını, bir sayfanın nasıl ekleneceğini ve ardından üstbilgi ve altbilgi bölümlerinin nasıl özelleştirileceğini gösterir. Başlığa bir görselin ve alt bilgiye sayfa numaralandırmalı bir metin parçasının nasıl ekleneceğini gösterir.

#### S: Başlık için herhangi bir görüntü formatını kullanabilir miyim ve yolunu nasıl belirleyebilirim?

 C: Evet, başlık görseli için çeşitli görsel formatlarını (JPEG, PNG, GIF vb.) kullanabilirsiniz. Resmin yolu kullanılarak belirtilir.`File` mülkiyeti`Aspose.Pdf.Image` nesne.

#### S: Başlık bölümündeki görselin görünümünü ve konumunu nasıl özelleştiririm?

 C: Görüntünün özelliklerini ayarlayarak görüntünün görünümünü ve konumunu özelleştirebilirsiniz.`Aspose.Pdf.Image` başlık bölümüne eklemeden önce nesneyi seçin. Örneğin görüntünün boyutlarını, hizalamasını, döndürmesini, opaklığını vb. ayarlayabilirsiniz.

####  Soru: Programın amacı nedir?`TextFragment` object used for the footer?

 C:`TextFragment` nesne, altbilgi bölümünde görüntülenecek metni oluşturmak ve biçimlendirmek için kullanılır. Verilen kodda sayfa numarasını ve toplam sayfa sayısını görüntülemek için kullanılmaktadır.

#### S: Alt bilgi metnini ek bilgi veya biçimlendirme içerecek şekilde değiştirebilir miyim?

 C: Evet, altbilgi metnini, içeriğini değiştirerek değiştirebilirsiniz.`TextFragment` nesne. Gereksinimlerinize göre ek metin ekleyebilir, yazı tiplerini, renkleri ve biçimlendirmeyi değiştirebilirsiniz.

#### S: PDF belgesinin farklı sayfalarına farklı üstbilgi ve altbilgi içerikleri uygulayabilir miyim?

 C: Evet, ayrı sayfalar oluşturarak farklı sayfalara farklı üstbilgi ve altbilgi içerikleri uygulayabilirsiniz.`HeaderFooter` kullanarak nesneleri belirli sayfalara atamak ve bunları belirli sayfalara atamak`Header` Ve`Footer` özellikleri`Aspose.Pdf.Page` nesne.

#### S: Yazı tipi stillerini değiştirmek veya ek öğeler eklemek gibi üstbilgi ve altbilgiyi nasıl daha fazla özelleştirebilirim?

C: Aspose.PDF for .NET tarafından sağlanan çeşitli sınıfları ve özellikleri kullanarak üstbilgi ve altbilgiyi özelleştirebilirsiniz. Örneğin, farklı metin biçimlendirme seçeneklerini kullanabilir, üstbilgi ve altbilgi bölümlerine daha fazla paragraf, resim ve hatta tablo ekleyebilirsiniz.

#### S: Gerekirse üst bilgi ve alt bilgi bölümlerini kaldırabilir veya temizleyebilir miyim?

C: Evet, üstbilgi ve altbilgi bölümlerini ayarlayarak kaldırabilir veya temizleyebilirsiniz.`Header` Ve`Footer` özellikleri`Aspose.Pdf.Page` itiraz etmek`null`.

#### S: Eklenen görselin ve sayfa numarasının farklı cihazlar ve izleyiciler arasında tutarlı kalmasını nasıl sağlayabilirim?

C: Aspose.PDF for .NET, standartlaştırılmış ve tutarlı PDF belgeleri oluşturmaya yönelik işlevsellik sağlayarak, eklenen görüntünün ve sayfa numarasının farklı cihazlarda ve PDF görüntüleyicilerde tutarlı bir şekilde görünmesini sağlar.