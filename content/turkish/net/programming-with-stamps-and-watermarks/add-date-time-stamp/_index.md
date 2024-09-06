---
title: PDF Dosyasına Tarih Saat Damgası Ekle
linktitle: PDF Dosyasına Tarih Saat Damgası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasına kolayca tarih ve saat damgası eklemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
Bu makalede, .NET için Aspose.PDF kullanarak PDF dosyasına tarih ve saat damgasının nasıl ekleneceğini adım adım anlatacağız. Mevcut bir PDF dosyasına tarih ve saat damgası eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 1: Ortamı kurma

Bir PDF belgesine tarih ve saat damgası ekleyebilmeniz için geliştirme ortamınızı ayarlamanız gerekir. İzlenecek adımlar şunlardır:

1. Favori IDE'nizi (Bütünleşik Geliştirme Ortamı) açın.
2. Yeni bir C# projesi oluşturun.
3. .NET için Aspose.PDF kütüphanesine bir referans eklediğinizden emin olun.

## Adım 2: Aspose.PDF kitaplığını ekleme

Projenizde PDF belgeleriyle çalışabilmeniz için .NET için Aspose.PDF kütüphanesine ihtiyacınız vardır.

## Adım 3: PDF belgesini yükleme

Tarih ve saat damgası eklemenin ilk adımı, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizin bulunduğu dizinin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 4: Tarih ve saat damgasını oluşturma

Artık belgeyi yüklediğinize göre

  PDF, eklemek için tarih ve saat damgası oluşturabilirsiniz. İşte nasıl yapılacağı:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Bir metin arabelleği oluşturun
TextStamp textStamp = new TextStamp(annotationText);
```

Yukarıdaki kod, geçerli tarih ve saati içeren yeni bir metin tamponu oluşturur.

## Adım 5: Damga Özelliklerini Yapılandırma

Damgayı PDF belgesine eklemeden önce, kenar boşluğu, yatay ve dikey hizalama vb. gibi damganın çeşitli özelliklerini yapılandırabilirsiniz. İşte nasıl:

```csharp
// Arabellek özelliklerini ayarla
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Bu özellikleri ihtiyaçlarınıza göre ayarlayabilirsiniz.

## Adım 6: PDF'ye Damga Ekleme

Artık tarih ve saat damgası hazır olduğuna göre, bunu PDF belgesinin belirli bir sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
// Pulunuzu sayfanın pul koleksiyonuna ekleyin
pdfDocument.Pages[1].AddStamp(textStamp);
```

Yukarıdaki kod, damgayı PDF belgesinin ilk sayfasına ekler. Gerekirse başka bir sayfa belirtebilirsiniz.

## Adım 7: Çıktı belgesini kaydedin

Tarih ve saat damgasını ekledikten sonra, değiştirilen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Çıktı belgesini kaydedin
pdfDocument.Save(dataDir);
```

Yukarıdaki kod düzenlenen PDF belgesini belirtilen dizine kaydeder.

### .NET için Aspose.PDF kullanarak Tarih Saat Damgası Ekleme için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Metin damgası oluştur
TextStamp textStamp = new TextStamp(annotationText);

// Damganın özelliklerini ayarla
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

// Çıktı belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak tarih ve saat damgası eklemeyi öğrendiniz. Şimdi bu bilgiyi kendi projelerinize uygulayarak PDF belgelerine tarih ve saat damgaları ekleyebilirsiniz.

### PDF dosyasına tarih saat damgası ekleme hakkında SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine tarih ve saat damgası eklemenin amacı nedir?

A: Bir PDF belgesine tarih ve saat damgası eklemek, belgenin ne zaman değiştirildiğini veya oluşturulduğunu belirterek bilgi değerini artırır. Bu özellik, belge değişikliklerini izlemek ve belge geçmişi için bir referans noktası sağlamak için yararlıdır.

#### S: Tarih ve saat damgasının biçimini belirli gereksinimleri karşılayacak şekilde özelleştirebilir miyim?

 A: Evet, tarih ve saat damgasının biçimini tercihlerinize göre özelleştirebilirsiniz. Sağlanan C# kaynak kodu,`DateTime.Now.ToString()` Belirli bir formatta zaman damgası oluşturma yöntemi. Bu kodu, zaman damgasını gerektiği gibi biçimlendirmek için değiştirebilirsiniz.

#### S: PDF sayfasında belirli bir yere tarih ve saat damgası eklemek mümkün müdür?

 A: Kesinlikle, PDF sayfasındaki tarih ve saat damgasının yerleşimini, özelliklerini değiştirerek ayarlayabilirsiniz.`TextStamp` nesne. Eğitimde sağlanan kod, kenar boşluğu, hizalama ve dikey konumlandırma gibi özelliklerin nasıl ayarlanacağını gösterir.

#### S: Aynı PDF belgesinin farklı sayfalarına birden fazla tarih ve saat damgası ekleyebilir miyim?

 A: Evet, aynı PDF belgesinin farklı sayfalarına birden fazla tarih ve saat damgası ekleyebilirsiniz. Basitçe bir tarih ve saat damgası oluşturma sürecini tekrarlayın.`TextStamp` Her istenilen sayfa için nesne ve özelliklerinin yapılandırılması.

#### S: Tarih ve saat damgası metninin yazı tipini, boyutunu veya rengini nasıl değiştirebilirim?

 A: Tarih ve saat damgası metninin yazı tipini, boyutunu veya rengini değiştirmek için,`DefaultAppearance` oluşturmak için kullanılan nesne`TextStamp`İstediğiniz görünümü elde etmek için yazı tipi adını, boyutunu ve renk değerlerini ayarlayın.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine başka türde açıklamalar veya damgalar eklemek mümkün müdür?

C: Evet, Aspose.PDF for .NET, metin açıklamaları, damgalar, çizgiler, şekiller ve daha fazlası dahil olmak üzere PDF belgelerine ekleyebileceğiniz çok çeşitli açıklama türleri sağlar. Açıklamalarla çalışma hakkında daha fazla ayrıntı için Aspose.PDF belgelerini inceleyebilirsiniz.

#### S: Bir PDF belgesine tarih ve saat damgası eklerken herhangi bir sınırlama veya dikkat edilmesi gereken husus var mıdır?

A: Tarih ve saat damgası eklemek basit olsa da, belgenin düzeni ve mevcut içerik gibi faktörleri göz önünde bulundurun. Damganın yerleşiminin önemli bilgileri gizlemediğinden veya belgenin okunabilirliğini etkilemediğinden emin olun.

#### S: Bu yöntemi kendi projelerime nasıl entegre ederek PDF belgelerine tarih ve saat damgası ekleyebilirim?

A: Bu yöntemi entegre etmek için, verilen adımları izleyin ve kodu projenizin yapısına uyacak şekilde ayarlayın. Kullanışlılıklarını artırmak ve değişikliklerin net bir zaman çizelgesini sağlamak için mevcut PDF belgelerine tarih ve saat damgaları ekleyebilirsiniz.

#### S: Birden fazla PDF belgesine tarih ve saat damgası ekleme sürecini otomatikleştirebilir miyim?

C: Evet, birden fazla PDF belgesine tarih ve saat damgası ekleme sürecini, bir belge listesi üzerinde yineleme yapan ve her birine aynı damgalama işlemini uygulayan bir betik veya program oluşturarak otomatikleştirebilirsiniz.