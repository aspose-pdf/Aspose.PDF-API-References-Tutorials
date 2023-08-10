---
title: PDF Form Alanı Koordinatlarını Alın
linktitle: PDF Form Alanı Koordinatlarını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki PDF form alanı koordinatlarını kolayca alın.
type: docs
weight: 120
url: /tr/net/programming-with-forms/get-coordinates/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF form alanı koordinatlarını nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

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

### Aspose.PDF for .NET kullanarak Koordinatları Al için örnek kaynak kodu 
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

### SSS

#### S: Aspose.PDF for .NET'te herhangi bir form alanı için koordinat almak için bu yöntemi kullanabilir miyim?

C: Evet, Aspose.PDF for .NET'te çeşitli form alanları için koordinatlar almak için bu yöntemi kullanabilirsiniz. Sağlanan C# kaynak kodu, RadioButton alanları için koordinatların nasıl alınacağını gösterir, ancak aynı yaklaşımı TextBox, CheckBox, ListBox ve daha fazlası gibi diğer form alanı türleri için de uyarlayabilirsiniz.

#### S: Form alanı koordinatlarını nasıl değiştirebilir veya ayarlayabilirim?

C: Form alanı koordinatları, başlangıç noktasının (0,0) sayfanın sol alt köşesinde bulunduğu PDF belgesinin koordinat sistemini temel alır. Form alanı koordinatlarını değiştirmek veya ayarlamak için`Rect` ilgili form alanının veya RadioButtonOptionField gibi alt öğelerinin özelliği.

#### S: Bir PDF belgesine programlı olarak eklenen form alanlarının koordinatlarını alabilir miyim?

C: Evet, programlı olarak bir PDF belgesine eklenen form alanlarının koordinatlarını alabilirsiniz. Aspose.PDF for .NET, form alanlarını dinamik olarak eklemenizi sağlar ve eklendikten sonra, bu eğitimde gösterilen yaklaşımı kullanarak bunların koordinatlarını alabilirsiniz.

#### S: Form alanı koordinatlarını almanın amacı nedir?

C: Form alanı koordinatlarını almak, bir PDF belgesindeki form alanlarında mizanpajla ilgili belirli işlemler veya doğrulamalar gerçekleştirmeniz gerektiğinde yardımcı olabilir. Form alanlarını koordinatlarına göre doğru bir şekilde konumlandırmanıza ve hizalamanıza olanak tanıyarak belgede doğru şekilde görünmelerini ve sorunsuz bir kullanıcı deneyimi sunmalarını sağlar.

#### S: Form alanı koordinatları noktalarla mı yoksa başka bir birimle mi ifade ediliyor?

C: Aspose.PDF for .NET'teki form alanı koordinatları nokta olarak ifade edilmiştir. Bir nokta 1/72 inç'e eşdeğerdir ve bu da onu PDF biçiminde standart bir ölçü birimi yapar.