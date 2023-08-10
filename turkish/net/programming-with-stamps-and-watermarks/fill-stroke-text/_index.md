---
title: PDF Dosyasında Kontur Metni Doldur
linktitle: PDF Dosyasında Kontur Metni Doldur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki metni nasıl kolayca dolduracağınızı ve ana hatları çizeceğinizi öğrenin.
type: docs
weight: 90
url: /tr/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasındaki metni nasıl dolduracağınızı ve ana hatları çizeceğinizi adım adım göstereceğiz. PDF dosyasındaki metne dolgu ve anahat renkleri uygulamak için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: TextState Nesnesini Oluşturma

İlk adım, gelişmiş özellikleri geçirmek için bir TextState nesnesi oluşturmaktır. İşte nasıl:

```csharp
// Gelişmiş özellikleri aktarmak için TextState nesnesi oluşturun
TextState ts = new TextState();

// Anahat rengini ayarla
ts.StrokingColor = Color.Gray;

// Metin oluşturma modunu tanımlayın
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Yukarıdaki kod, yeni bir TextState nesnesi oluşturur ve anahat rengini ve metnin nasıl işlendiğini ayarlar.

## 3. Adım: PDF belgesini yükleme

Artık TextState nesnesi hazır olduğuna göre, PDF belgesini metin dolgusu ve anahattı uygulamak istediğimiz yere yükleyebiliriz. İşte nasıl:

```csharp
// PDF belgesini girdi olarak yükleyin
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Yukarıdaki kod, Aspose.PDF.Facades kitaplığından PdfFileStamp sınıfını kullanarak mevcut PDF belgesini yükler.

## 4. Adım: Metne Dolgu ve Kontur Ekleyin

Artık PDF belgesi yüklendiğine göre, metne dolgu ve anahat ekleyebiliriz. İşte nasıl:

```csharp
// Tanımlanan metin ve özelliklerle bir damga (Damga) oluşturun
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// TextState nesnesini bağlayın
stamp.BindTextState(ts);

// X, Y orijinini ayarla
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Belgeye damga ekleyin
fileStamp.AddStamp(stamp);
```

Yukarıdaki kod, belirtilen metne ve tanımlanmış Dolgu ve Kontur özelliklerine sahip bir Damga oluşturur.

## Adım 5: Çıktı belgesini kaydedin

Metin damgası eklendikten sonra, değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen belgeyi kaydet
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanan Fill Stroke Text için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Gelişmiş özellikleri aktarmak için TextState nesnesi oluşturun
TextState ts = new TextState();

// Kontur için renk ayarla
ts.StrokingColor = Color.Gray;

// Metin oluşturma modunu ayarla
ts.RenderingMode = TextRenderingMode.StrokeText;

// Bir giriş PDF belgesi yükleyin
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Metin Durumunu Bağla
stamp.BindTextState(ts);

// X,Y orijinini ayarla
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Damga Ekle
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki metni nasıl dolduracağınızı ve ana hatları çizeceğinizi öğrendiniz. Artık bu bilgiyi PDF belgelerinizdeki dolgu ve anahat renklerini özelleştirmek için uygulayabilirsiniz.

### PDF dosyasındaki dolgu konturu metni hakkında SSS

#### S: Bir PDF belgesinde metni doldurmak ve ana hatlarını çizmek ne anlama gelir ve bunu ne zaman yapmam gerekebilir?

Y: Bir PDF belgesindeki metni doldurmak ve ana hatları çizmek, metin karakterlerinin iç kısmına (doldurma) ve metnin etrafındaki kenarlıklara (anahat) renk uygulamayı içerir. Bu, metnin görsel görünümünü iyileştirmek, vurgu oluşturmak veya PDF içindeki belirli içeriği vurgulamak için kullanılabilir.

#### S: Sağlanan C# kaynak kodu, bir PDF dosyasındaki metni doldurmayı ve ana hatları çizmeyi nasıl başarıyor?

 C: Sağlanan kaynak kodu, nasıl oluşturulacağını gösterir.`TextState` anahat rengi ve oluşturma modu gibi gelişmiş metin özelliklerini tanımlamak için nesne. Daha sonra Aspose.PDF.Facades'i kullanarak mevcut bir PDF belgesini yükleyin, belirtilen dolgu ve kontur özelliklerine sahip metni içeren bir damga oluşturun ve damgayı belgeye ekleyin.

####  S: Amacı nedir?`TextState` object in the code?

 C:`TextState`nesne, metin anahattının rengi (kontur) ve oluşturma modu dahil olmak üzere gelişmiş metin özelliklerini tanımlamak için kullanılır. Metnin kontur ve dolgu açısından nasıl görüneceğini özelleştirmenize olanak tanır.

#### S: Aynı metnin farklı bölümlerine farklı dolgu ve anahat renkleri uygulayabilir miyim?

 C: Evet, farklı oluşturmak için kodu değiştirebilirsiniz.`TextState` farklı dolgu ve anahat renklerine sahip nesneler ve bunları ayrı kullanarak metnin belirli bölümlerine uygulayın`Stamp` nesneler.

#### S: PDF belgesinde zaten mevcut olan metne dolgu ve anahat renkleri uygulayabilir miyim?

 C: Evet, benzer ilkeleri kullanarak PDF belgesindeki mevcut metne dolgu ve anahat renkleri uygulayabilirsiniz.`TextState` özellikler.

#### S: Doldurulmuş ve çerçevelenmiş metnin opaklığını ve karışımını nasıl ayarlayabilirim?

 A: Sağlanan kod, damganın opaklığını ve karıştırma özelliklerini ayarlamanıza izin verir.`Opacity` Ve`BlendingSpace`sırasıyla özellikler. İstenen görsel efekti elde etmek için bu değerleri ayarlayabilirsiniz.

#### S: Aynı PDF belgesindeki birden çok damgaya farklı dolgu ve dış hat renkleri nasıl uygulayabilirim?

 C: Birden çok oluşturabilirsiniz`TextState` farklı dolgu ve anahat renklerine sahip nesneleri seçin ve ardından ayrı ayrı oluşturun`Stamp` her metin kümesi için farklı renklere sahip nesneler. kullanarak bu damgaları aynı PDF belgesine ekleyin.`PdfFileStamp` sınıf.

#### S: Ana hatları çizilen ve doldurulmuş metin için Arial dışında yazı tipleri kullanabilir miyim?

 A: Evet, yazı tipini, içindeki yazı tipi adı parametresini değiştirerek değiştirebilirsiniz.`FormattedText` damga oluştururken yapıcı. Sisteminizde bulunan herhangi bir yazı tipini kullanabilirsiniz.

#### S: Ana hatları çizilen ve doldurulmuş metnin dönüş açısını nasıl değiştirebilirim?

 A: Sağlanan kod, damganın dönüş açısını kullanarak ayarlamanıza izin verir.`Rotation` mülk. Metin için istenen döndürme açısını belirtmek için bu özelliği ayarlayabilirsiniz.

#### S: Sayfadaki ana hatları çizilen ve doldurulmuş metnin konumunu ve boyutunu nasıl kontrol edebilirim?

C: Şunu kullanabilirsiniz:`SetOrigin` yöntemi`Stamp` damganın sayfadaki konumunun X ve Y koordinatlarını ayarlamak için nesne. Ek olarak, yazı tipi boyutunu da ayarlayabilirsiniz.`FormattedText` metnin boyutunu kontrol etmek için yapıcı.