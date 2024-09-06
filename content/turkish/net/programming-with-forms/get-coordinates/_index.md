---
title: PDF Form Alan Koordinatlarını Alın
linktitle: PDF Form Alan Koordinatlarını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki PDF form alanı koordinatlarını kolayca alın.
type: docs
weight: 120
url: /tr/net/programming-with-forms/get-coordinates/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF form alanı koordinatlarını nasıl alacağınızı göstereceğiz. Bu süreçte size rehberlik etmek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kütüphaneleri içe aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Çıktı belgesini yükleyin

Çıktı PDF belgesini yükleyin:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Adım 3: Eklenen alanları bulun

Eklenen form alanlarını bulun (bu örnekte "Item1", "Item2" ve "Item3" alanlarını kullanıyoruz):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Adım 4: Her alan için alt öğe konumlarını görüntüleyin

Her alan için seçenekler arasında gezinin ve her alt öğenin koordinatlarını görüntüleyin:

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

### .NET için Aspose.PDF kullanarak Koordinatları Almak için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Çıktı belgesini yükleyin
	Document doc1 = new Document( dataDir + "input.pdf");
	// Eklenen alanları bul
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Ve her birinin alt öğelerinin pozisyonlarını göster.
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

Bu eğitimde, .NET için Aspose.PDF kullanarak form alanı koordinatlarının nasıl alınacağını öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinizdeki form alanlarınızın alt öğelerinin koordinatlarını kolayca alabilirsiniz.

### SSS

#### S: Bu yöntemi Aspose.PDF for .NET'te herhangi bir form alanı için koordinatları almak amacıyla kullanabilir miyim?

A: Evet, bu yöntemi .NET için Aspose.PDF'de çeşitli form alanı türleri için koordinatları almak için kullanabilirsiniz. Sağlanan C# kaynak kodu, RadioButton alanları için koordinatların nasıl alınacağını gösterir, ancak aynı yaklaşımı TextBox, CheckBox, ListBox ve daha fazlası gibi diğer form alanı türleri için de uyarlayabilirsiniz.

#### S: Form alanı koordinatlarını nasıl değiştirebilir veya ayarlayabilirim?

A: Form alanı koordinatları, başlangıç noktasının (0,0) sayfanın sol alt köşesinde bulunduğu PDF belgesinin koordinat sistemine dayanır. Form alanı koordinatlarını değiştirmek veya ayarlamak için,`Rect` İlgili form alanının veya alt öğelerinin özelliği, örneğin RadioButtonOptionField.

#### S: Form alanlarının koordinatlarını PDF belgesine program aracılığıyla ekleyebilir miyim?

C: Evet, PDF belgesine programatik olarak eklenen form alanlarının koordinatlarını alabilirsiniz. .NET için Aspose.PDF, form alanlarını dinamik olarak eklemenize olanak tanır ve eklendikten sonra, bu eğitimde gösterilen yaklaşımı kullanarak koordinatlarını alabilirsiniz.

#### S: Form alanı koordinatlarını almanın amacı nedir?

A: Form alanı koordinatlarını almak, bir PDF belgesindeki form alanlarında belirli düzen ile ilgili işlemler veya doğrulamalar yapmanız gerektiğinde faydalı olabilir. Form alanlarını koordinatlarına göre doğru bir şekilde konumlandırmanıza ve hizalamanıza olanak tanır, belgede doğru şekilde görünmelerini ve sorunsuz bir kullanıcı deneyimi sağlamalarını sağlar.

#### S: Form alanı koordinatları nokta cinsinden mi yoksa başka bir birimle mi ifade ediliyor?

A: Aspose.PDF for .NET'teki form alanı koordinatları noktalarla ifade edilir. Bir nokta 1/72 inç'e eşdeğerdir ve bu da onu PDF formatında standart bir ölçüm birimi yapar.