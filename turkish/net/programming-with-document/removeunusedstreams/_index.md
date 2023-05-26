---
title: Kullanılmayan Akışları Kaldır
linktitle: Kullanılmayan Akışları Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak kullanılmayan akışları PDF dosyalarından nasıl kaldıracağınızı öğrenin. Adım adım kılavuzumuz.
type: docs
weight: 270
url: /tr/net/programming-with-document/removeunusedstreams/
---
Bu örnekte, Aspose.PDF for .NET kullanılarak kullanılmayan akışların PDF belgelerinden nasıl kaldırılacağını tartışacağız. Açıklamalı tam kaynak kodu da dahil olmak üzere, bunun nasıl yapılacağına dair adım adım bir kılavuz sağlayacağız.

## Adım 1: Belgeler dizinine giden yol

Kodun ilk satırı, PDF belgenizin bulunduğu dizinin yolunu belirler. "BELGE DİZİNİNİZİ" gerçek dizin yolu ile değiştirdiğinizden emin olun.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi açın

Bir sonraki kod satırı, Aspose.PDF for .NET kitaplığını kullanarak PDF belgesini açar.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 3. Adım: RemoveUnusedStreams seçeneğini ayarlayın

Bir sonraki adım, RemoveUnusedStreams seçeneğini true olarak ayarlamaktır. Bu, kullanılmayan akışları PDF belgesinden kaldıracaktır.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## 4. Adım: OptimizationOptions'ı kullanarak PDF belgesini optimize edin

Artık optimizasyon seçeneklerini ayarladığımıza göre, aşağıdaki kod satırını kullanarak PDF belgesini optimize edebiliriz.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 5. Adım: Güncellenen belgeyi kaydedin

Son olarak, Document sınıfının Save yöntemini kullanarak güncellenen belgeyi kaydedebiliriz.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Kullanılmayan Akışları Kaldırmak için örnek kaynak kodu

Aspose.PDF for .NET kullanarak kullanılmayan akışları kaldırmak için örnek kaynak kodu aşağıdadır.

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// RemoveUsedStreams seçeneğini ayarlayın
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedStreams = true
	};
	// OptimizationOptions kullanarak PDF belgesini optimize edin
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Güncellenen belgeyi kaydet
	pdfDocument.Save(dataDir);

```
