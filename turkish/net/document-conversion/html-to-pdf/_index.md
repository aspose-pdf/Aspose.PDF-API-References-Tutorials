---
title: HTML'den PDF'ye
linktitle: HTML'den PDF'ye
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak HTML'yi PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 50
url: /tr/net/document-conversion/html-to-pdf/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir HTML dosyasını PDF'ye dönüştürme sürecinde size yol göstereceğiz. HTML (HyperText Markup Language), web içeriğini yapılandırmak ve sunmak için kullanılan bir biçimlendirme dilidir. Aşağıdaki adımları izleyerek HTML dosyalarını PDF formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: HTML dosyasını yükleme
Bu adımda, Aspose.PDF for .NET kullanarak HTML dosyasını yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

HtmlLoadOptions options = new HtmlLoadOptions();
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` HTML dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: HTML yükleme seçenekleri
Artık HTML dosyasını yüklediğimize göre, belirli yükleme seçeneklerini belirtebiliriz. Aşağıdaki kodu kullanın:

```csharp
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);
```

Yukarıdaki kod, Aspose.PDF'ye görüntüler gibi harici kaynaklar için özel bir yükleme stratejisi kullanmasını söyler. Bu politikayı ihtiyaçlarınıza göre özelleştirebilirsiniz.

## 3. Adım: HTML'den PDF'e dönüştürme
HTML dosyasını yükleyip yükleme seçeneklerini belirttikten sonra PDF'e dönüştürme işlemine geçebiliriz. Aşağıdaki kodu kullanın:

```csharp
pdfDocument.Save("HTMLToPDF_out.pdf");
```

### Aspose.Words for .NET kullanarak HTML'den PDF'e dönüştürme için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	HtmlLoadOptions options = new HtmlLoadOptions();
	options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

	Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
	pdfDocument.Save("HTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm
Bu eğitimde, süreci adım adım ele aldık. Aspose.PDF for .NET kullanarak bir HTML dosyasını PDF'ye dönüştürme adımı. Yukarıda özetlenen talimatları izleyerek, artık HTML dosyalarını PDF formatına dönüştürebilmelisiniz. Bu özellik, HTML içeriğinden PDF belgeleri oluşturmanız gerektiğinde yararlı olabilir.

