---
title: PDF'den PDFA'ya
linktitle: PDF'den PDFA'ya
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'yi PDFA'ya dönüştürmek için adım adım kılavuz.
type: docs
weight: 140
url: /tr/net/document-conversion/pdf-to-pdfa/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını PDF/A formatına dönüştürme sürecinde size yol göstereceğiz. PDF/A formatı, elektronik belgelerin uzun süreli korunmasını garanti eden bir ISO standardıdır. Aşağıdaki adımları izleyerek, PDF dosyalarını PDF/A formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: Kaynak PDF belgesini açma
Bu adımda, Aspose.PDF for .NET kullanarak kaynak PDF dosyasını açacağız. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Kaynak PDF belgesini aç
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: PDF/A biçimine dönüştürme
PDF dosyasını açtıktan sonra PDF/A formatına dönüştürme işlemine geçebiliriz. Aşağıdaki kodu kullanın:

```csharp
// PDF/A uyumlu belgeye dönüştürün
// Dönüştürme işlemi sırasında doğrulama da gerçekleştirilir
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

 Yukarıdaki kod, PDF dosyasını PDF/A-1b formatına dönüştürür ve ayrıca dönüştürme işlemi sırasında doğrulama gerçekleştirir. Herhangi bir hata kayıt altına alınır.`"log.xml"` dosya.

## 3. Adım: Ortaya çıkan PDF/A dosyasını kaydetme
Dönüştürme tamamlandıktan sonra ortaya çıkan PDF/A dosyasını kaydetmemiz gerekiyor. İşte son adım:

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` Çıktı PDF/A dosyasını kaydetmek istediğiniz istediğiniz dizinle.

### Aspose.Words for .NET kullanarak PDF'den HTML'ye dönüştürme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

// PDF/A uyumlu belgeye dönüştürün
// Dönüştürme işlemi sırasında doğrulama da gerçekleştirilir
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını PDF/A formatına dönüştürme sürecini adım adım ele aldık. Yukarıda açıklanan talimatları izleyerek, artık PDF dosyalarını PDF/A formatına dönüştürebilmelisiniz. Bu özellik, elektronik belgelerinizin uzun vadeli uyumluluğunu sağlamak istediğinizde kullanışlıdır.