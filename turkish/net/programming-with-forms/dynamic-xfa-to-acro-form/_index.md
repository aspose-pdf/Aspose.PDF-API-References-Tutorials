---
title: Acro Forma Dinamik XFA
linktitle: Acro Forma Dinamik XFA
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile dinamik XFA To formlarını kolayca standart AcroForm formlarına dönüştürün.
type: docs
weight: 70
url: /tr/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir XFA To dinamik formunu bir AcroForm'a nasıl dönüştüreceğinizi göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

İlk olarak, gerekli kitaplıkları içe aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Dinamik XFA formunu yükleyin

Dinamik XFA formunu yükleyin:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Adım 3: Form Türünü Standart AcroForm Olarak Ayarlayın

Form türünü standart AcroForm olarak ayarlayın:

```csharp
document.Form.Type = FormType.Standard;
```

## 4. Adım: Elde Edilen PDF'yi Kaydedin

Ortaya çıkan PDF'yi kaydedin:

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### Aspose.PDF for .NET kullanan Dynamic XFA To Acro Form için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dinamik XFA formu yükle
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Form alanları türünü standart AcroForm olarak ayarlayın
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Ortaya çıkan PDF'yi kaydedin
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir XFA To dinamik formunu standart bir AcroForm formuna dönüştürmeyi öğrendik. Bu adımları izleyerek dinamik XFATo formlarınızı daha yaygın kullanım için kolayca AcroForms'a dönüştürebilirsiniz.