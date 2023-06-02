---
title: PDF UA Standardını Doğrulayın
linktitle: PDF UA Standardını Doğrulayın
second_title: Aspose.PDF for .NET API Referansı
description: C# kodunu kullanarak PDF/UA standardını doğrulamak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin. Adım adım rehber.
type: docs
weight: 400
url: /tr/net/programming-with-document/validatepdfuastandard/
---
Aspose.PDF for .NET, PDF belgeleriyle çalışmak için çeşitli özellikler sağlayan güçlü bir kitaplıktır. Özelliklerinden biri, PDF belgelerini PDF/UA standart uyumluluğu için doğrulama yeteneğidir. Bu makalede, C# kodunu kullanarak PDF/UA standart uyumluluğunu almak ve doğrulamak için Aspose.PDF for .NET'in nasıl kullanılacağına dair adım adım rehberlik edeceğiz.

## 1. Adım: Belge Dizini Yolunu Tanımlama

Ardından, PDF belgemizin bulunduğu dizine giden yolu tanımlamamız gerekiyor. Aşağıdaki kod parçacığını ekleyerek bunu yapabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"BELGE DİZİNİNİZİ", PDF belge dizininizin gerçek yolu ile değiştirin.

## 2. Adım: PDF Belgesini Açma

Belge dizini yolunu tanımladıktan sonra aşağıdaki kodu kullanarak PDF belgemizi açabiliriz:

```csharp
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");
```

 Bu kod yeni bir oluşturur`Document` belirtilen dizinde bulunan PDF dosyamızdan nesne.

## 3. Adım: PDF'yi PDF/UA için doğrulama

Artık PDF belgesini açtığımıza göre, belgeyi PDF/UA uyumluluğu açısından doğrulamak için Aspose.PDF for .NET'i kullanabiliriz. Aşağıdaki kod parçası işinizi görecektir:

```csharp
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
```

Bu kod, PDF belgesini PDF/UA standart uyumluluğu için doğrular ve belirtilen XML dosyasında bir doğrulama raporu oluşturur. Doğrulama sonucu,`isValidPdfUa` boolean veri tipinde olan değişken.

### Aspose.PDF for .NET kullanarak Get Validate PDFUAstandard için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");

// PDF/UA için PDF'yi Doğrula
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1); 
```
