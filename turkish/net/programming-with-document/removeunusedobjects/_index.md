---
title: Kullanılmayan Nesneleri Kaldır
linktitle: Kullanılmayan Nesneleri Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla, Aspose.PDF for .NET'i PDF belgelerinden kullanılmayan nesneleri kaldırmak için nasıl kullanacağınızı öğrenin.
type: docs
weight: 260
url: /tr/net/programming-with-document/removeunusedobjects/
---
Aspose.PDF for .NET kullanarak PDF belgelerinizdeki kullanılmayan nesneleri kaldırmanın bir yolunu arıyorsanız, doğru yerdesiniz. Bu adım adım kılavuz, bu görevi gerçekleştirmek için sağlanan C# kaynak kodunu nasıl kullanacağınızı gösterecektir.

## 1. Adım: Dizin yolunu ayarlayın

Öncelikle, "BELGE DİZİNİNİZİ" uygun yolla değiştirerek belge dizininizin yolunu ayarlamanız gerekir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF belgesini açın

Ardından, aşağıdaki kodu kullanarak optimize etmek istediğiniz PDF belgesini açmanız gerekir:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 3. Adım: RemoveUnusedObjects seçeneğini ayarlayın

PDF belgenizdeki kullanılmayan nesneleri kaldırmak için RemoveUnusedObjects seçeneğini aşağıdaki gibi "true" olarak ayarlamanız gerekir:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## 4. Adım: OptimizationOptions'ı kullanarak PDF belgesini optimize edin

Şimdi, az önce belirlediğiniz optimizasyon seçenekleriyle OptimizeResources yöntemini kullanarak PDF belgenizi optimize edebilirsiniz:

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 5. Adım: Güncellenen belgeyi kaydedin

Son olarak, güncellenen belgeyi aşağıdaki kodla kaydedebilirsiniz:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

Bu kadar! Aspose.PDF for .NET'i kullanarak kullanılmayan nesneleri PDF belgenizden başarıyla kaldırdınız.

### Aspose.PDF for .NET kullanarak Kullanılmayan Nesneleri Kaldır için örnek kaynak kodu:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// RemoveUsedObject seçeneğini ayarla
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedObjects = true
	};
	// OptimizationOptions kullanarak PDF belgesini optimize edin
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Güncellenen belgeyi kaydet
	pdfDocument.Save(dataDir);

```
