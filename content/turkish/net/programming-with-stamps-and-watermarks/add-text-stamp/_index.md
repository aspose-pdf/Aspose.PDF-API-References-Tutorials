---
title: PDF Dosyasına Metin Damgası Ekleme
linktitle: PDF Dosyasına Metin Damgası Ekleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasına kolayca metin damgası eklemeyi öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasına nasıl metin damgası ekleyeceğinizi adım adım anlatacağız. PDF dosyasının belirli bir sayfasına özel metin damgası eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.

## Adım 2: PDF belgesini yükleme

İlk adım mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"BELGELERİNİZ DİZİNİ"ni, PDF belgenizin bulunduğu dizine giden gerçek yolla değiştirdiğinizden emin olun.

## 3. Adım: Metin arabelleğini oluşturma

Artık PDF belgesini yüklediğinize göre eklenecek metin damgasını oluşturabilirsiniz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// Metin arabelleğini oluşturun
TextStamp textStamp = new TextStamp("Example Stamp");
```

Yukarıdaki kod, belirtilen metni içeren yeni bir metin arabelleği oluşturur.

## Adım 4: Metin Damgası Özelliklerini Yapılandırma

Metin damgasını PDF belgesine eklemeden önce damganın arka plan, konum, döndürme, yazı tipi, boyut vb. çeşitli özelliklerini yapılandırabilirsiniz. Bunu şu şekilde yapabilirsiniz:

```csharp
// Metin arabelleği özelliklerini yapılandırma
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

## Adım 5: PDF'ye Metin Damgası Ekleme

Artık metin damgası hazır olduğuna göre onu PDF belgesinin belirli bir sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
//Belirli bir sayfaya metin arabelleği ekleyin
pdfDocument.Pages[1].AddStamp(textStamp);
```

Yukarıdaki kod, metin damgasını PDF belgesinin ilk sayfasına ekler. Gerekirse başka bir sayfa belirtebilirsiniz.

## Adım 6: Çıktı belgesini kaydedin

Metin damgasını ekledikten sonra düzenlenen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Çıktı belgesini kaydet
pdfDocument.Save(dataDir);
```

Yukarıdaki kod, değiştirilen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Metin Damgası Ekleme için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Metin damgası oluştur
TextStamp textStamp = new TextStamp("Sample Stamp");

// Damganın arka planda olup olmayacağını ayarlayın
textStamp.Background = true;

// Başlangıç noktasını ayarla
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Damgayı döndür
textStamp.Rotate = Rotation.on90;

// Metin özelliklerini ayarlama
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

Tebrikler! Aspose.PDF for .NET'i kullanarak nasıl metin damgası ekleyeceğinizi öğrendiniz. Artık PDF belgelerine özel metin damgaları eklemek için bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF dosyasına metin damgası eklemek için SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF dosyasına metin damgası eklemenin amacı nedir?

C: Metin damgası eklemek, özel metni bir PDF belgesinin belirli bir sayfasına yerleştirmenize olanak tanır. Bu özellik, belgenin içeriğini geliştirmek ve ek bağlam sağlamak amacıyla etiketler, yorumlar, filigranlar veya diğer metinsel bilgileri eklemek için kullanışlıdır.

#### S: Metin damgasının yazı tipi, boyutu, rengi ve döndürme gibi görünümünü özelleştirebilir miyim?

 C: Evet, metin damgasının görünümünü tamamen özelleştirebilirsiniz. Sağlanan C# kaynak kodu, C#'ın çeşitli özelliklerinin nasıl ayarlanacağını gösterir.`TextStamp` yazı tipi, yazı tipi boyutu, yazı tipi stili, metin rengi, arka plan rengi ve döndürme dahil olmak üzere nesne.

#### S: Aynı PDF belgesinin farklı sayfalarına birden fazla metin damgası eklemek mümkün müdür?

C: Kesinlikle, aynı PDF belgesinin farklı sayfalarına birden fazla metin damgası ekleyebilirsiniz. Eğitimin sağladığı kod, metin damgasını eklemek için hedef sayfayı belirlemenize olanak tanır ve belge içindeki farklı sayfalar için onu çok yönlü hale getirir.

#### S: Metin damgasının PDF belgesindeki konumunu nasıl belirlerim?

 C: Metin damgasının konumunu değiştirerek özelleştirebilirsiniz.`XIndent` Ve`YIndent` özellikleri`TextStamp` nesne. Bu özellikler damganın sol üst köşesinin koordinatlarını sayfanın kaynağına göre tanımlar.

#### S: Metin damgaları eklemek için bu yöntemi mevcut PDF belgelerine uygulayabilir miyim?

C: Evet, metin damgaları eklemek için bu yöntemi mevcut PDF belgelerine uygulayabilirsiniz. Eğitimde sağlanan kod, mevcut bir PDF belgesinin nasıl yükleneceğini ve belirli bir sayfaya metin damgasının nasıl ekleneceğini gösterir.

#### S: Metin damgasına hem arka plan hem de ön plan renkleri ekleyebilir miyim?

 C: Evet, metin damgasına hem arka plan hem de ön plan renkleri ekleyebilirsiniz. Ayarlayarak`Background` mülkiyet`true` metin damgası için renkli bir arka plan sağlayabilirsiniz. Ek olarak,`TextState.ForegroundColor` Metnin rengini belirtme özelliği.

#### S: Metin damgasının PDF belgesinin temel içeriğini gizlememesini nasıl sağlayabilirim?

 C: Bir metin damgası eklerken, kritik bilgileri engellemediğinden veya belgenin okunabilirliğini olumsuz etkilemediğinden emin olmak için yerleşimine dikkat edin. Ayarlayabilirsiniz`XIndent` Ve`YIndent` metin damgasını uygun şekilde konumlandırmak için özellikler.

#### S: Bu yöntemi metin dışında resim veya logo gibi damgalar eklemek için kullanabilir miyim?

C: Bu özel eğitim metin damgaları eklemeye odaklanıyor ancak Aspose.PDF for .NET'i kullanarak benzer şekilde resim veya logo gibi diğer damga türlerini de ekleyebilirsiniz. Süreç, uygun damga nesnesinin oluşturulmasını ve özelliklerinin yapılandırılmasını içerir.

#### S: Birden fazla PDF belgesine metin damgası ekleme işlemini nasıl otomatikleştirebilirim?

C: Bir belge listesi üzerinde yinelenen ve her birine aynı metin damgalama işlemini uygulayan bir komut dosyası veya program oluşturarak, birden fazla PDF belgesine metin damgası ekleme işlemini otomatikleştirebilirsiniz.