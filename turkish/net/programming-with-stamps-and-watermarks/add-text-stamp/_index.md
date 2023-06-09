---
title: Metin Damgası Ekle
linktitle: Metin Damgası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinize kolayca nasıl metin damgası ekleyeceğinizi öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl metin damgası ekleyeceğinizi adım adım anlatacağız. PDF belgesinin belirli bir sayfasına özel bir metin damgası eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

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
// Belirli bir sayfaya metin arabelleği ekle
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
