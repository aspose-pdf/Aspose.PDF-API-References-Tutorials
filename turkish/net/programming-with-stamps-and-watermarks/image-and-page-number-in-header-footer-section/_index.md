---
title: Üstbilgi Altbilgi Bölümündeki Resim ve Sayfa Numarası
linktitle: Üstbilgi Altbilgi Bölümündeki Resim ve Sayfa Numarası
second_title: Aspose.PDF for .NET API Referansı
description: Aspose ile bir PDF belgesinin üstbilgisine ve altbilgisine nasıl resim ve sayfa numarası ekleyeceğinizi öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinin üst bilgi ve alt bilgi bölümüne nasıl resim ve sayfa numarası ekleyeceğiniz konusunda size adım adım rehberlik edeceğiz. Size bir sayfa oluşturmak, üstbilgi ve altbilgi ayarlamak, üstbilgiye resim ve belge altbilgisi PDF'sine sayfa numaralı metin eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF Belgesini ve Sayfasını Oluşturma

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

## 3. Adım: Resimli başlık ekleme

Artık sayfa oluşturulduğuna göre, resimli bir başlık bölümü ekleyebiliriz. İşte nasıl:

```csharp
// Bir başlık bölümü oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Sayfa başlığını ayarla
page. Header = header;

// Bir Görüntü nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Görüntü yolunu ayarla
image1.File = dataDir + "aspose-logo.jpg";

// Görüntüyü PDF belgesinin sayfa başlığına ekleyin
header.Paragraphs.Add(image1);
```

Yukarıdaki kod bir başlık bölümü oluşturur, bu bölümle sayfa başlığını ayarlar ve başlığa bir resim ekler.

## 4. Adım: Altbilgiyi sayfa numarasıyla ekleme

Artık üstbilgi eklendiğine göre, sayfa numarası içeren bir altbilgi bölümü ekleyebiliriz. İşte nasıl:

```csharp
// Bir alt bilgi bölümü oluşturun
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// PDF belgesinin altbilgisini tanımlayın
page. Footer = footer;

// Bir TextFragment nesnesi oluşturun
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Sayfa numarasını içeren metni PDF belgesinin altbilgisine ekleyin
footer.Paragraphs.Add(txt);
```

Yukarıdaki kod bir altbilgi bölümü oluşturur, bu bölümün bulunduğu sayfanın altbilgisini ayarlar ve "Page: ($p of $P )" metnini içeren bir TextFragment ekler.

  sayfa numarasını görüntüler.

## 5. Adım: Değiştirilen PDF belgesini kaydetme

Üst bilgi ve alt bilgi eklendikten sonra, değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanılarak Üstbilgi Altbilgi bölümünde Görüntü ve Sayfa Numarası için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
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

//Görüntü dosyasının yolunu ayarla
image1.File = dataDir + "aspose-logo.jpg";

// Pdf dosyasının Başlık sayfasına resim ekleyin
header.Paragraphs.Add(image1);

// Belgenin Alt Bilgi Bölümünü oluşturun
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// PDF dosyasının altbilgisini ayarlayın
page.Footer = footer;

// Bir Metin nesnesi oluşturun
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Pdf dosyasının Başlık bölümüne metin ekleyin
footer.Paragraphs.Add(txt);

// Pdf dosyasını kaydedin
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin üst bilgi ve alt bilgi bölümüne nasıl resim ve sayfa numarası ekleyeceğinizi öğrendiniz. Artık PDF belgelerinizdeki üstbilgi ve altbilgiyi özelleştirmek için bu yöntemi kullanabilirsiniz.

### SSS

#### S: Bir PDF belgesinin üst bilgi ve alt bilgi bölümüne resim ve sayfa numarası eklemenin amacı nedir?

Y: Bir PDF belgesinin üst bilgi ve alt bilgi bölümüne bir resim ve sayfa numarası eklemek, görsel çekiciliğini, marka bilincini ve gezinme öğelerini geliştirebilir. Bir resim bir logoyu, filigranı veya herhangi bir grafik öğeyi temsil edebilirken, sayfa numarası kullanıcıların ilerlemelerini takip etmelerine ve belirli sayfaları bulmalarına yardımcı olur.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin üstbilgisine ve altbilgisine görüntü ve sayfa numarası eklenmesine nasıl yardımcı olur?

