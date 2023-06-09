---
title: Bölgeden Alanları Al
linktitle: Bölgeden Alanları Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile belirli bir bölgeden alanları kolayca PDF belgelerinize alın.
type: docs
weight: 130
url: /tr/net/programming-with-forms/get-fields-from-region/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde belirli bir bölgenin alanlarını nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

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
//Dikdörtgen alandaki alanları alın
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