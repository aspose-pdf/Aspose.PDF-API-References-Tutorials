---
title: PDF Dosyasında Bölgeden Alanları Al
linktitle: PDF Dosyasında Bölgeden Alanları Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki belirli bir bölgedeki alanları kolayca alın.
type: docs
weight: 130
url: /tr/net/programming-with-forms/get-fields-from-region/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasındaki belirli bir bölgenin alanlarını nasıl alacağınızı göstereceğiz. Bu süreçte size rehberlik etmek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kütüphaneleri içe aktardığınızdan ve belgelerinizin dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: PDF dosyasını açın

PDF dosyasını açın:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Adım 3: Bölgeyi sınırlamak için bir dikdörtgen nesnesi oluşturun

Alanları almak istediğiniz bölgeyi sınırlamak için bir dikdörtgen nesnesi oluşturun:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Adım 4: PDF formunu edinin

Belgenin PDF formunu alın:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Adım 5: Dikdörtgen bölgedeki alanları alın

Belirtilen dikdörtgensel bölgede bulunan alanları al:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Adım 6: Alan adlarını ve değerlerini görüntüleyin

Ortaya çıkan alanlar arasında gezinin ve bunların adlarını ve değerlerini görüntüleyin:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### .NET için Aspose.PDF kullanarak Bölgeden Alanları Almak için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF dosyasını aç
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Bu alandaki alanları almak için dikdörtgen nesnesi oluşturun
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// PDF formunu alın
Aspose.Pdf.Forms.Form form = doc.Form;
// Dikdörtgen alandaki alanları alın
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Alan adlarını ve değerlerini görüntüle
foreach (Field field in fields)
{
	// Tüm yerleşimler için görüntü yerleşim özelliklerini görüntüle
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki belirli bir bölgenin alanlarını nasıl alacağımızı öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgenizin belirli bir dikdörtgen alanında bulunan alanları kolayca çıkarabilirsiniz.

### SSS

#### S: Bu yöntemi bir PDF belgesindeki dikdörtgen olmayan bir bölgeden alanları almak için kullanabilir miyim?

 A: Hayır, sağlanan yöntem`GetFieldsInRect` PDF belgesinde dikdörtgen bir bölge içinde bulunan alanları almak için özel olarak tasarlanmıştır. Dikdörtgen olmayan bir bölgeden alanları çıkarmanız gerekiyorsa, alanları alan koordinatları veya adları gibi diğer ölçütlere göre tanımlamak ve çıkarmak için özel mantık uygulamanız gerekir.

#### S: Farklı bir bölgedeki alanları almak için dikdörtgenin boyutunu veya konumunu nasıl değiştirebilirim?

 A: Farklı bir bölgeden alanlar almak için,`Aspose.Pdf.Rectangle` sınırlayıcı dikdörtgeni tanımlamak için kullanılan nesnenin parametreleri.`Rectangle` constructor dört parametre alır:`x`, `y`, `width` , Ve`height`dikdörtgenin sol üst köşe koordinatlarını ve boyutlarını temsil eder. Bu parametreleri ayarlamak, alanların çıkarıldığı bölgeyi değiştirecektir.

#### S: Belirtilen dikdörtgensel bölgede hiçbir alan yoksa ne olur?

 A: Belirtilen dikdörtgen bölge içerisinde herhangi bir alan yoksa,`GetFieldsInRect` yöntemi boş bir dizi döndürecektir. Bölge içerisinde herhangi bir alan olup olmadığını belirlemek için dizinin uzunluğunu kontrol edebilirsiniz.

#### S: PDF belgesinde çakışan bölgelerden alan alabilir miyim?

 A: Evet, birden fazla alan oluşturarak PDF belgesindeki örtüşen bölgelerden alanlar alabilirsiniz.`Aspose.Pdf.Rectangle` nesneler ve çağrı`GetFieldsInRect` her biri için bir yöntem. Çakışan bölgeler bağımsız olarak ele alınacak ve her bölge için ayrı alan dizileri alacaksınız.

#### S: PDF belgesinde belirli bir sayfadan veya birden fazla sayfadan alan almak mümkün müdür?

A: Evet, PDF belgesinde belirli bir sayfadan veya birden fazla sayfadan alanlar alabilirsiniz. Bunu başarmak için PDF belgesini yükleyebilir, istediğiniz sayfalara erişebilirsiniz`doc.Pages` toplama ve ardından uygulama`GetFieldsInRect` Her sayfanın belirli bölgesine özel bir yöntem.