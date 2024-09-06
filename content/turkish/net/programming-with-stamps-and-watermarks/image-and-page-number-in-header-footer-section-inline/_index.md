---
title: Üstbilgi Altbilgi Bölümünde Resim ve Sayfa Numarası Satır İçi
linktitle: Üstbilgi Altbilgi Bölümünde Resim ve Sayfa Numarası Satır İçi
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile satır içi paragrafları kullanarak üstbilgi ve altbilgiye resim ve sayfa numarasının nasıl ekleneceğini öğrenin.
type: docs
weight: 120
url: /tr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF belgesinin üstbilgi ve altbilgi bölümüne resim ve sayfa numarasının nasıl ekleneceğini adım adım göstereceğiz. Sağlanan C# kaynak kodunu kullanarak bir sayfa oluşturacağız, üstbilgi ve altbilgiyi ayarlayacağız, PDF belgesinin üstbilgisine satır içi paragraflar kullanarak resim ve metin ekleyeceğiz.

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
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Belgede bir sayfa oluşturun
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Yukarıdaki kod PDF belgesinde yeni bir Belge nesnesi ve boş bir sayfa oluşturur.

## Adım 3: Resim ve satır içi metin içeren başlığı ekleme

Sayfa artık oluşturulduğuna göre, satır içi paragraflar kullanarak resim ve metin içeren bir başlık bölümü ekleyebiliriz. İşte nasıl:

```csharp
// Bir başlık bölümü oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Sayfa başlığını ayarlayın
page. Header = header;

// İlk satır içi metin için bir TextFragment nesnesi oluşturun
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Metin rengini belirtin
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Resim için bir Resim nesnesi oluşturun
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

// Üstbilgiye öğeler ekle
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Yukarıdaki kod bir header bölümü oluşturur, bu bölümle sayfa başlığını ayarlar, satır içi metin içeren bir TextFragment ve satır içi Image nesnesi ekler.

## Adım 4: Değiştirilen PDF belgesinin kaydedilmesi

Resim ve satır içi metin içeren başlık eklendiğinde, değiştirilmiş PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Yukarıdaki kod düzenlenen PDF belgesini belirtilen dizine kaydeder.

### .NET için Aspose.PDF kullanarak Üstbilgi Altbilgi bölümündeki Resim ve Sayfa Numarası için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak bir Belge nesnesi örneği oluşturun
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Pdf nesnesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Belgenin Başlık Bölümünü Oluştur
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// PDF dosyası için başlığı ayarlayın
page.Header = header;

// Bir Metin nesnesi oluşturun
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Rengi belirtin
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Bölümde bir resim nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Görüntü dosyasının yolunu ayarlayın
image1.File = dataDir + "aspose-logo.jpg";

//Resim genişliğini ayarlayın Bilgi
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

// PDF'yi kaydet
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET ile satır içi paragraflar kullanarak bir PDF belgesinin üstbilgi ve altbilgi bölümüne resim ve sayfa numarası eklemeyi öğrendiniz. Artık PDF belgelerinizin üstbilgi ve altbilgisini esnek bir şekilde özelleştirebilirsiniz.

### SSS

#### S: PDF belgesinin başlığına resim ve metin eklemek için satır içi paragrafları kullanmanın avantajı nedir?

A: Satır içi paragrafları kullanmak, aynı paragrafta görselleri ve metni sorunsuz bir şekilde entegre etmenize olanak tanır ve bunların yerleşimi ve biçimlendirmesi üzerinde hassas kontrol sağlar. Bu yöntem, özellikle görsel öğelerle özelleştirilmiş başlıklar oluşturmak için kullanışlıdır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesindeki başlık için satır içi paragrafları nasıl elde ediyor?

A: Sağlanan kod, PDF belgesi oluşturmayı, sayfa eklemeyi ve satır içi paragraflar kullanarak başlığı özelleştirmeyi gösterir. Satır içi metin, satır içi resim ve başka bir satır içi TextFragment içeren bir TextFragment ekler.

#### S: Başlıktaki satır içi metnin rengini nasıl belirleyebilirim?

 A: Satır içi metnin rengi, şunu kullanarak belirtilir:`ForegroundColor` mülkiyeti`TextState` of'un`TextFragment` nesne.

#### S: Başlıktaki satır içi görselin boyutlarını ayarlayabilir miyim?

 A: Evet, satır içi görüntünün boyutlarını kullanarak ayarlayabilirsiniz.`FixWidth` Ve`FixHeight` özellikleri`Image` nesne. Bu, başlık içindeki görüntünün genişliğini ve yüksekliğini kontrol etmenizi sağlar.

#### S: Üst bilgiye köprü metinleri veya farklı yazı tipleri gibi ek satır içi öğeler ekleyebilir miyim?

 A: Evet, daha fazla öğe oluşturarak başlığa ek satır içi öğeler ekleyebilirsiniz.`TextFragment` veya`Image` İstenilen özelliklere sahip nesneler. Bu, köprü metinleri, farklı yazı tipleri veya diğer görsel öğeler dahil olmak üzere başlığı daha da özelleştirmenize olanak tanır.

#### S: Satır içi görselin ve metnin farklı cihazlarda ve görüntüleyicilerde düzgün şekilde hizalanmasını ve biçimlendirilmesini nasıl sağlayabilirim?

A: Aspose.PDF for .NET, satır içi görsellerin ve metinlerin düzgün şekilde hizalanmasını ve biçimlendirilmesini sağlayarak farklı cihazlarda ve PDF görüntüleyicilerinde tutarlı bir görünüm sağlar.

#### S: Satır içi paragrafları altbilgi bölümüne de uygulayabilir miyim?

 A: Evet, aynı satır içi paragraf kullanma tekniğini altbilgi bölümüne de uygulayabilirsiniz.`Footer` nesneye metin ve resim gibi satır içi öğeler eklemek.

#### S: Satır içi paragrafları diğer üstbilgi veya altbilgi özelleştirme yöntemleriyle birleştirmek mümkün müdür?

C: Evet, Aspose.PDF for .NET tarafından sağlanan diğer üstbilgi veya altbilgi özelleştirme yöntemleriyle satır içi paragrafları birleştirerek daha karmaşık ve özelleştirilmiş üstbilgi veya altbilgi tasarımları oluşturabilirsiniz.

#### S: Gerektiğinde başlıktaki satır içi öğeleri kaldırabilir veya temizleyebilir miyim?

 A: Evet, satır içi öğeleri, içeriklerini değiştirerek kaldırabilir veya temizleyebilirsiniz.`HeaderFooter`nesne ve ilgili satır içi paragrafları kaldırma.

#### S: PDF belgesinin belirli sayfalarına satır içi paragrafları nasıl uygulayabilirim?

 A: Belirli sayfalara satır içi paragraflar uygulamak için ayrı sayfalar oluşturabilirsiniz.`HeaderFooter` her sayfa için nesneler belirleyin ve bunları kullanarak atayın`Header` ilgili kişinin mülkiyeti`Aspose.Pdf.Page` nesneler.