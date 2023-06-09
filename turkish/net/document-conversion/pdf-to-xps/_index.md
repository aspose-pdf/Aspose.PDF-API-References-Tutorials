---
title: PDF'den XPS'ye dönüştürme
linktitle: PDF'den XPS'ye dönüştürme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'yi XPS'e dönüştürmek için adım adım kılavuz.
type: docs
weight: 220
url: /tr/net/document-conversion/pdf-to-xps/
---

Bu eğitici yazıda, Aspose.PDF for .NET kullanarak bir PDF dosyasını XPS (XML Kağıt Spesifikasyonu) formatına dönüştürme sürecinde size yol göstereceğiz. XPS formatı, belgeleri elektronik olarak temsil etmek için kullanılan XML tabanlı bir dosya formatıdır. Aşağıdaki adımları izleyerek, bir PDF dosyasını XPS formatına dönüştürebileceksiniz.

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

## 2. Adım: XPS kaydetme seçeneklerini somutlaştırın
PDF dosyasını yükledikten sonra, XPS kaydetme seçeneklerini başlatacağız. Aşağıdaki kodu kullanın:

```csharp
// XPS kaydetme seçeneklerini somutlaştırın
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## 3. Adım: Ortaya çıkan XPS dosyasını kaydetme
Şimdi dönüştürülen PDF dosyasını XPS formatında kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// XPS belgesini kaydedin
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Yukarıdaki kod, dönüştürülen PDF dosyasını dosya adıyla XPS formatında kaydeder.`"PDFToXPS_out.xps"`.


### Aspose.PDF for .NET kullanarak PDF to XPS için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini yükle
Document pdfDocument = new Document(dataDir + "input.pdf");

// Örnek XPS Kaydetme seçenekleri
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// XPS belgesini kaydedin
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını XPS formatına dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık bir PDF dosyasını XPS formatına dönüştürebilmelisiniz. Bu özellik, PDF belgelerini XPS biçiminde görüntülemek veya yazdırmak istediğinizde kullanışlıdır.