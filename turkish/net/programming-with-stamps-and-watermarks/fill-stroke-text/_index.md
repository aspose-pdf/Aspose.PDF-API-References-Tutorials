---
title: Konturlu Metni Doldur
linktitle: Konturlu Metni Doldur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki metni kolayca nasıl dolduracağınızı ve ana hatları çizeceğinizi öğrenin.
type: docs
weight: 90
url: /tr/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki metni nasıl dolduracağınızı ve ana hatları çizeceğinizi adım adım göstereceğiz. PDF belgesindeki metne dolgu ve anahat renkleri uygulamak için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

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

//Bir giriş PDF belgesi yükleyin
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
