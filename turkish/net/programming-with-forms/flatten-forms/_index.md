---
title: Formları Düzleştir
linktitle: Formları Düzleştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgelerinizdeki formları kolayca düzleştirin.
type: docs
weight: 100
url: /tr/net/programming-with-forms/flatten-forms/
---

Bu eğitimde size Aspose.PDF for .NET kullanarak formları nasıl düzleştireceğinizi göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

İlk olarak, gerekli kitaplıkları içe aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Kaynak PDF formunu yükleyin

Kaynak PDF formunu yükleyin:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 3. Adım: Formları düzleştirin

Önce belgede herhangi bir form alanı olup olmadığını kontrol edin. Öyleyse, her alanı yineleyin ve düzleştirme uygulayın:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## 4. Adım: Güncellenen belgeyi kaydedin

Güncellenmiş PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Aspose.Words for .NET kullanarak Flatten Forms için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Kaynak PDF formunu yükle
Document doc = new Document(dataDir + "input.pdf");
// Formları Düzleştir
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Güncellenen belgeyi kaydedin
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak formları nasıl düzleştireceğimizi öğrendik. Bu adımları izleyerek, PDF belgelerinizdeki formları kolayca düzleştirebilir, alanları düzenlenemez hale getirebilir ve açıklamaları belge içeriğiyle birleştirebilirsiniz.