---
title: Koordinatları Al
linktitle: Koordinatları Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki form alanı koordinatlarını kolayca alın.
type: docs
weight: 120
url: /tr/net/programming-with-forms/get-coordinates/
---

Bu eğitimde size Aspose.PDF for .NET kullanarak form alanı koordinatlarını nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Çıktı belgesini yükleyin

Çıktı PDF belgesini yükleyin:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## 3. Adım: Eklenen alanları bulun

Eklenen form alanlarını bulun (bu örnekte "Öğe1", "Öğe2" ve "Öğe3" alanlarını kullanıyoruz):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## 4. Adım: Her alan için alt öğe konumlarını görüntüleyin

Her alan için seçenekler arasında gezinin ve her alt öğe için koordinatları görüntüleyin:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Aspose.Words for .NET kullanarak Koordinatları Al için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Çıkış belgesini yükleyin
	Document doc1 = new Document( dataDir + "input.pdf");
	// Eklenen alanları bulun
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Ve her biri için alt öğelerin konumlarını gösterin.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak form alanı koordinatlarını nasıl alacağımızı öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinizdeki form alanlarınızın alt öğelerinin koordinatlarını kolayca alabilirsiniz.