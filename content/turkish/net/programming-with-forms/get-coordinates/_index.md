---
title: PDF Form Alanı Koordinatlarını Alın
linktitle: PDF Form Alanı Koordinatlarını Alın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF belgelerinizdeki PDF form alanı koordinatlarını kolayca alın.
type: docs
weight: 120
url: /tr/net/programming-with-forms/get-coordinates/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak PDF form alanı koordinatlarını nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininin yolunu ayarladığınızdan emin olun:

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

Her alanın seçenekleri arasında gezinin ve her alt öğenin koordinatlarını görüntüleyin:

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
	// Eklenen alanları bul
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

Bu eğitimde Aspose.PDF for .NET kullanarak form alanı koordinatlarının nasıl alınacağını öğrendik. Bu adımları izleyerek form alanlarınızın alt öğelerinin koordinatlarını Aspose.PDF kullanarak PDF belgelerinizde kolayca alabilirsiniz.

### SSS'ler

#### S: Aspose.PDF for .NET'te herhangi bir form alanının koordinatlarını almak için bu yöntemi kullanabilir miyim?

C: Evet, Aspose.PDF for .NET'te çeşitli form alanı türlerinin koordinatlarını almak için bu yöntemi kullanabilirsiniz. Sağlanan C# kaynak kodu, RadioButton alanları için koordinatların nasıl alınacağını gösterir, ancak aynı yaklaşımı TextBox, CheckBox, ListBox ve daha fazlası gibi diğer form alanı türleri için de uyarlayabilirsiniz.

#### S: Form alanı koordinatlarını nasıl değiştirebilirim veya ayarlayabilirim?

C: Form alanı koordinatları, başlangıç noktasının (0,0) sayfanın sol alt köşesinde bulunduğu PDF belgesinin koordinat sistemini temel alır. Form alanı koordinatlarını değiştirmek veya ayarlamak için`Rect` ilgili form alanının veya RadioButtonOptionField gibi alt öğelerinin özelliği.

#### S: Bir PDF belgesine program aracılığıyla eklenen form alanlarının koordinatlarını alabilir miyim?

C: Evet, program aracılığıyla bir PDF belgesine eklenen form alanlarının koordinatlarını alabilirsiniz. Aspose.PDF for .NET, form alanlarını dinamik olarak eklemenizi sağlar ve bir kez eklendiğinde bu eğitimde gösterilen yaklaşımı kullanarak bunların koordinatlarını alabilirsiniz.

#### S: Form alanı koordinatlarını almanın amacı nedir?

C: Bir PDF belgesindeki form alanlarında düzen ile ilgili belirli işlemler veya doğrulamalar yapmanız gerektiğinde form alanı koordinatlarını almak yararlı olabilir. Form alanlarını koordinatlarına göre doğru bir şekilde konumlandırmanıza ve hizalamanıza olanak tanıyarak belgede doğru görünmelerini sağlar ve kusursuz bir kullanıcı deneyimi sunar.

#### S: Form alanı koordinatları noktalarla mı yoksa başka bir birimle mi ifade ediliyor?

C: Aspose.PDF for .NET'teki form alanı koordinatları noktalarla ifade edilir. Bir nokta 1/72 inç'e eşdeğerdir ve bu da onu PDF formatında standart bir ölçü birimi yapar.