---
title: PDF Dosyasına Metin Damgası Ekleyin
linktitle: PDF Dosyasına Metin Damgası Ekleyin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasına kolayca nasıl metin damgası ekleyeceğinizi öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasına nasıl metin damgası ekleyeceğinizi adım adım anlatacağız. PDF dosyasının belirli bir sayfasına özel bir metin damgası eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi aç
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Metin arabelleği oluşturma

Artık PDF belgesini yüklediğinize göre, eklenecek metin damgasını oluşturabilirsiniz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// Metin arabelleğini oluştur
TextStamp textStamp = new TextStamp("Example Stamp");
```

Yukarıdaki kod, belirtilen metni içeren yeni bir metin arabelleği oluşturur.

## Adım 4: Metin Damgası Özelliklerini Yapılandırma

Metin damgasını PDF belgesine eklemeden önce, damganın arka plan, konum, döndürme, yazı tipi, boyut vb. gibi çeşitli özelliklerini yapılandırabilirsiniz. Bunu şu şekilde yapabilirsiniz:

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

## Adım 5: PDF'ye Metin Damgası Ekleyin

Artık metin damgası hazır olduğuna göre, onu PDF belgesinin belirli bir sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
//Belirli bir sayfaya metin arabelleği ekle
pdfDocument.Pages[1].AddStamp(textStamp);
```

Yukarıdaki kod, metin damgasını PDF belgesinin ilk sayfasına ekler. Gerekirse başka bir sayfa belirtebilirsiniz.

## 6. Adım: Çıktı belgesini kaydedin

Metin damgasını ekledikten sonra düzenlenen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
```

Yukarıdaki kod, değiştirilen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Add Text Stamp için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Metin damgası oluştur
TextStamp textStamp = new TextStamp("Sample Stamp");

// Damganın arka plan olup olmadığını ayarlayın
textStamp.Background = true;

// Menşei ayarla
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Damgayı döndür
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

// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak metin damgası eklemeyi öğrendiniz. Artık PDF belgelerine özel metin damgaları eklemek için bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF dosyasına metin damgası eklemek için SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF dosyasına metin damgası eklemenin amacı nedir?

A: Bir metin damgası eklemek, bir PDF belgesinin belirli bir sayfasına özel metin yerleştirmenize olanak tanır. Bu özellik, belgenin içeriğini geliştirmek ve ek bağlam sağlamak için etiketler, yorumlar, filigranlar veya başka herhangi bir metin bilgisi eklemek için kullanışlıdır.

#### S: Metin damgasının yazı tipi, boyutu, rengi ve dönüşü gibi görünümünü özelleştirebilir miyim?

 C: Evet, metin damgasının görünümünü tamamen özelleştirebilirsiniz. Sağlanan C# kaynak kodu, çeşitli özelliklerin nasıl ayarlanacağını gösterir.`TextStamp` yazı tipi, yazı tipi boyutu, yazı tipi stili, metin rengi, arka plan rengi ve döndürme dahil olmak üzere nesne.

#### S: Aynı PDF belgesinin farklı sayfalarına birden fazla metin damgası eklemek mümkün müdür?

C: Kesinlikle, aynı PDF belgesinin farklı sayfalarına birden fazla metin damgası ekleyebilirsiniz. Öğreticinin sağladığı kod, metin damgasını eklemek için hedef sayfayı belirtmenize izin vererek, onu belgedeki farklı sayfalar için çok yönlü hale getirir.

#### S: PDF belgesindeki metin damgasının konumunu nasıl belirleyebilirim?

 A: Metin damgasının konumunu değiştirerek özelleştirebilirsiniz.`XIndent` Ve`YIndent` özellikleri`TextStamp` nesne. Bu özellikler, sayfanın kaynağına göre damganın sol üst köşesinin koordinatlarını tanımlar.

#### S: Metin damgası eklemek için bu yöntemi mevcut PDF belgelerine uygulayabilir miyim?

C: Evet, metin damgaları eklemek için bu yöntemi mevcut PDF belgelerine uygulayabilirsiniz. Öğreticinin sağladığı kod, mevcut bir PDF belgesinin nasıl yükleneceğini ve belirli bir sayfaya metin damgası ekleneceğini gösterir.

#### S: Metin damgasına hem arka plan hem de ön plan renkleri ekleyebilir miyim?

 C: Evet, metin damgasına hem arka plan hem de ön plan renkleri ekleyebilirsiniz. ayarlayarak`Background` mülkiyet`true` , metin damgası için renkli bir arka plan sağlayabilirsiniz. Ek olarak,`TextState.ForegroundColor` Metnin kendisinin rengini belirtmek için özellik.

#### S: Metin damgasının PDF belgesinin temel içeriğini gizlememesini nasıl sağlayabilirim?

 C: Bir metin damgası eklerken, kritik bilgileri engellemediğinden veya belgenin okunabilirliğini olumsuz etkilemediğinden emin olmak için yerleşimine dikkat edin. ayarlayabilirsiniz`XIndent` Ve`YIndent` Metin damgasını uygun şekilde konumlandırmak için özellikler.

#### S: Bu yöntemi, resim veya logo gibi metin dışında damgalar eklemek için kullanabilir miyim?

C: Bu özel öğretici, metin damgaları eklemeye odaklanır, ancak benzer şekilde, Aspose.PDF for .NET'i kullanarak resimler veya logolar gibi başka türde damgalar da ekleyebilirsiniz. İşlem, uygun damga nesnesinin oluşturulmasını ve özelliklerinin yapılandırılmasını içerir.

#### S: Birden çok PDF belgesine metin damgası ekleme işlemini nasıl otomatik hale getirebilirim?

Y: Bir belge listesinde yinelenen ve her birine aynı metin damgalama işlemini uygulayan bir komut dosyası veya program oluşturarak birden çok PDF belgesine metin damgası ekleme işlemini otomatikleştirebilirsiniz.