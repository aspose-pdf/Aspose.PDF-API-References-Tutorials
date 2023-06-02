---
title: Alandan Değer Alın
linktitle: Alandan Değer Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki bir form alanının değerini kolayca elde edin.
type: docs
weight: 140
url: /tr/net/programming-with-forms/get-value-from-field/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir form alanının değerini nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi açın

PDF belgesini açın:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## 3. Adım: Alanı Alın

İstediğiniz form alanını alın (bu örnekte "textbox1" alanını kullanıyoruz):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 4. Adım: Alan değerini alın

 kullanarak alan değerini alın.`Value` mülk:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Aspose.Words for .NET kullanarak Get Value From Field için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// bir alan al
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Alan değerini al
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir form alanının değerini nasıl alacağımızı öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinizdeki belirli bir form alanının değerini kolayca çıkarabilirsiniz.