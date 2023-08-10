---
title: PDF Dosyasına Tarih Saat Damgası Ekleyin
linktitle: PDF Dosyasına Tarih Saat Damgası Ekleyin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasına nasıl kolayca tarih ve saat damgası ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
Bu yazıda, Aspose.PDF for .NET kullanarak PDF dosyasına nasıl tarih ve saat damgası ekleyeceğinizi adım adım anlatacağız. Mevcut bir PDF dosyasına tarih ve saat damgası eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Gereksinimler

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 1. Adım: Ortamı ayarlama

Bir PDF belgesine tarih ve saat damgası ekleyebilmeniz için önce geliştirme ortamınızı kurmanız gerekir. İzlenecek adımlar şunlardır:

1. Favori IDE'nizi (Entegre Geliştirme Ortamı) açın.
2. Yeni bir C# projesi oluşturun.
3. .NET için Aspose.PDF kitaplığına bir referans eklediğinizden emin olun.

## Adım 2: Aspose.PDF kitaplığının eklenmesi

.NET için Aspose.PDF kitaplığı, projenizde PDF belgeleriyle çalışmak için gereklidir.

## 3. Adım: PDF belgesini yükleme

Tarih ve saat damgası eklemenin ilk adımı, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi aç
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 4. Adım: Tarih ve saat damgasının oluşturulması

Belgeyi yüklediğinize göre

  PDF, eklemek için tarih ve saat damgası oluşturabilirsiniz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Bir metin arabelleği oluşturun
TextStamp textStamp = new TextStamp(annotationText);
```

Yukarıdaki kod, geçerli tarih ve saati içeren yeni bir metin arabelleği oluşturur.

## Adım 5: Damga Özelliklerini Yapılandırma

Damgayı PDF belgesine eklemeden önce, damganın kenar boşluğu, yatay ve dikey hizalama gibi çeşitli özelliklerini yapılandırabilirsiniz. Bunu şu şekilde yapabilirsiniz:

```csharp
// arabellek özelliklerini ayarla
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Bu özellikleri ihtiyaçlarınıza göre ayarlayabilirsiniz.

## 6. Adım: PDF'ye Damga Ekleyin

Artık tarih ve saat damgası hazır olduğuna göre, bunu PDF belgesinin belirli bir sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
// Damgayı sayfanın pul koleksiyonuna ekleyin
pdfDocument.Pages[1].AddStamp(textStamp);
```

Yukarıdaki kod, damgayı PDF belgesinin ilk sayfasına ekler. Gerekirse başka bir sayfa belirtebilirsiniz.

## 7. Adım: Çıktı belgesini kaydedin

Tarih ve saat damgasını ekledikten sonra değiştirilen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Add Date Time Stamp için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Metin damgası oluştur
TextStamp textStamp = new TextStamp(annotationText);

// Damganın özelliklerini ayarlama
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Pul koleksiyonuna pul ekleme
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak nasıl tarih ve saat damgası ekleyeceğinizi öğrendiniz. Artık PDF belgelerine tarih ve saat damgaları eklemek için bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF dosyasına tarih ve saat damgası eklemek için SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine tarih ve saat damgası eklemenin amacı nedir?

Y: Bir PDF belgesine tarih ve saat damgası eklemek, belgenin ne zaman değiştirildiğini veya oluşturulduğunu belirterek bilgi değerini artırır. Bu özellik, belge değişikliklerini izlemek ve belge geçmişi için bir referans noktası sağlamak için kullanışlıdır.

#### S: Belirli gereksinimleri karşılamak için tarih ve saat damgasının biçimini özelleştirebilir miyim?

 C: Evet, tarih ve saat damgasının biçimini tercihlerinize göre özelleştirebilirsiniz. Sağlanan C# kaynak kodu,`DateTime.Now.ToString()` zaman damgasını belirli bir biçimde oluşturma yöntemi. Zaman damgasını gerektiği gibi biçimlendirmek için bu kodu değiştirebilirsiniz.

#### S: PDF sayfasındaki belirli bir konuma tarih ve saat damgası eklemek mümkün müdür?

 C: Kesinlikle, PDF sayfasındaki tarih ve saat damgasının yerleşimini ayarlayabilirsiniz.`TextStamp` nesne. Öğreticide sağlanan kod, kenar boşluğu, hizalama ve dikey konumlandırma gibi özelliklerin nasıl ayarlanacağını gösterir.

#### S: Aynı PDF belgesinin farklı sayfalarına birden çok tarih ve saat damgası ekleyebilir miyim?

 C: Evet, aynı PDF belgesinin farklı sayfalarına birden çok tarih ve saat damgası ekleyebilirsiniz. oluşturma işlemini tekrarlamanız yeterlidir.`TextStamp` nesne ve istenen her sayfa için özelliklerini yapılandırma.

#### S: Tarih ve zaman damgası metninin yazı tipini, boyutunu veya rengini nasıl değiştirebilirim?

 C: Tarih ve zaman damgası metninin yazı tipini, boyutunu veya rengini değiştirmek için, damganın özelliklerini özelleştirebilirsiniz.`DefaultAppearance` oluşturmak için kullanılan nesne`TextStamp`. İstenen görünümü elde etmek için yazı tipi adını, boyutunu ve renk değerlerini ayarlayın.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine başka türden notlar veya damgalar eklemek mümkün müdür?

C: Evet, Aspose.PDF for .NET, PDF belgelerine ekleyebileceğiniz metin açıklamaları, damgalar, çizgiler, şekiller ve daha fazlasını içeren çok çeşitli açıklama türleri sağlar. Ek açıklamalarla çalışma hakkında daha fazla ayrıntı için Aspose.PDF belgelerini inceleyebilirsiniz.

#### S: Bir PDF belgesine tarih ve saat damgası eklerken herhangi bir sınırlama veya dikkat edilmesi gereken nokta var mı?

C: Tarih ve saat damgası eklemek kolay olsa da, belgenin düzeni ve mevcut içerik gibi faktörleri göz önünde bulundurun. Damganın yerleşiminin önemli bilgileri gizlemediğinden veya belgenin okunabilirliğini etkilemediğinden emin olun.

#### S: PDF belgelerine tarih ve saat damgaları eklemek için bu yöntemi kendi projelerime nasıl entegre edebilirim?

C: Bu yöntemi entegre etmek için verilen adımları izleyin ve kodu projenizin yapısına uyacak şekilde ayarlayın. Kullanışlılıklarını artırmak ve değişikliklerin net bir zaman çizelgesini sağlamak için mevcut PDF belgelerine tarih ve saat damgaları ekleyebilirsiniz.

#### S: Birden çok PDF belgesine tarih ve saat damgası ekleme sürecini otomatikleştirebilir miyim?

Y: Evet, bir belge listesi içinde yinelenen ve her birine aynı damgalama işlemini uygulayan bir komut dosyası veya program oluşturarak birden çok PDF belgesine tarih ve saat damgası ekleme işlemini otomatikleştirebilirsiniz.