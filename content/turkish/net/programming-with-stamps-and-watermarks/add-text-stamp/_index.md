---
title: PDF Dosyasına Metin Damgası Ekle
linktitle: PDF Dosyasına Metin Damgası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasına nasıl kolayca metin damgası ekleyeceğinizi öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasına nasıl metin damgası ekleyeceğinizi adım adım göstereceğiz. Sağlanan C# kaynak kodunu kullanarak PDF dosyasının belirli bir sayfasına özel bir metin damgası eklemeyi göstereceğiz.

## Adım 1: Ortamı kurma

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 2: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizin bulunduğu dizinin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 3: Metin tamponunu oluşturma

Artık PDF belgenizi yüklediğinize göre, eklemek için metin damgasını oluşturabilirsiniz. İşte nasıl yapacağınız:

```csharp
// Metin tamponunu oluştur
TextStamp textStamp = new TextStamp("Example Stamp");
```

Yukarıdaki kod belirtilen metni içeren yeni bir metin tamponu oluşturur.

## Adım 4: Metin Damgası Özelliklerini Yapılandırma

PDF belgesine metin damgasını eklemeden önce damganın arka plan, konum, dönüş, yazı tipi, boyut vb. gibi çeşitli özelliklerini yapılandırabilirsiniz. İşte nasıl:

```csharp
// Metin arabelleği özelliklerini yapılandırın
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Bu özellikleri ihtiyaçlarınıza göre ayarlayabilirsiniz.

## Adım 5: PDF'e Metin Damgası Ekleme

Artık metin damgası hazır olduğuna göre, onu PDF belgesinin belirli bir sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
//Belirli bir sayfaya metin arabelleği ekle
pdfDocument.Pages[1].AddStamp(textStamp);
```

Yukarıdaki kod, PDF belgesinin ilk sayfasına metin damgası ekler. Gerekirse başka bir sayfa belirtebilirsiniz.

## Adım 6: Çıktı belgesini kaydedin

Metin damgasını ekledikten sonra, düzenlenen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Çıktı belgesini kaydedin
pdfDocument.Save(dataDir);
```

Yukarıdaki kod, değiştirilen PDF belgesini belirtilen dizine kaydeder.

### .NET için Aspose.PDF kullanarak Metin Damgası Ekleme için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Metin damgası oluştur
TextStamp textStamp = new TextStamp("Sample Stamp");

// Damganın arka plan olup olmadığını ayarlayın
textStamp.Background = true;

// Kökeni ayarla
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Pul döndür
textStamp.Rotate = Rotation.on90;

// Metin özelliklerini ayarla
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Belirli bir sayfaya damga ekle
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Çıktı belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak metin damgası eklemeyi öğrendiniz. Şimdi bu bilgiyi kendi projelerinize uygulayarak PDF belgelerine özel metin damgaları ekleyebilirsiniz.

### PDF dosyasına metin damgası eklemeyle ilgili SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF dosyasına metin damgası eklemenin amacı nedir?

A: Metin damgası eklemek, PDF belgesinin belirli bir sayfasına özel metin yerleştirmenize olanak tanır. Bu özellik, belgenin içeriğini geliştirmek ve ek bağlam sağlamak için etiketler, yorumlar, filigranlar veya başka herhangi bir metinsel bilgi eklemek için kullanışlıdır.

#### S: Metin damgasının yazı tipi, boyutu, rengi ve dönüşü gibi görünümünü özelleştirebilir miyim?

 A: Evet, metin damgasının görünümünü tamamen özelleştirebilirsiniz. Sağlanan C# kaynak kodu, çeşitli özelliklerin nasıl ayarlanacağını gösterir`TextStamp` yazı tipi, yazı tipi boyutu, yazı tipi stili, metin rengi, arka plan rengi ve dönüş dahil olmak üzere nesne.

#### S: Aynı PDF belgesinin farklı sayfalarına birden fazla metin damgası eklemek mümkün müdür?

A: Kesinlikle, aynı PDF belgesinin farklı sayfalarına birden fazla metin damgası ekleyebilirsiniz. Eğitimin sağladığı kod, metin damgasını eklemek için hedef sayfayı belirtmenize olanak tanır ve bu da belgedeki farklı sayfalar için çok yönlü hale getirir.

#### S: PDF belgesindeki metin damgasının konumunu nasıl belirlerim?

 A: Metin damgasının konumunu,`XIndent` Ve`YIndent` özellikleri`TextStamp` nesne. Bu özellikler, pulun sol üst köşesinin sayfanın kökenine göre koordinatlarını tanımlar.

#### S: Bu yöntemi mevcut PDF belgelerine metin damgaları eklemek için uygulayabilir miyim?

A: Evet, metin damgaları eklemek için bu yöntemi mevcut PDF belgelerine uygulayabilirsiniz. Eğitimde sağlanan kod, mevcut bir PDF belgesinin nasıl yükleneceğini ve belirli bir sayfaya metin damgası nasıl ekleneceğini gösterir.

#### S: Metin damgasına hem arka plan hem de ön plan renklerini ekleyebilir miyim?

 A: Evet, metin damgasına hem arka plan hem de ön plan renkleri ekleyebilirsiniz.`Background` mülk`true` , metin damgası için renkli bir arka plan sağlayabilirsiniz. Ek olarak,`TextState.ForegroundColor` Metnin rengini belirtmek için kullanılan özellik.

#### S: Metin damgasının PDF belgesinin altta yatan içeriğini gizlemediğinden nasıl emin olabilirim?

A: Bir metin damgası eklerken, kritik bilgileri engellememesini veya belgenin okunabilirliğini olumsuz etkilememesini sağlamak için yerleşimine dikkat edin.`XIndent` Ve`YIndent` Metin damgasını uygun şekilde konumlandırmak için özellikler.

#### S: Bu yöntemi metin dışında resim veya logo gibi pullar eklemek için kullanabilir miyim?

A: Bu özel eğitim metin damgaları eklemeye odaklanır, ancak benzer şekilde Aspose.PDF for .NET kullanarak resim veya logo gibi diğer damga türlerini de ekleyebilirsiniz. İşlem, uygun damga nesnesini oluşturmayı ve özelliklerini yapılandırmayı içerir.

#### S: Birden fazla PDF belgesine metin damgası ekleme sürecini nasıl otomatikleştirebilirim?

A: Birden fazla PDF belgesine metin damgası ekleme sürecini, bir belge listesi üzerinde yineleme yapan ve her birine aynı metin damgalama işlemini uygulayan bir betik veya program oluşturarak otomatikleştirebilirsiniz.