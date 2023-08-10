---
title: Üst Bilgi Alt Bilgi Bölümü Satır İçi Görüntü ve Sayfa Numarası
linktitle: Üst Bilgi Alt Bilgi Bölümü Satır İçi Görüntü ve Sayfa Numarası
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile satır içi paragrafları kullanarak üst bilgiye ve alt bilgiye nasıl resim ve sayfa numarası ekleyeceğinizi öğrenin.
type: docs
weight: 120
url: /tr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF belgesinin üst bilgi ve alt bilgi bölümüne nasıl resim ve sayfa numarası ekleyeceğiniz konusunda adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu bir sayfa oluşturmak, üstbilgi ve altbilgi ayarlamak, PDF belgesinin başlığındaki satır içi paragrafları kullanarak resim ve metin eklemek için kullanacağız.

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
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Belgede bir sayfa oluşturun
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Yukarıdaki kod, PDF belgesinde yeni bir Belge nesnesi ve boş bir sayfa oluşturur.

## 3. Adım: Resim ve satır içi metin içeren üst bilgi ekleme

Artık sayfa oluşturulduğundan, satır içi paragrafları kullanarak resim ve metin içeren bir başlık bölümü ekleyebiliriz. İşte nasıl:

```csharp
// Bir başlık bölümü oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Sayfa başlığını ayarla
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

Yukarıdaki kod bir başlık bölümü oluşturur, bu bölümle birlikte sayfa başlığını ayarlar, satır içi metin içeren bir TextFragment ve satır içi Image nesnesi ekler.

## 4. Adım: Değiştirilen PDF belgesini kaydetme

Resim ve satır içi metin içeren başlık eklendikten sonra, değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanılarak Satır İçi Üstbilgi Altbilgi bölümünde Görüntü ve Sayfa Numarası için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak bir Document nesnesinin örneğini oluşturun
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Pdf nesnesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Belgenin Başlık Bölümünü Oluştur
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// PDF dosyası için başlığı ayarlayın
page.Header = header;

// Bir Metin nesnesi oluşturun
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// rengi belirtin
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Bölümde bir resim nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//Görüntü dosyasının yolunu ayarla
image1.File = dataDir + "aspose-logo.jpg";

// Görüntü genişliğini ayarla Bilgi
image1.FixWidth = 50;
image1.FixHeight = 20;

// seg1'in InlineParagraph'ının bir resim olduğunu belirtin.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Pdf'i kaydet
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET ile satır içi paragraflar kullanarak bir PDF belgesinin üst bilgi ve alt bilgi bölümüne nasıl resim ve sayfa numarası ekleyeceğinizi öğrendiniz. Artık PDF belgelerinizin üst bilgisini ve alt bilgisini esnek bir şekilde özelleştirebilirsiniz.

### SSS

#### S: Bir PDF belgesinin başlığına resim ve metin eklemek için satır içi paragraflar kullanmanın avantajı nedir?

Y: Satır içi paragrafları kullanmak, görüntüleri ve metni aynı paragraf içinde sorunsuz bir şekilde entegre etmenize olanak tanıyarak bunların yerleşimi ve biçimlendirmesi üzerinde hassas kontrol sağlar. Bu yöntem, özellikle görsel öğeler içeren özelleştirilmiş başlıklar oluşturmak için kullanışlıdır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesindeki başlık için satır içi paragraflara nasıl ulaşır?

A: Sağlanan kod, bir PDF belgesinin nasıl oluşturulacağını, bir sayfanın nasıl ekleneceğini ve satır içi paragraflar kullanılarak başlığın nasıl özelleştirileceğini gösterir. Satır içi metin, satır içi görüntü ve başka bir satır içi TextFragment içeren bir TextFragment ekler.

#### S: Başlıktaki satır içi metnin rengini nasıl belirlerim?

 C: Satır içi metnin rengi,`ForegroundColor` mülkiyeti`TextState` arasında`TextFragment` nesne.

#### S: Başlıktaki satır içi görüntünün boyutlarını ayarlayabilir miyim?

 C: Evet, satır içi görüntünün boyutlarını kullanarak ayarlayabilirsiniz.`FixWidth` Ve`FixHeight` özellikleri`Image` nesne. Bu, başlık içindeki görüntünün genişliğini ve yüksekliğini kontrol etmenizi sağlar.

#### S: Başlığa köprüler veya farklı yazı tipi stilleri gibi ek satır içi öğeler ekleyebilir miyim?

 C: Evet, daha fazla satır içi öğe oluşturarak başlığa ek satır içi öğeler ekleyebilirsiniz.`TextFragment` veya`Image` istenen özelliklere sahip nesneler. Bu, köprüler, farklı yazı tipi stilleri veya diğer görsel öğeler dahil olmak üzere başlığı daha da özelleştirmenize olanak tanır.

#### S: Satır içi görüntünün ve metnin farklı cihazlarda ve görüntüleyicilerde düzgün bir şekilde hizalanmış ve biçimlendirilmiş olarak kalmasını nasıl sağlayabilirim?

Y: Aspose.PDF for .NET, satır içi görüntülerin ve metnin düzgün bir şekilde hizalanmasını ve biçimlendirilmesini sağlayarak, farklı cihazlarda ve PDF görüntüleyicilerde tutarlı bir görünüm sağlar.

#### S: Satır içi paragrafları alt bilgi bölümüne de uygulayabilir miyim?

 C: Evet, satır içi paragraf kullanma tekniğini altbilgi bölümüne de uygulayabilirsiniz.`Footer` nesne ve buna metin ve resimler gibi satır içi öğeler ekleme.

#### S: Satır içi paragrafları diğer üstbilgi veya altbilgi özelleştirme yöntemleriyle birleştirmek mümkün müdür?

C: Evet, daha karmaşık ve uyarlanmış üst bilgi veya alt bilgi tasarımları oluşturmak için satır içi paragrafları Aspose.PDF for .NET tarafından sağlanan diğer üst bilgi veya alt bilgi özelleştirme yöntemleriyle birleştirebilirsiniz.

#### S: Gerekirse başlıktaki satır içi öğeleri kaldırabilir veya temizleyebilir miyim?

 C: Evet, satır içi öğeleri, satır içi öğelerin içeriğini değiştirerek kaldırabilir veya temizleyebilirsiniz.`HeaderFooter` nesne ve ilgili satır içi paragrafları kaldırma.

#### S: Satır içi paragrafları PDF belgesinin belirli sayfalarına nasıl uygulayabilirim?

 C: Satır içi paragrafları belirli sayfalara uygulamak için ayrı sayfalar oluşturabilirsiniz.`HeaderFooter` her sayfa için nesneler ve bunları kullanarak atayın`Header` ilgili mülkiyet`Aspose.Pdf.Page` nesneler.