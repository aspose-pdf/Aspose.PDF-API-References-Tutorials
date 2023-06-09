---
title: Sayfa Numarası Damgaları
linktitle: Sayfa Numarası Damgaları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesine sayfa numarası damgalarının nasıl ekleneceğini öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine sayfa numarası damgalarının nasıl ekleneceği konusunda size adım adım rehberlik edeceğiz. Mevcut bir PDF belgesini açmak, bir sayfa numarası damgası oluşturmak, özelliklerini ayarlamak ve bunu PDF belgesindeki belirli bir sayfaya eklemek için sağlanan C# kaynak kodunu kullanacağız.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: Mevcut PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut PDF belgesini aç
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Sayfa Numaralandırma Damgasını Oluşturma ve Yapılandırma

Artık PDF belgesi yüklendiğine göre, bir sayfa numaralandırma arabelleği oluşturabilir ve ihtiyaçlarımıza göre yapılandırabiliriz. İşte nasıl:

```csharp
// Bir sayfa numarası arabelleği oluşturun
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Tamponun arka planda olup olmadığını tanımlayın
pageNumberStamp.Background = false;

// Sayfa numaralandırma arabelleğinin biçimi
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Sayfa numaralandırma arabelleğinin alt kenar boşluğu
pageNumberStamp.BottomMargin = 10;

// Sayfa numaralandırma arabelleğinin yatay hizalaması
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Sayfa numaralandırma başlangıç numarası
pageNumberStamp.StartingNumber = 1;

// Sayfa numarası arabelleği metin özelliklerini ayarla
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Yukarıdaki kod, sayfa numarası formatı, alt kenar boşluğu, yatay hizalama, başlangıç numarası ve metin özellikleri gibi özelliklere sahip bir sayfa numarası damgası oluşturur.

## 4. Adım: Belirli bir sayfaya sayfa numarası damgası ekleme

Sayfa numarası damgası yapılandırıldıktan sonra, onu PDF belgesinin belirli bir sayfasına ekleyebiliriz. İşte nasıl:

```csharp
// Sayfa numarası arabelleğini belirli bir sayfaya ekleyin
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Yukarıdaki kod, sayfa numarası damgasını PDF belgesinin ilk sayfasına ekler. Sayfa numarasını gerektiği gibi değiştirebilirsiniz.

## 5. Adım: Değiştirilen PDF belgesini kaydetme

PDF belgesine sayfa numarası damgası eklendikten sonra, değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

"BELGELER DİZİNİNİZ"i, düzenlenmiş PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Sayfa Numarası Damgaları için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Sayfa numarası damgası oluştur
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Damganın arka plan olup olmadığı
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Metin özelliklerini ayarla
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Belirli bir sayfaya damga ekle
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesine sayfa numarası damgalarının nasıl ekleneceğini öğrendiniz. Artık net ve bilgilendirici sayfa numaraları ekleyerek PDF belgelerinizi kişiselleştirebilirsiniz.
