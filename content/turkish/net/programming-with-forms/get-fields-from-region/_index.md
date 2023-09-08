---
title: Bölgeden Alanları PDF Dosyasında Al
linktitle: Bölgeden Alanları PDF Dosyasında Al
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasındaki belirli bir bölgedeki alanları kolayca alın.
type: docs
weight: 130
url: /tr/net/programming-with-forms/get-fields-from-region/
---
Bu derste size Aspose.PDF for .NET kullanarak PDF dosyasındaki belirli bir bölgenin alanlarını nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininizin yolunu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF dosyasını açın

PDF dosyasını açın:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## 3. Adım: Bölgeyi sınırlamak için bir dikdörtgen nesnesi oluşturun

Alanları almak istediğiniz bölgeyi sınırlamak için bir dikdörtgen nesnesi oluşturun:

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

### Aspose.PDF for .NET kullanarak Bölgeden Alan Al için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Pdf dosyasını aç
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Bu alandaki alanları almak için dikdörtgen nesnesi oluşturun
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// PDF formunu edinin
Aspose.Pdf.Forms.Form form = doc.Form;
// Dikdörtgen alandaki alanları alın
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Alan adlarını ve değerlerini görüntüle
foreach (Field field in fields)
{
	// Tüm yerleşimler için resim yerleşimi özelliklerini görüntüle
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinde belirli bir bölgenin alanlarını nasıl elde edeceğimizi öğrendik. Bu adımları takip ederek Aspose.PDF'yi kullanarak PDF belgenizin belirli bir dikdörtgen alanında bulunan alanları kolayca çıkarabilirsiniz.

### SSS'ler

#### S: Bir PDF belgesinde dikdörtgen olmayan bir bölgeden alanlar almak için bu yöntemi kullanabilir miyim?

 C: Hayır, sağlanan yöntem`GetFieldsInRect` PDF belgesinde dikdörtgen bir bölge içinde bulunan alanları almak için özel olarak tasarlanmıştır. Dikdörtgen olmayan bir bölgeden alan çıkarmanız gerekiyorsa, alan koordinatları veya adları gibi diğer ölçütlere göre alanları tanımlamak ve çıkarmak için özel mantık uygulamanız gerekir.

#### S: Farklı bir bölgeden alanlar almak için dikdörtgenin boyutunu veya konumunu nasıl değiştirebilirim?

 C: Farklı bir bölgeden alanlar almak için`Aspose.Pdf.Rectangle` sınırlayıcı dikdörtgeni tanımlamak için kullanılan nesnenin parametreleri.`Rectangle` yapıcı dört parametre alır:`x`, `y`, `width` , Ve`height`sol üst köşe koordinatlarını ve dikdörtgenin boyutlarını temsil eder. Bu parametrelerin ayarlanması, alanların çıkarıldığı bölgeyi değiştirecektir.

#### S: Belirtilen dikdörtgen bölge içerisinde hiçbir alan yoksa ne olur?

 C: Belirtilen dikdörtgen bölge içerisinde hiçbir alan yoksa,`GetFieldsInRect` yöntemi boş bir dizi döndürecektir. Bölgede herhangi bir alan olup olmadığını belirlemek için dizinin uzunluğunu kontrol edebilirsiniz.

#### S: Bir PDF belgesinde çakışan bölgelerden alanlar alabilir miyim?

 C: Evet, birden çok alan oluşturarak bir PDF belgesinde çakışan bölgelerden alanlar alabilirsiniz.`Aspose.Pdf.Rectangle` nesneleri çağırmak ve`GetFieldsInRect` Her biri için yöntem. Çakışan bölgeler bağımsız olarak ele alınacak ve her bölge için ayrı alan dizileri alacaksınız.

#### S: PDF belgesindeki belirli bir sayfadan veya birden fazla sayfadan alan almak mümkün mü?

C: Evet, alanları bir PDF belgesindeki belirli bir sayfadan veya birden çok sayfadan alabilirsiniz. Bunu başarmak için PDF belgesini yükleyebilir, istediğiniz sayfalara`doc.Pages` toplayın ve ardından uygulayın`GetFieldsInRect` yöntemi her sayfanın belirli bölgesine göre ayarlayın.