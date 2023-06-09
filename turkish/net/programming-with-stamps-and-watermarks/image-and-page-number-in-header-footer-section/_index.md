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

// Görüntü dosyasının yolunu ayarla
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
