---
title: Üstbilgi Altbilgi Bölümündeki Resim ve Sayfa Numarası
linktitle: Üstbilgi Altbilgi Bölümündeki Resim ve Sayfa Numarası
second_title: Aspose.PDF for .NET API Referansı
description: Aspose ile bir PDF belgesinin üst bilgi ve alt bilgisine resim ve sayfa numarasının nasıl ekleneceğini öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinin üstbilgi ve altbilgi bölümüne resim ve sayfa numarası ekleme konusunda adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu kullanarak bir sayfa oluşturmayı, üstbilgi ve altbilgi ayarlamayı, üstbilgiye resim ve sayfa numarasıyla birlikte belge altbilgisi PDF'sine metin eklemeyi göstereceğiz.

## Adım 1: Ortamı kurma

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 2: PDF Belgesi ve Sayfasını Oluşturma

İlk adım, PDF belgesinde yeni bir Belge nesnesi ve bir sayfa oluşturmaktır. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir Belge nesnesi oluşturun
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Belgede bir sayfa oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();
```

Yukarıdaki kod PDF belgesinde yeni bir Belge nesnesi ve boş bir sayfa oluşturur.

## Adım 3: Görselle birlikte başlığı ekleme

Sayfa artık oluşturulduğuna göre, bir resimle birlikte bir başlık bölümü ekleyebiliriz. İşte nasıl:

```csharp
// Bir başlık bölümü oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Sayfa başlığını ayarlayın
page. Header = header;

// Bir Görüntü nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Görüntü yolunu ayarla
image1.File = dataDir + "aspose-logo.jpg";

// Resmi PDF belgesinin sayfa başlığına ekleyin
header.Paragraphs.Add(image1);
```

Yukarıdaki kod bir başlık bölümü oluşturur, bu bölümle sayfa başlığını ayarlar ve başlığa bir resim ekler.

## Adım 4: Sayfa numarasıyla altbilgi ekleme

Artık başlık eklendiğine göre, sayfa numarası olan bir altbilgi bölümü ekleyebiliriz. İşte nasıl:

```csharp
// Bir altbilgi bölümü oluşturun
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// PDF belgesinin altbilgisini tanımlayın
page. Footer = footer;

