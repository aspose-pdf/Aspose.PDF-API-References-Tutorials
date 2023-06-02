---
title: XFAFields'ı doldurun
linktitle: XFAFields'ı doldurun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgelerinizdeki XFA alanlarını kolayca doldurun.
type: docs
weight: 90
url: /tr/net/programming-with-forms/fill-xfafields/
---

Bu eğitimde, size Aspose.PDF for .NET kullanarak XFA alanlarını nasıl dolduracağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

İlk olarak, gerekli kitaplıkları içe aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: XFA formunu yükleyin

XFA formunu yükleyin:

```csharp
Document doc = new Document(dataDir + "FillXFAFields.pdf");
```

## 3. Adım: XFA Alan Adlarını Alın

Formun XFA alan adlarını alın:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## 4. Adım: Alan Değerlerini Ayarlayın

Daha önce elde edilen adları kullanarak XFA alan değerlerini ayarlayın:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## 5. Adım: Güncellenen belgeyi kaydedin

Güncellenmiş PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Aspose.Words for .NET kullanan Fill XFAFields için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// XFA formunu yükle
Document doc = new Document(dataDir + "FillXFAFields.pdf");
//XFA form alanlarının adlarını alın
string[] names = doc.Form.XFA.FieldNames;
// Alan değerlerini ayarla
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
dataDir = dataDir + "Filled_XFA_out.pdf";
// Güncellenen belgeyi kaydedin
doc.Save(dataDir);
Console.WriteLine("\nXFA fields filled successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak XFA alanlarını nasıl dolduracağımızı öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinizdeki XFA alanlarının değerlerini kolayca değiştirebilirsiniz.