A: Sağlanan kod, bir PDF belgesinin nasıl oluşturulacağını, bir sayfanın nasıl ekleneceğini ve ardından üst bilgi ve alt bilgi bölümlerinin nasıl özelleştirileceğini gösterir. Başlığa nasıl resim ve alt bilgiye sayfa numaralandırmalı bir metin parçasının nasıl ekleneceğini gösterir.

#### S: Başlık için herhangi bir resim formatı kullanabilir miyim ve yolunu nasıl belirtebilirim?

 C: Evet, başlık resmi için çeşitli resim formatlarını (JPEG, PNG, GIF vb.) kullanabilirsiniz. Resmin yolu kullanılarak belirtilir.`File` mülkiyeti`Aspose.Pdf.Image` nesne.

#### S: Başlık bölümündeki görüntünün görünümünü ve konumunu nasıl özelleştirebilirim?

 A: Görüntünün özelliklerini ayarlayarak görüntünün görünümünü ve konumunu özelleştirebilirsiniz.`Aspose.Pdf.Image` başlık bölümüne eklemeden önce nesne. Örneğin, görüntünün boyutlarını, hizalamasını, döndürmesini, opaklığını vb. ayarlayabilirsiniz.

####  S: Amacı nedir?`TextFragment` object used for the footer?

 C:`TextFragment`nesne, alt bilgi bölümünde görüntülenecek metni oluşturmak ve biçimlendirmek için kullanılır. Verilen kodda sayfa numarası ve toplam sayfa sayısını görüntülemek için kullanılır.

#### S: Ek bilgi veya biçimlendirme eklemek için altbilgi metnini değiştirebilir miyim?

 C: Evet, altbilgi metnini, içeriğini değiştirerek değiştirebilirsiniz.`TextFragment` nesne. Gereksinimlerinize göre ek metin ekleyebilir, yazı tiplerini, renkleri ve biçimlendirmeyi değiştirebilirsiniz.

#### S: PDF belgesinin farklı sayfalarına farklı üstbilgi ve altbilgi içerikleri uygulayabilir miyim?

 C: Evet, farklı üstbilgi ve altbilgi içeriklerini farklı sayfalar oluşturarak farklı sayfalara uygulayabilirsiniz.`HeaderFooter` kullanarak bunları belirli sayfalara atama`Header` Ve`Footer` özellikleri`Aspose.Pdf.Page` nesne.

#### S: Yazı tipi stillerini değiştirmek veya ek öğeler eklemek gibi üstbilgi ve altbilgiyi nasıl daha fazla özelleştirebilirim?

C: Aspose.PDF for .NET tarafından sağlanan çeşitli sınıfları ve özellikleri kullanarak üstbilgi ve altbilgiyi özelleştirebilirsiniz. Örneğin, farklı metin biçimlendirme seçenekleri kullanabilir, üst bilgi ve alt bilgi bölümlerine daha fazla paragraf, resim ve hatta tablo ekleyebilirsiniz.

#### S: Gerekirse üst bilgi ve alt bilgi bölümlerini kaldırabilir veya temizleyebilir miyim?

 C: Evet, üst bilgi ve alt bilgi bölümlerini ayarlayarak kaldırabilir veya temizleyebilirsiniz.`Header` Ve`Footer` özellikleri`Aspose.Pdf.Page` itiraz etmek`null`.

#### S: Eklenen resim ve sayfa numarasının farklı cihazlarda ve görüntüleyicilerde tutarlı kalmasını nasıl sağlayabilirim?

Y: Aspose.PDF for .NET, standartlaştırılmış ve tutarlı PDF belgeleri oluşturmak için işlevsellik sağlayarak, eklenen görüntü ve sayfa numarasının farklı cihazlarda ve PDF görüntüleyicilerde tutarlı bir şekilde görünmesini sağlar.