// Bir TextFragment nesnesi oluşturun
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// PDF belgesinin altbilgisine sayfa numarasıyla birlikte metni ekleyin
footer.Paragraphs.Add(txt);
```

Yukarıdaki kod bir footer bölümü oluşturur, sayfanın footer'ını bu bölümle ayarlar ve "Sayfa: ($p of $P )" metnini içeren bir TextFragment ekler.

  sayfa numarasını gösteren.

## Adım 5: Değiştirilen PDF belgesinin kaydedilmesi

Başlık ve altbilgi eklendikten sonra, değiştirilmiş PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Yukarıdaki kod düzenlenen PDF belgesini belirtilen dizine kaydeder.

### .NET için Aspose.PDF kullanarak Başlık Altbilgi bölümündeki Resim ve Sayfa Numarası için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Belge nesnesinde bir sayfa oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();

// Belgenin Başlık Bölümünü Oluştur
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// PDF dosyası için başlığı ayarlayın
page.Header = header;

// Sayfada bir resim nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Görüntü dosyasının yolunu ayarlayın
image1.File = dataDir + "aspose-logo.jpg";

// Pdf dosyasının Başlık sayfasına resim ekleyin
header.Paragraphs.Add(image1);

//Belgenin Alt Bilgi Bölümünü Oluşturun
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// PDF dosyasının altbilgisini ayarlayın
page.Footer = footer;

// Bir Metin nesnesi oluşturun
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Pdf dosyasının Başlık bölümüne metin ekleyin
footer.Paragraphs.Add(txt);

// PDF dosyasını kaydedin
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin üstbilgi ve altbilgi bölümüne resim ve sayfa numarası eklemeyi öğrendiniz. Şimdi bu yöntemi kullanarak PDF belgelerinizdeki üstbilgi ve altbilgiyi özelleştirebilirsiniz.

### SSS

#### S: PDF belgesinin üst bilgi ve alt bilgi bölümüne resim ve sayfa numarası eklemenin amacı nedir?

A: Bir PDF belgesinin üstbilgi ve altbilgi bölümüne bir resim ve sayfa numarası eklemek, görsel çekiciliğini, markasını ve gezinme öğelerini geliştirebilir. Bir resim bir logoyu, filigranı veya herhangi bir grafik öğeyi temsil edebilirken, bir sayfa numarası kullanıcıların ilerlemelerini takip etmelerine ve belirli sayfaları bulmalarına yardımcı olur.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin üst bilgi ve alt bilgisine resim ve sayfa numarası eklemede nasıl yardımcı olur?

A: Sağlanan kod, bir PDF belgesinin nasıl oluşturulacağını, bir sayfanın nasıl ekleneceğini ve ardından başlık ve altbilgi bölümlerinin nasıl özelleştirileceğini gösterir. Başlığa bir resim ve altbilgiye sayfa numaralandırması olan bir metin parçasının nasıl ekleneceğini gösterir.

#### S: Başlık için herhangi bir resim biçimini kullanabilir miyim ve yolunu nasıl belirtebilirim?

 A: Evet, başlık resmi için çeşitli resim formatlarını (JPEG, PNG, GIF vb. gibi) kullanabilirsiniz. Resmin yolu,`File` mülkiyeti`Aspose.Pdf.Image` nesne.

#### S: Başlık bölümündeki görselin görünümünü ve konumunu nasıl özelleştirebilirim?

 A: Görüntünün görünümünü ve konumunu, özelliklerini ayarlayarak özelleştirebilirsiniz.`Aspose.Pdf.Image` Başlık bölümüne eklemeden önce nesneyi ayarlayın. Örneğin, görüntünün boyutlarını, hizalamasını, dönüşünü, opaklığını vb. ayarlayabilirsiniz.

####  S: Amacı nedir?`TextFragment` object used for the footer?

 A:`TextFragment` nesnesi, altbilgi bölümünde görüntülenecek metni oluşturmak ve biçimlendirmek için kullanılır. Sağlanan kodda, sayfa numarasını ve toplam sayfa sayısını görüntülemek için kullanılır.

#### S: Ek bilgi veya biçimlendirme eklemek için altbilgi metnini değiştirebilir miyim?

 A: Evet, altbilginin içeriğini değiştirerek altbilgi metnini değiştirebilirsiniz.`TextFragment` nesne. İhtiyaçlarınıza göre ek metin ekleyebilir, yazı tiplerini, renkleri ve biçimlendirmeyi değiştirebilirsiniz.

#### S: PDF belgesinin farklı sayfalarına farklı üst bilgi ve alt bilgi içerikleri uygulayabilir miyim?

 A: Evet, ayrı başlık ve alt bilgi içerikleri oluşturarak farklı sayfalara farklı başlık ve alt bilgi içerikleri uygulayabilirsiniz.`HeaderFooter` nesneleri ve bunları kullanarak belirli sayfalara atama`Header` Ve`Footer` özellikleri`Aspose.Pdf.Page` nesne.

#### S: Üstbilgi ve altbilgiyi daha fazla nasıl özelleştirebilirim? Örneğin, yazı tipi stillerini değiştirebilir veya ek öğeler ekleyebilir miyim?

A: Aspose.PDF for .NET tarafından sağlanan çeşitli sınıfları ve özellikleri kullanarak üstbilgi ve altbilgiyi özelleştirebilirsiniz. Örneğin, farklı metin biçimlendirme seçenekleri kullanabilir, üstbilgi ve altbilgi bölümlerine daha fazla paragraf, resim veya hatta tablo ekleyebilirsiniz.

#### S: Gerektiğinde üstbilgi ve altbilgi bölümlerini kaldırabilir veya temizleyebilir miyim?

A: Evet, üst bilgi ve alt bilgi bölümlerini ayarlayarak kaldırabilir veya temizleyebilirsiniz.`Header` Ve`Footer` özellikleri`Aspose.Pdf.Page` itiraz etmek`null`.

#### S: Eklenen görselin ve sayfa numarasının farklı cihazlarda ve görüntüleyicilerde tutarlı kalmasını nasıl sağlayabilirim?

C: Aspose.PDF for .NET, standartlaştırılmış ve tutarlı PDF belgeleri oluşturma işlevi sunarak, eklenen görüntünün ve sayfa numarasının farklı cihazlarda ve PDF görüntüleyicilerde tutarlı bir şekilde görünmesini sağlar.