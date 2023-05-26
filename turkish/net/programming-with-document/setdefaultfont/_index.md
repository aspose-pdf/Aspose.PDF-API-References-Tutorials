---
title: Varsayılan Yazı Tipini Ayarla
linktitle: Varsayılan Yazı Tipini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak bir PDF belgesi için varsayılan yazı tipini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 280
url: /tr/net/programming-with-document/setdefaultfont/
---
.NET'te PDF belgeleriyle çalışıyorsanız, PDF'de kullanılan yazı tipinin görüntülendiği veya yazdırıldığı sistemde bulunmadığı sorunlarla karşılaşabilirsiniz. Bu, metnin yanlış görünmesine veya hiç görünmemesine neden olabilir. Aspose.PDF for .NET, belge için varsayılan bir yazı tipi belirlemenize izin vererek bu soruna bir çözüm sunar. Bu örnekte, Aspose.PDF for .NET kullanılarak varsayılan yazı tipinin nasıl ayarlanacağı anlatılmaktadır.

## 1. Adım: Belge dizinine giden yolu ayarlayın

PDF belgemizin bulunduğu dizine giden yolu belirlememiz gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF belgesini yükleyin

 Eksik yazı tiplerine sahip mevcut bir PDF belgesini yükleyerek başlayacağız. Bu örnekte, PDF belgesinin, tarafından belirtilen dizinde bulunduğunu varsayacağız.`dataDir` değişken.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // kod buraya gelecek
}
```

## 3. Adım: Varsayılan yazı tipini ayarlayın

 Ardından, kullanarak PDF belgesi için varsayılan yazı tipini ayarlayacağız.`PdfSaveOptions`sınıf. Bu örnekte, varsayılan yazı tipini "Arial" olarak ayarlayacağız.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## 4. Adım: Güncellenen belgeyi kaydedin

Son olarak, güncellenen belgeyi yeni bir dosyaya kaydedeceğiz. Bu örnekte, güncellenen belgeyi giriş dosyasıyla aynı dizinde bulunan "output_out.pdf" adlı bir dosyaya kaydedeceğiz.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Aspose.PDF for .NET kullanarak Varsayılan Yazı Tipini Ayarlamak için Örnek Kaynak Kodu

```csharp
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Mevcut bir PDF belgesini eksik yazı tipiyle yükleyin
	string documentName = dataDir + "input.pdf";
	string newName = "Arial";
	using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
	using (Document document = new Document(fs))
	{
		PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
		// Varsayılan Yazı Tipi Adını Belirtin
		pdfSaveOptions.DefaultFontName = newName;
		document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
	}
	
```
