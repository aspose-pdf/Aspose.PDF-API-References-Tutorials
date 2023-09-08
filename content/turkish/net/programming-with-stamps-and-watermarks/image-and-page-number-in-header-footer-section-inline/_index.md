---
title: Üst Bilgi Alt Bilgi Bölümündeki Resim ve Sayfa Numarası Satır İçi
linktitle: Üst Bilgi Alt Bilgi Bölümündeki Resim ve Sayfa Numarası Satır İçi
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile satır içi paragrafları kullanarak üstbilgi ve altbilgiye resim ve sayfa numarası eklemeyi öğrenin.
type: docs
weight: 120
url: /tr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF belgesinin üstbilgi ve altbilgi bölümüne resim ve sayfa numarasının nasıl ekleneceği konusunda size adım adım rehberlik edeceğiz. PDF belgesinin başlığındaki satır içi paragrafları kullanarak sayfa oluşturmak, üstbilgi ve altbilgiyi ayarlamak, resim ve metin eklemek için sağlanan C# kaynak kodunu kullanacağız.

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
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Belgede bir sayfa oluşturun
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Yukarıdaki kod, PDF belgesinde yeni bir Belge nesnesi ve boş bir sayfa oluşturur.

## 3. Adım: Resim ve satır içi metin içeren başlığı ekleme

Artık sayfa oluşturulduğuna göre, satır içi paragrafları kullanarak resim ve metin içeren bir başlık bölümü ekleyebiliriz. İşte nasıl:

```csharp
// Başlık bölümü oluşturma
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Sayfa başlığını ayarlayın
page. Header = header;

// İlk satır içi metin için bir TextFragment nesnesi oluşturun
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Metin rengini belirtin
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Görüntü için bir Görüntü nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Görüntü yolunu ayarla
image1.File = dataDir + "aspose-logo.jpg";

// Resmin boyutlarını tanımlayın
image1.FixWidth = 50;
image1.FixHeight = 20;

// İlk satır içi metnin bir resim olduğunu belirtin
image1.IsInLineParagraph = true;

// İkinci bir satır içi metin oluşturun
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Başlığa öğe ekle
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Yukarıdaki kod bir başlık bölümü oluşturur, bu bölümle sayfa başlığını ayarlar, satır içi metin içeren bir TextFragment ve satır içi Image nesnesi ekler.

## Adım 4: Değiştirilen PDF belgesini kaydetme

Görüntüyü ve satır içi metni içeren başlık eklendikten sonra değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Satır İçi Başlık Alt Bilgi bölümündeki Görüntü ve Sayfa Numarası için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş yapıcısını çağırarak bir Document nesnesinin örneğini oluşturun
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Pdf nesnesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Belgenin Başlık Bölümünü Oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// PDF dosyasının başlığını ayarlayın
page.Header = header;

// Metin nesnesi oluşturma
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Rengi belirtin
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Bölümde bir görüntü nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Görüntü dosyasının yolunu ayarlayın
image1.File = dataDir + "aspose-logo.jpg";

// Görüntü genişliğini ayarlayın Bilgi
image1.FixWidth = 50;
image1.FixHeight = 20;

// Seg1'in InlineParagraph'ının bir resim olduğunu belirtin.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// PDF'yi kaydet
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET ile satır içi paragrafları kullanarak bir PDF belgesinin üstbilgi ve altbilgi bölümüne nasıl resim ve sayfa numarası ekleyeceğinizi öğrendiniz. Artık PDF belgelerinizin üstbilgisini ve altbilgisini esnek bir şekilde özelleştirebilirsiniz.

### SSS'ler

#### S: PDF belgesinin başlığına resim ve metin eklemek için satır içi paragraf kullanmanın avantajı nedir?

C: Satır içi paragrafları kullanmak, görselleri ve metni aynı paragraf içinde sorunsuz bir şekilde entegre etmenize olanak tanıyarak bunların yerleşimi ve biçimlendirmesi üzerinde hassas kontrol sağlar. Bu yöntem özellikle görsel öğeler içeren özelleştirilmiş başlıklar oluşturmak için kullanışlıdır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesindeki başlık için satır içi paragrafları nasıl elde eder?

C: Sağlanan kod, bir PDF belgesinin nasıl oluşturulacağını, sayfa ekleneceğini ve satır içi paragraflar kullanılarak başlığın nasıl özelleştirileceğini gösterir. Satır içi metin içeren bir TextFragment, bir satır içi görüntü ve başka bir satır içi TextFragment ekler.

#### S: Başlıktaki satır içi metnin rengini nasıl belirlerim?

 C: Satır içi metnin rengi şu komut kullanılarak belirtilir:`ForegroundColor` mülkiyeti`TextState` arasında`TextFragment` nesne.

#### S: Başlıktaki satır içi görüntünün boyutlarını ayarlayabilir miyim?

 C: Evet, satır içi görüntünün boyutlarını aşağıdaki düğmeyi kullanarak ayarlayabilirsiniz:`FixWidth` Ve`FixHeight` özellikleri`Image` nesne. Bu, başlıktaki görüntünün genişliğini ve yüksekliğini kontrol etmenize olanak tanır.

#### S: Başlığa köprüler veya farklı yazı tipi stilleri gibi ek satır içi öğeler ekleyebilir miyim?

 C: Evet, daha fazla öğe oluşturarak başlığa ek satır içi öğeler ekleyebilirsiniz.`TextFragment` veya`Image` İstenilen özelliklere sahip nesneler. Bu, köprüler, farklı yazı tipi stilleri veya diğer görsel öğeler de dahil olmak üzere başlığı daha da özelleştirmenize olanak tanır.

#### S: Satır içi görselin ve metnin farklı cihazlar ve izleyiciler arasında düzgün şekilde hizalandığından ve biçimlendirildiğinden nasıl emin olabilirim?

C: Aspose.PDF for .NET, satır içi görsellerin ve metinlerin düzgün şekilde hizalanmasını ve formatlanmasını sağlayarak farklı cihazlar ve PDF görüntüleyiciler arasında tutarlı bir görünüm sağlar.

#### S: Satır içi paragrafları altbilgi bölümüne de uygulayabilir miyim?

 C: Evet, satır içi paragraf kullanma tekniğinin aynısını altbilgi bölümüne de uygulayabilirsiniz.`Footer` nesne ve ona metin ve resimler gibi satır içi öğeler ekleme.

#### S: Satır içi paragrafları diğer üstbilgi veya altbilgi özelleştirme yöntemleriyle birleştirmek mümkün müdür?

C: Evet, daha karmaşık ve özelleştirilmiş üstbilgi veya altbilgi tasarımları oluşturmak için satır içi paragrafları Aspose.PDF for .NET tarafından sağlanan diğer üstbilgi veya altbilgi özelleştirme yöntemleriyle birleştirebilirsiniz.

#### S: Gerekirse başlıktaki satır içi öğeleri kaldırabilir veya temizleyebilir miyim?

 C: Evet, satır içi öğeleri, içeriğini değiştirerek kaldırabilir veya temizleyebilirsiniz.`HeaderFooter` nesne ve ilgili satır içi paragrafların kaldırılması.

#### S: Satır içi paragrafları PDF belgesinin belirli sayfalarına nasıl uygulayabilirim?

 C: Satır içi paragrafları belirli sayfalara uygulamak için ayrı paragraflar oluşturabilirsiniz.`HeaderFooter` her sayfa için nesneler ve bunları kullanarak atayın`Header` ilgilinin mülkiyeti`Aspose.Pdf.Page` nesneler.