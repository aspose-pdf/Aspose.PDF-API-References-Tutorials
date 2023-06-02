---
title: PDF'den PDFA3b'ye
linktitle: PDF'den PDFA3b'ye
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'yi PDF/A-3b'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 150
url: /tr/net/document-conversion/pdf-to-pdfa3b/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını PDF/A-3b formatına dönüştürme sürecinde size yol göstereceğiz. PDF/A-3b, dosyaları ve verileri bir PDF belgesine gömmek için bir ISO standardıdır. Aşağıdaki adımları izleyerek PDF dosyalarını PDF/A-3b formatına dönüştürebileceksiniz.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: PDF/A-3b'ye Dönüştürün
PDF dosyasını açtıktan sonra PDF/A-3b formatına dönüştürme işlemine geçebiliriz. Aşağıdaki kodu kullanın:

```csharp
// PDF/A-3b formatına dönüştürün
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

Yukarıdaki kod, PDF dosyasını PDF/A-3b formatına dönüştürür ve tüm dönüştürme hatalarını kaldırır.

## 3. Adım: Ortaya çıkan PDF/A-3b dosyasını kaydetme
Dönüştürme tamamlandıktan sonra ortaya çıkan PDF/A-3b dosyasını kaydetmemiz gerekiyor. İşte son adım:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` Çıktı PDF/A-3b dosyasını kaydetmek istediğiniz istediğiniz dizinle.

### Aspose.Words for .NET kullanarak PDF'den PDFA3b'ye dönüştürme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını PDF/A-3b formatına dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık PDF dosyalarını PDF/A-3b formatına dönüştürebilmelisiniz. Bu özellik, PDF/A-3b standardına uygun bir PDF belgesine ek dosya ve veri gömmek istediğinizde kullanışlıdır.