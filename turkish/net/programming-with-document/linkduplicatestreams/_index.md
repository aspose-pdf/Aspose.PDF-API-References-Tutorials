---
title: Yinelenen Akışları Bağlayın
linktitle: Yinelenen Akışları Bağlayın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET Link Duplicate Streams özelliğini kullanarak PDF belgelerinizi optimize etmeyi öğrenin.
type: docs
weight: 230
url: /tr/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF for .NET, PDF dosyalarıyla çalışmak için çeşitli özellikler sağlayan kapsamlı ve güçlü bir kitaplıktır. Temel özelliklerinden biri, PDF dosyalarını optimize etme yeteneğidir. Bu yazıda Aspose.PDF for .NET'in Duplicate Streams Link özelliğinin PDF dosyalarını optimize etmek için nasıl kullanılacağını açıklayacağız. Adım adım talimatlar sağlayacağız ve geliştiricilerin takip etmesini kolaylaştırmak için tam bir kaynak kodu örneği ekleyeceğiz.

## 1. Adım: PDF Belgesini Açma

Aspose.PDF for .NET kullanarak PDF belgesini açmak için şu adımları izleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

Yukarıdaki kodda, "BELGE DİZİNİNİZİ" proje dizininizin yolu ile değiştirin.

## 2. Adım: LinkDuplicateStreams Seçeneğini Ayarlama

LinkDuplicateStreams seçeneğini ayarlamak için şu adımları izleyin:

```csharp
// LinkDuplcateStreams seçeneğini ayarlayın
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

Yukarıdaki kodda, yeni bir OptimizationOptions örneği oluşturduk ve LinkDuplicateStreams seçeneğini true olarak ayarladık.

## 3. Adım: PDF Belgesini Optimize Etme

PDF belgesini optimize etmek için şu adımları izleyin:

```csharp
// OptimizationOptions kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
```

Yukarıdaki kodda, daha önce oluşturduğumuz OptimizationOptions'ı kullanarak PDF belgesini optimize etmek için pdfDocument nesnesinin OptimizeResources yöntemini kullandık.

## 4. Adım: Güncellenen Belgeyi Kaydetme

Güncellenen belgeyi kaydetmek için şu adımları izleyin:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
```

Yukarıdaki kodda, güncellenen belgeyi proje dizininde "OptimizeDocument_out.pdf" adlı yeni bir dosyaya kaydetmek için pdfDocument nesnesinin Save yöntemini kullandık.

### Aspose.PDF for .NET kullanarak Yinelenen Akışları Bağlamak için Örnek Kaynak Kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// LinkDuplcateStreams seçeneğini ayarlayın
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// OptimizationOptions kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
```
