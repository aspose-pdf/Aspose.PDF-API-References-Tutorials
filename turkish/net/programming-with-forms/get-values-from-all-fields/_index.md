---
title: Tüm Alanlardan Değer Alın
linktitle: Tüm Alanlardan Değer Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki tüm form alanlarının değerlerini kolayca alın.
type: docs
weight: 150
url: /tr/net/programming-with-forms/get-values-from-all-fields/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm form alanlarının değerlerini nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi açın

PDF belgesini açın:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## 3. Adım: Tüm alanlar için değerleri alın

Belgedeki tüm form alanları arasında dolaşın ve adlarını ve değerlerini alın:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Aspose.PDF for .NET kullanarak Tüm Alanlardan Değer Al için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Tüm alanlardan değerleri al
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm form alanlarının değerlerini nasıl alacağımızı öğrendik. Bu adımları izleyerek Aspose.PDF kullanarak tüm form alanlarının değerlerini PDF belgelerinizden kolayca çıkarabilirsiniz.