---
title: SVG'den PDF'ye
linktitle: SVG'den PDF'ye
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak kolay ve hızlı SVG'den PDF'e dönüştürme.
type: docs
weight: 280
url: /tr/net/document-conversion/svg-to-pdf/
---

Bu eğitim, Aspose.PDF for .NET kullanarak bir SVG dosyasını PDF dosyasına dönüştürme adımlarında size yol gösterecektir. Aspose.PDF, içerik kalitesini ve düzenini korurken SVG dosyalarını PDF'ye dönüştürmek için basit ve etkili bir çözüm sunar. Bu dönüşümü gerçekleştirmek için aşağıdaki adımları izleyin.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: SVG dosyasını yükleme
 İlk adım, SVG dosyasını bir`Document`SVG yükleme seçeneğini kullanarak nesne (`SvgLoadOptions`). Aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// SVG yükleme seçeneğini kullanarak LoadOption nesnesini oluşturun
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Belge nesnesi oluştur
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` SVG dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: PDF'ye Dönüştürün
 İkinci adım, SVG belgesini kullanarak bir PDF belgesine dönüştürmektir.`Save` yöntemi`Document` nesne. Aşağıdaki kodu kullanın:

```csharp
// Ortaya çıkan PDF belgesini kaydedin
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Ortaya çıkan PDF dosyası için istenen yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.PDF for .NET kullanarak SVG'den PDF'e dönüştürme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// SVG yükleme seçeneğini kullanarak LoadOption nesnesini oluşturun
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Belge nesnesi oluştur
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Ortaya çıkan PDF belgesini kaydedin
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir SVG dosyasını PDF dosyasına dönüştürmeyi öğrendik. Yukarıda verilen adımları takip ederek bu dönüşümü kolaylıkla gerçekleştirebilirsiniz. SVG dosyalarınızı PDF'ye dönüştürmek için bu yöntemi kullanın ve Aspose.PDF'nin esnekliğinin ve kalitesinin keyfini çıkarın.