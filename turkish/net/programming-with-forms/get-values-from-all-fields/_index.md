---
title: PDF Belgesindeki Tüm Alanlardan Değer Alın
linktitle: PDF Belgesindeki Tüm Alanlardan Değer Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgesindeki tüm form alanlarının değerlerini kolayca alın.
type: docs
weight: 150
url: /tr/net/programming-with-forms/get-values-from-all-fields/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm form alanlarının değerlerini nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi açın

PDF belgesini açın:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## 3. Adım: Tüm alanlar için değerleri alın

Belgedeki tüm form alanları arasında dolaşın ve adlarını ve değerlerini alın:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Aspose.PDF for .NET kullanarak Tüm Alanlardan Değer Al için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Tüm alanlardan değerleri al
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm form alanlarının değerlerini nasıl alacağımızı öğrendik. Bu adımları izleyerek Aspose.PDF kullanarak tüm form alanlarının değerlerini PDF belgelerinizden kolayca çıkarabilirsiniz.

### SSS

#### S: Form alanlarının değerlerini Aspose.PDF for .NET kullanarak alırken değiştirebilir miyim?

 C: Evet, form alanlarının değerlerini Aspose.PDF for .NET kullanarak alırken değiştirebilirsiniz. sahip olduğunuzda`Field` bir form alanını temsil eden nesneyi güncelleyebilirsiniz.`Value`istenen değere sahip özellik. Gerekli değişiklikleri yaptıktan sonra, güncellenmiş PDF belgesini değişiklikleri yansıtacak şekilde kaydedebilirsiniz.

#### S: Belirli form alanlarını türlerine (örn. metin alanları, onay kutuları) göre nasıl filtreleyebilirim ve alabilirim?

 C: Türlerine göre belirli form alanlarını almak için, ilgi alanlarını filtrelemek üzere koşullu ifadeleri veya LINQ sorgularını kullanabilirsiniz. Alanın türünü kullanarak her bir form alanının türünü kontrol edebilirsiniz.`FieldType` özelliği ve ardından buna göre değerleri alın.

#### S: PDF belgesinde form alanı yoksa ne olur?

 Y: PDF belgesi herhangi bir form alanı içermiyorsa,`pdfDocument.Form` özellik boş bir koleksiyon döndürür. Bu gibi durumlarda, değerleri alma döngüsü yürütülmez ve hiçbir değer görüntülenmez.

#### S: Form alanı değerlerini belirli bir sırayla alabilir miyim veya alfabetik olarak sıralayabilir miyim?

C: Form alanlarının alınma sırası, PDF belgesinin temel yapısına bağlıdır. Aspose.PDF for .NET, form alanlarını belgeye eklendikleri sırayla döndürür. Form alanlarını belirli bir sırada görüntülemek veya işlemek istiyorsanız, gereksinimlerinize göre özel sıralama mantığı uygulayabilirsiniz.

#### S: Parola korumalı form alanlarıyla şifrelenmiş PDF belgelerini nasıl işleyebilirim?

 Y: Aspose.PDF for .NET, şifrelenmiş PDF belgeleri ve parola korumalı form alanlarıyla çalışmak için özellikler sağlar. Belgeyi yüklemeden önce, parolayı kullanarak ayarlayabilirsiniz.`pdfDocument.Password` özelliği, güvenli PDF belgesine ve form alanlarına erişim sağlar.