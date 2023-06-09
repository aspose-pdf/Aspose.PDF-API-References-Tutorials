---
title: XFA Özelliklerini Alın
linktitle: XFA Özelliklerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki form alanlarının XFA özelliklerini kolayca elde edin.
type: docs
weight: 160
url: /tr/net/programming-with-forms/get-xfaproperties/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki form alanlarının XFA özelliklerini nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: XFA formunu yükleyin

XFA formunu PDF belgesinden yükleyin:

```csharp
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
```

## 3. Adım: Alan adlarını alın

XFA alan adlarını alın:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## 4. Adım: Alan Değerlerini Ayarlayın

XFA alanları için değerleri ayarlayın:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## 5. Adım: Alanların konumunu alın

XFA alanlarının konumunu alın:

```csharp
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
```

## 6. Adım: Güncellenen belgeyi kaydedin

Güncellenmiş PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Get XFAProperties için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// XFA formunu yükle
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
string[] names = doc.Form.XFA.FieldNames;
// Alan değerlerini ayarla
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
// Saha pozisyonunu al
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
// Saha pozisyonunu al
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
dataDir = dataDir + "Filled_XFA_out.pdf";
// Güncellenen belgeyi kaydedin
doc.Save(dataDir);
Console.WriteLine("\nXFA fields properties retrieved successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki form alanlarının XFA özelliklerini nasıl alacağımızı öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinden konumlar gibi XFA alan bilgilerini kolayca çıkarabilirsiniz.