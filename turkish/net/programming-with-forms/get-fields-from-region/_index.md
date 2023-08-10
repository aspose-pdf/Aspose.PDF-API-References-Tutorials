---
title: PDF Dosyasında Bölgeden Alanları Alın
linktitle: PDF Dosyasında Bölgeden Alanları Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki belirli bir bölgeden alanları kolayca alın.
type: docs
weight: 130
url: /tr/net/programming-with-forms/get-fields-from-region/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasında belirli bir bölgenin alanlarını nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF dosyasını açın

PDF dosyasını açın:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## 3. Adım: Bölgeyi sınırlamak için bir dikdörtgen nesne oluşturun

Alanları almak istediğiniz bölgeyi sınırlamak için bir dikdörtgen nesne oluşturun:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## 4. Adım: PDF formunu edinin

Belgenin PDF formunu alın:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Adım 5: Dikdörtgen bölgedeki alanları alın

Belirtilen dikdörtgen bölgede bulunan alanları alın:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## 6. Adım: Alan adlarını ve değerlerini görüntüleyin

Ortaya çıkan alanları yineleyin ve adlarını ve değerlerini görüntüleyin:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Aspose.PDF for .NET kullanarak Bölgeden Alan Getir için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// pdf dosyasını aç
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Bu alandaki alanları almak için dikdörtgen nesne oluşturun
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// PDF formunu edinin
Aspose.Pdf.Forms.Form form = doc.Form;
// Dikdörtgen alandaki alanları alın
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Görüntü Alan adları ve değerleri
foreach (Field field in fields)
{
	// Tüm yerleşimler için resim yerleşimi özelliklerini göster
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde belirli bir bölgenin alanlarını nasıl alacağımızı öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgenizin belirli bir dikdörtgen alanında bulunan alanları kolayca çıkarabilirsiniz.

### SSS

#### S: Bir PDF belgesinde dikdörtgen olmayan bir bölgeden alanlar almak için bu yöntemi kullanabilir miyim?

 C: Hayır, sağlanan yöntem`GetFieldsInRect` bir PDF belgesinde dikdörtgen bir bölge içinde yer alan alanları almak için özel olarak tasarlanmıştır. Dikdörtgen olmayan bir bölgeden alanları ayıklamanız gerekirse, alanları, alan koordinatları veya adları gibi diğer ölçütlere göre tanımlamak ve ayıklamak için özel bir mantık uygulamanız gerekir.

#### S: Farklı bir bölgeden alanlar almak için dikdörtgenin boyutunu veya konumunu nasıl değiştirebilirim?

 C: Farklı bir bölgeden alanlar almak için`Aspose.Pdf.Rectangle` sınırlayıcı dikdörtgeni tanımlamak için kullanılan nesnenin parametreleri. bu`Rectangle` yapıcı dört parametre alır:`x`, `y`, `width` , Ve`height`sol üst köşe koordinatlarını ve dikdörtgenin boyutlarını temsil eder. Bu parametreleri ayarlamak, alanların ayıklandığı bölgeyi değiştirecektir.

#### S: Belirtilen dikdörtgen bölgede hiç alan yoksa ne olur?

 A: Belirtilen dikdörtgen bölge içinde alan yoksa,`GetFieldsInRect` yöntem boş bir dizi döndürür. Bölge içinde herhangi bir alan olup olmadığını belirlemek için dizinin uzunluğunu kontrol edebilirsiniz.

#### S: Bir PDF belgesinde çakışan bölgelerden alanlar alabilir miyim?

 C: Evet, bir PDF belgesinde birden çok alan oluşturarak çakışan bölgelerden alanlar alabilirsiniz.`Aspose.Pdf.Rectangle` nesneler ve çağırma`GetFieldsInRect` Her biri için yöntem. Çakışan bölgeler bağımsız olarak ele alınır ve her bölge için ayrı alan dizileri alırsınız.

#### S: PDF belgesinde belirli bir sayfadan veya birden çok sayfadan alanlar almak mümkün mü?

Y: Evet, bir PDF belgesinde belirli bir sayfadan veya birden çok sayfadan alanlar alabilirsiniz. Bunu başarmak için PDF belgesini yükleyebilir, istediğiniz sayfalara`doc.Pages` toplama ve ardından`GetFieldsInRect` yöntemi her sayfanın belirli bölgesine.