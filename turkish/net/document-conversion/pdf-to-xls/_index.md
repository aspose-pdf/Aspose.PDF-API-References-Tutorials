---
title: PDF'yi XLS'ye dönüştürme
linktitle: PDF'yi XLS'ye dönüştürme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'yi XLS'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 200
url: /tr/net/document-conversion/pdf-to-xls/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını XLS (Microsoft Excel) formatına dönüştürme sürecinde size yol göstereceğiz. Aşağıdaki adımları izleyerek, bir PDF dosyasını XLS formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: PDF belgesini yükleme
Bu adımda, Aspose.PDF for .NET kullanarak kaynak PDF dosyasını yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini yükleyin
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: Excel yedekleme seçeneklerini somutlaştırın
PDF dosyasını yükledikten sonra, Excel kaydetme seçeneklerini başlatacağız. Aşağıdaki kodu kullanın:

```csharp
// Bir ExcelSaveOptions nesnesinin örneğini oluşturun
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## 3. Adım: Ortaya çıkan XLS dosyasını kaydetme
Şimdi dönüştürülen PDF dosyasını XLS formatında kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Çıktıyı XLS biçiminde kaydedin
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 Yukarıdaki kod, dönüştürülen PDF dosyasını dosya adıyla XLS formatında kaydeder.`"PDFToXLS_out.xls"`.

### Aspose.PDF for .NET kullanarak PDF to XLS için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini yükle
Document pdfDocument = new Document(dataDir + "input.pdf");

// ExcelSave Seçeneği nesnesini örnekleyin
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Çıktıyı XLS biçiminde kaydedin
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını XLS formatına dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık bir PDF dosyasını XLS formatına dönüştürebilmelisiniz. Bu özellik, bir PDF dosyasından tablo verilerini ayıklamak ve Microsoft Excel'de kullanmak istediğinizde kullanışlıdır.