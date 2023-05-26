---
title: Belgeleri Küçült
linktitle: Belgeleri Küçült
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET'i kullanarak PDF belgelerini küçültmeyi öğrenin.
type: docs
weight: 350
url: /tr/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF for .NET, geliştiricilerin C# kullanarak PDF belgeleri oluşturmasını, değiştirmesini ve optimize etmesini sağlayan güçlü bir kitaplıktır. Bu eğitimde, bir PDF belgesini küçültmek için Aspose.PDF'nin nasıl kullanılacağına dair bir örnek üzerinden ilerleyeceğiz.

## 1. Adım: PDF Belgesini Yükleme

 Bir PDF belgesini küçültmek için önce onu Aspose.PDF kullanarak C# uygulamamıza yüklememiz gerekiyor. Aşağıdaki kodda, PDF belgemizin yolunu belirtiyor ve yeni bir örnek oluşturuyoruz.`Document` sınıf.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## 2. Adım: PDF Belgesini Küçültme

 PDF belgesini yükledikten sonra,`OptimizeResources` yöntemi`Document`Belgeyi en iyi duruma getirmek ve boyutunu potansiyel olarak küçültmek için sınıf. Bazı PDF belgeleri zaten yüksek düzeyde optimize edilmiş olabileceğinden, bu yöntemin belge küçültmeyi garanti edemeyeceğini unutmayın.

```csharp
// PDF belgesini optimize edin. Ancak, bu yöntemin belge küçültmeyi garanti edemeyeceğini unutmayın.
pdfDocument.OptimizeResources();
```

## 3. Adım: Güncellenmiş PDF Belgesini Kaydetme

 PDF belgesini optimize ettikten sonra, güncellenmiş sürümü kullanarak yeni bir dosyaya kaydedebiliriz.`Save` yöntemi`Document` sınıf. Aşağıdaki kodda çıktı dosyasının yolunu ve dosya adını belirtiyoruz.

```csharp
// Çıktı dosyası yolunu belirtin
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(outputFilePath);
```

### Aspose.PDF for .NET kullanan Belgeleri Küçültmek için Örnek Kaynak Kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
	// PDF belgesini optimize edin. Ancak, bu yöntemin belge küçültmeyi garanti edemeyeceğini unutmayın.
	pdfDocument.OptimizeResources();
	dataDir = dataDir + "ShrinkDocument_out.pdf";
	// Güncellenen belgeyi kaydet
	pdfDocument.Save(dataDir);
	
```
