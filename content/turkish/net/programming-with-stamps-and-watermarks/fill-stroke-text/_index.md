---
title: PDF Dosyasındaki Kontur Metnini Doldur
linktitle: PDF Dosyasındaki Kontur Metnini Doldur
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasındaki metni nasıl kolayca doldurup çerçeveleyeceğinizi öğrenin.
type: docs
weight: 90
url: /tr/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak PDF dosyasındaki metni nasıl doldurup çerçeveleyeceğinizi adım adım anlatacağız. PDF dosyasındaki metne dolgu ve anahat renklerini uygulamak için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.

## Adım 2: TextState Nesnesini Oluşturma

İlk adım, gelişmiş özellikleri iletmek için bir TextState nesnesi oluşturmaktır. İşte nasıl:

```csharp
// Gelişmiş özellikleri aktarmak için TextState nesnesi oluşturun
TextState ts = new TextState();

// Anahat rengini ayarla
ts.StrokingColor = Color.Gray;

// Metin oluşturma modunu tanımlayın
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Yukarıdaki kod, yeni bir TextState nesnesi oluşturur ve anahat rengini ve metnin nasıl oluşturulacağını ayarlar.

## 3. Adım: PDF belgesini yükleme

Artık TextState nesnesi hazır olduğuna göre, PDF belgesini metin dolgusunu ve ana hatlarını uygulamak istediğimiz yere yükleyebiliriz. İşte nasıl:

```csharp
// PDF belgesini giriş olarak yükleyin
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Yukarıdaki kod, Aspose.PDF.Facades kütüphanesindeki PdfFileStamp sınıfını kullanarak mevcut PDF belgesini yükler.

## Adım 4: Metne Dolgu ve Kontur Ekleme

Artık PDF belgesi yüklendiğine göre metne dolgu ve anahat ekleyebiliriz. İşte nasıl:

```csharp
// Tanımlanmış metin ve özelliklere sahip bir damga (Damga) oluşturun
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// TextState nesnesini bağlayın
stamp.BindTextState(ts);

// Başlangıç noktasını ayarla X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Damgayı belgeye ekleme
fileStamp.AddStamp(stamp);
```

Yukarıdaki kod, belirtilen metin ve tanımlanmış Dolgu ve Kontur özelliklerine sahip bir Damga oluşturur.

## 5. Adım: Çıktı belgesini kaydedin

Metin damgası eklendikten sonra değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen belgeyi kaydet
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanılarak Kontur Metni Dolgusu için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Gelişmiş özellikleri aktarmak için TextState nesnesi oluşturun
TextState ts = new TextState();

// Kontur için rengi ayarla
ts.StrokingColor = Color.Gray;

// Metin oluşturma modunu ayarlama
ts.RenderingMode = TextRenderingMode.StrokeText;

// Giriş PDF belgesi yükleme
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// TextState'i Bağla
stamp.BindTextState(ts);

// X,Y kökenini ayarla
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki metni nasıl doldurup çerçeveleyeceğinizi öğrendiniz. Artık bu bilgiyi PDF belgelerinizdeki dolgu ve anahat renklerini özelleştirmek için uygulayabilirsiniz.

### PDF dosyasındaki dolgu kontur metni hakkında SSS

#### S: Bir PDF belgesindeki metni doldurmak ve ana hatlarını çizmek ne anlama gelir ve bunu ne zaman yapmam gerekebilir?

C: Bir PDF belgesindeki metnin doldurulması ve ana hatlarının belirlenmesi, metin karakterlerinin iç kısmına (dolgu) ve metnin etrafındaki kenarlıklara (anahat) renk uygulanmasını içerir. Bu, metnin görsel görünümünü geliştirmek, vurgu oluşturmak veya PDF'deki belirli içeriği vurgulamak için kullanılabilir.

#### S: Sağlanan C# kaynak kodu, bir PDF dosyasındaki metni doldurmayı ve ana hatlarını çizmeyi nasıl başarır?

 C: Sağlanan kaynak kodu nasıl oluşturulacağını gösterir.`TextState` Anahat rengi ve oluşturma modu gibi gelişmiş metin özelliklerini tanımlamak için nesne. Daha sonra mevcut bir PDF belgesini yüklemek, belirtilen dolgu ve kontur özelliklerine sahip metni içeren bir damga oluşturmak ve damgayı belgeye eklemek için Aspose.PDF.Facades'i kullanır.

####  Soru: Programın amacı nedir?`TextState` object in the code?

 C:`TextState`nesne, metin anahattının rengi (kontur) ve oluşturma modu dahil olmak üzere gelişmiş metin özelliklerini tanımlamak için kullanılır. Metnin kontur ve dolgu açısından nasıl görüneceğini özelleştirmenize olanak tanır.

#### S: Aynı metnin farklı bölümlerine farklı dolgu ve anahat renkleri uygulayabilir miyim?

 C: Evet, farklı oluşturmak için kodu değiştirebilirsiniz.`TextState` farklı dolgu ve anahat renklerine sahip nesneler oluşturabilir ve bunları ayrı ayrı kullanarak metnin belirli bölümlerine uygulayabilirsiniz.`Stamp` nesneler.

#### S: PDF belgesinde zaten mevcut olan metne dolgu ve anahat renklerini uygulayabilir miyim?

 C: Evet, uygun metin nesnelerini seçip bunları istediğiniz şekilde damga olarak ekleyerek PDF belgesindeki mevcut metne dolgu ve anahat renklerini uygulamak için benzer ilkeleri kullanabilirsiniz.`TextState` özellikler.

#### S: Doldurulmuş ve çerçeveleri çizilen metnin opaklığını ve karışımını nasıl ayarlayabilirim?

 C: Sağlanan kod, damganın opaklığını ve karışım özelliklerini ayarlamanıza olanak tanır.`Opacity` Ve`BlendingSpace`sırasıyla özellikler. İstediğiniz görsel efekti elde etmek için bu değerleri ayarlayabilirsiniz.

#### S: Aynı PDF belgesindeki birden fazla damgaya farklı dolgu ve anahat renklerini nasıl uygulayabilirim?

 C: Birden fazla oluşturabilirsiniz`TextState` farklı dolgu ve anahat renklerine sahip nesneler oluşturun ve ardından ayrı ayrı oluşturun`Stamp` her metin kümesi için farklı renklere sahip nesneler. Bu damgaları aynı PDF belgesine şunu kullanarak ekleyin:`PdfFileStamp` sınıf.

#### S: Özetlenen ve doldurulmuş metin için Arial dışında yazı tipleri kullanabilir miyim?

 C: Evet, yazı tipi adı parametresini değiştirerek yazı tipini değiştirebilirsiniz.`FormattedText` damgayı oluştururken yapıcı. Sisteminizde bulunan herhangi bir yazı tipini kullanabilirsiniz.

#### S: Ana hatları çizilen ve doldurulan metnin dönüş açısını nasıl değiştirebilirim?

 C: Sağlanan kod, damganın dönüş açısını kullanarak ayarlamanıza olanak tanır.`Rotation` mülk. Metin için istenen dönüş açısını belirtmek için bu özelliği ayarlayabilirsiniz.

#### S: Sayfadaki özetlenen ve doldurulmuş metnin konumunu ve boyutunu nasıl kontrol edebilirim?

C: Kullanabilirsiniz`SetOrigin` yöntemi`Stamp` Damganın sayfadaki konumunun X ve Y koordinatlarını ayarlamak için nesne. Ayrıca yazı tipi boyutunu da ayarlayabilirsiniz.`FormattedText` Metnin boyutunu kontrol etmek için yapıcı.