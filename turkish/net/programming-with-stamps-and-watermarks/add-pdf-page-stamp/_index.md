---
title: PDF Sayfa Damgası Ekle
linktitle: PDF Sayfa Damgası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinize kolayca bir PDF sayfa damgası eklemeyi öğrenin.
type: docs
weight: 40
url: /tr/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl PDF sayfa damgası ekleyeceğinizi adım adım anlatacağız. PDF belgesinin belirli bir sayfasına özel bir damga eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

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
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Sayfa arabelleği oluşturma

Artık PDF belgesini yüklediğinize göre, eklenecek sayfa damgasını oluşturabilirsiniz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// Sayfa arabelleğini oluştur
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

Yukarıdaki kod, PDF belgesinin ilk sayfasını kullanarak yeni bir sayfa arabelleği oluşturur.

## 4. Adım: Sayfa Arabelleği Özelliklerini Yapılandırma

Sayfa damgasını PDF belgesine eklemeden önce, damganın arka plan, konum, döndürme vb. gibi çeşitli özelliklerini yapılandırabilirsiniz. Bunu şu şekilde yapabilirsiniz:

```csharp
// Sayfa arabelleği özelliklerini yapılandırma
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

Bu özellikleri ihtiyaçlarınıza göre ayarlayabilirsiniz.

## 5. Adım: Sayfa damgasını PDF'ye ekleme

Artık sayfa damgası hazır olduğuna göre, onu PDF belgesinin belirli bir sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
// Belirli bir sayfaya sayfa arabelleği ekle
pdfDocument.Pages[1].AddStamp(pageStamp);
```

Yukarıdaki kod, sayfa damgasını PDF belgesinin ilk sayfasına ekler. Gerekirse başka bir sayfa belirtebilirsiniz.

## 6. Adım: Çıktı belgesini kaydedin

Sayfa damgasını ekledikten sonra değiştirilen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Add PDFPage Stamp için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

// Sayfa damgası oluştur
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

// Belirli bir sayfaya damga ekle
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF sayfa damgasının nasıl ekleneceğini öğrendiniz. Artık bu bilgiyi kendi projelerinize uygulayarak PDF belgelerinizin belirli sayfalarına özel damgalar ekleyebilirsiniz.
