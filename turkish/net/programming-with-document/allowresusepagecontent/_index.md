---
title: Sayfa İçeriğinin Yeniden Kullanılmasına İzin Ver
linktitle: Sayfa İçeriğinin Yeniden Kullanılmasına İzin Ver
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak "Sayfa İçeriğinin Yeniden Kullanılmasına İzin Ver" özelliğini etkinleştirerek PDF'leri nasıl optimize edeceğinizi öğrenin. Dosya boyutunu azaltın ve performansı artırın.
type: docs
weight: 50
url: /tr/net/programming-with-document/allowresusepagecontent/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak "Sayfa İçeriğinin Yeniden Kullanılmasına İzin Ver" özelliğinin nasıl etkinleştirileceğini açıklayacağız. Bu özellik, sayfa içeriğini yeniden kullanarak, dosya boyutunu küçülterek ve performansı artırarak PDF belgesini optimize eder. Aşağıdaki adım adım kılavuzu izleyin:

## 1. Adım: PDF belgesini yükleyin

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 2. Adım: AllowReusePageContent seçeneğini ayarlayın

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## 3. Adım: PDF belgesini optimize edin

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 4. Adım: Güncellenen belgeyi kaydedin

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 5. Adım: Dosya boyutu küçültmeyi kontrol edin

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Tebrikler! PDF belgenizde sayfa içeriğinin yeniden kullanılmasına başarıyla izin verdiniz.

### Aspose.PDF for .NET kullanarak Sayfa İçeriğinin Yeniden Kullanımına İzin Verme için örnek kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// AllowReusePageContent seçeneğini ayarlayın
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// OptimizationOptions kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);

// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Artık sayfa içeriğinin yeniden kullanılmasına izin vererek PDF belgelerinizi etkili bir şekilde optimize edebilirsiniz.
