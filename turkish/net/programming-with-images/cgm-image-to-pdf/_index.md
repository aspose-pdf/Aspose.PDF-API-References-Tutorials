---
title: CGM Görüntüsünü PDF'ye Dönüştürme
linktitle: CGM Görüntüsünü PDF'ye Dönüştürme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile CGM görüntüsünü kolayca PDF'ye dönüştürün.
type: docs
weight: 40
url: /tr/net/programming-with-images/cgm-image-to-pdf/
---

Bu adım adım kılavuz, Aspose.PDF for .NET kullanılarak bir CGM görüntüsünün PDF'ye nasıl dönüştürüleceğini açıklar. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` CGM dosyanızın bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Giriş ve çıkış dosyasını tanımlayın

 CGM giriş dosyası adını ve PDF çıktı dosyası adını ayarlayın. Yer değiştirmek`"corvette.cgm"` CGM dosyanızın adıyla ve güncelleyerek`dataDir`istenen çıktı dizini ve PDF dosya adı ile.

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## 3. Adım: CGM görüntüsünü PDF'ye dönüştürün

 Kullan`Produce` yöntemi`PdfProducer` kullanarak CGM dosyasını PDF biçimine dönüştürmek için`ImportFormat.Cgm`. CGM girdi dosyasını ve PDF çıktı dosyasını belirtin.

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### Aspose.PDF for .NET kullanarak CGMImage'dan PDF'e dönüştürme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
// CGM'yi PDF formatında kaydedin
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir CGM dosyasını başarıyla PDF'e dönüştürdünüz. Oluşturulan PDF dosyasını artık projelerinizde veya uygulamalarınızda kullanabilirsiniz.