---
title: PDF Dosyasında Vuruş Metnini Doldur
linktitle: PDF Dosyasında Vuruş Metnini Doldur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki metni nasıl kolayca dolduracağınızı ve ana hatlarını nasıl çıkaracağınızı öğrenin.
type: docs
weight: 90
url: /tr/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasındaki metni nasıl dolduracağınızı ve ana hatlarını nasıl çizeceğinizi adım adım göstereceğiz. PDF dosyasındaki metne dolgu ve ana hat renklerini uygulamak için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Adım 1: Ortamı kurma

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 2: TextState Nesnesini Oluşturma

İlk adım, gelişmiş özellikleri geçirmek için bir TextState nesnesi oluşturmaktır. İşte nasıl:

```csharp
// Gelişmiş özellikleri aktarmak için TextState nesnesi oluşturun
TextState ts = new TextState();

// Anahat rengini ayarla
ts.StrokingColor = Color.Gray;

// Metin oluşturma modunu tanımlayın
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Yukarıdaki kod yeni bir TextState nesnesi oluşturur ve metnin anahat rengini ve nasıl işleneceğini ayarlar.

## Adım 3: PDF belgesini yükleme

Artık TextState nesnesi hazır olduğuna göre, metin dolgusunu ve taslağını uygulamak istediğimiz PDF belgesini yükleyebiliriz. İşte nasıl:

```csharp
// PDF belgesini giriş olarak yükleyin
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Yukarıdaki kod, Aspose.PDF.Facades kütüphanesindeki PdfFileStamp sınıfını kullanarak mevcut PDF belgesini yükler.

## Adım 4: Metne Dolgu ve Kontur Ekleme

Artık PDF belgesi yüklendiğine göre, metne dolgu ve anahat ekleyebiliriz. İşte nasıl:

```csharp
// Tanımlı metin ve özelliklerle bir damga (Damga) oluşturun
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// TextState nesnesini bağlayın
stamp.BindTextState(ts);

// Kökeni X, Y olarak ayarla
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Belgeye damgayı ekleyin
fileStamp.AddStamp(stamp);
```

Yukarıdaki kod belirtilen metin ve tanımlanmış Dolgu ve Kontur özellikleriyle bir Damga oluşturur.

## Adım 5: Çıktı belgesini kaydedin

Metin damgası eklendikten sonra, değiştirilmiş PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen belgeyi kaydet
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Yukarıdaki kod düzenlenen PDF belgesini belirtilen dizine kaydeder.

### .NET için Aspose.PDF kullanarak Dolgu Vuruşlu Metin için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Gelişmiş özellikleri aktarmak için TextState nesnesi oluşturun
TextState ts = new TextState();

// Vuruş için renk ayarla
ts.StrokingColor = Color.Gray;

// Metin oluşturma modunu ayarla
ts.RenderingMode = TextRenderingMode.StrokeText;

// Bir giriş PDF belgesi yükleyin
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// TextState'i Bağla
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde metni nasıl dolduracağınızı ve ana hatlarını nasıl çizeceğinizi öğrendiniz. Şimdi bu bilgiyi PDF belgelerinizdeki dolgu ve ana hat renklerini özelleştirmek için kullanabilirsiniz.

### PDF dosyasında dolgu vuruşu metni için SSS

#### S: Bir PDF belgesinde metni doldurmak ve ana hatlarını çıkarmak ne anlama geliyor ve bunu ne zaman yapmam gerekebilir?

A: Bir PDF belgesinde metni doldurmak ve ana hatlarını çıkarmak, metin karakterlerinin iç kısmına (dolgu) ve metnin etrafındaki kenarlıklara (ana hat) renk uygulamayı içerir. Bu, metnin görsel görünümünü geliştirmek, vurgu oluşturmak veya PDF içindeki belirli içerikleri vurgulamak için kullanılabilir.

#### S: Sağlanan C# kaynak kodu bir PDF dosyasındaki metni doldurmayı ve ana hatlarını çıkarmayı nasıl başarıyor?

 A: Sağlanan kaynak kodu, bir`TextState` gelişmiş metin özelliklerini tanımlamak için nesne, örneğin anahat rengi ve işleme modu. Daha sonra Aspose.PDF.Facades'i kullanarak mevcut bir PDF belgesini yükler, belirtilen dolgu ve kontur özelliklerine sahip metni içeren bir damga oluşturur ve damgayı belgeye ekler.

####  S: Amacı nedir?`TextState` object in the code?

 A:`TextState`nesnesi, metin anahattı rengi (vuruş) ve işleme modu dahil olmak üzere gelişmiş metin özelliklerini tanımlamak için kullanılır. Metnin vuruş ve dolgu açısından nasıl göründüğünü özelleştirmenize olanak tanır.

#### S: Aynı metnin farklı kısımlarına farklı dolgu ve anahat renkleri uygulayabilir miyim?

 A: Evet, farklı kodlar oluşturmak için kodu değiştirebilirsiniz.`TextState` ayrı dolgu ve anahat renklerine sahip nesneler oluşturun ve bunları ayrı metinler kullanarak metnin belirli bölümlerine uygulayın`Stamp` nesneler.

#### S: PDF belgesinde halihazırda bulunan metne dolgu ve anahat renkleri uygulayabilir miyim?

 A: Evet, uygun metin nesnelerini seçip bunları istediğiniz şekilde damgalar olarak ekleyerek PDF belgesinde mevcut metne dolgu ve anahat renkleri uygulamak için benzer ilkeleri kullanabilirsiniz.`TextState` özellikler.

#### S: Dolu ve dış çizgili metnin opaklığını ve karışımını nasıl ayarlayabilirim?

 A: Sağlanan kod, damganın opaklığını ve karıştırma özelliklerini ayarlamanıza olanak tanır.`Opacity` Ve`BlendingSpace`sırasıyla özellikler. İstediğiniz görsel efekti elde etmek için bu değerleri ayarlayabilirsiniz.

#### S: Aynı PDF belgesindeki birden fazla damgaya farklı dolgu ve anahat renkleri nasıl uygulayabilirim?

 A: Birden fazla oluşturabilirsiniz`TextState` farklı dolgu ve anahat renklerine sahip nesneler ve ardından ayrı`Stamp` her metin kümesi için farklı renklere sahip nesneler. Bu damgaları, aynı PDF belgesine kullanarak ekleyin`PdfFileStamp` sınıf.

#### S: Anahatlı ve dolgulu metinlerde Arial fontu dışında başka fontlar kullanabilir miyim?

 A: Evet, yazı tipi adı parametresini değiştirerek yazı tipini değiştirebilirsiniz.`FormattedText` Damgayı oluştururken constructor'ı kullanın. Sisteminizde mevcut olan herhangi bir fontu kullanabilirsiniz.

#### S: Anahatlı ve doldurulmuş metnin dönüş açısını nasıl değiştirebilirim?

 A: Sağlanan kod, pulun dönüş açısını ayarlamanıza olanak tanır.`Rotation` özellik. Metnin istediğiniz dönüş açısını belirtmek için bu özelliği ayarlayabilirsiniz.

#### S: Sayfadaki anahatlı ve doldurulmuş metnin konumunu ve boyutunu nasıl kontrol edebilirim?

 A: Kullanabilirsiniz`SetOrigin` yöntemi`Stamp` Sayfadaki damganın konumunun X ve Y koordinatlarını ayarlamak için nesne. Ayrıca, yazı tipi boyutunu ayarlayabilirsiniz`FormattedText` Metnin boyutunu kontrol eden yapıcı.