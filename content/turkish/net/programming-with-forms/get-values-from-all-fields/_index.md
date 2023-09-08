---
title: PDF Belgesindeki Tüm Alanlardan Değer Al
linktitle: PDF Belgesindeki Tüm Alanlardan Değer Al
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF belgesindeki tüm form alanlarının değerlerini kolayca alın.
type: docs
weight: 150
url: /tr/net/programming-with-forms/get-values-from-all-fields/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm form alanlarının değerlerini nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininizin yolunu ayarladığınızdan emin olun:

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
// Tüm alanlardan değer alın
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm form alanlarının değerlerini nasıl elde edeceğimizi öğrendik. Bu adımları takip ederek Aspose.PDF'yi kullanarak tüm form alanlarının değerlerini PDF belgelerinizden kolayca çıkarabilirsiniz.

### SSS'ler

#### S: Aspose.PDF for .NET'i kullanarak form alanlarının değerlerini alırken değiştirebilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak form alanlarının değerlerini alırken değiştirebilirsiniz. Bir kez sahip olduğunuzda`Field` Bir form alanını temsil eden nesneyi güncelleyebilirsiniz.`Value`İstenilen değere sahip özellik. Gerekli değişiklikleri yaptıktan sonra güncellenen PDF belgesini değişiklikleri yansıtacak şekilde kaydedebilirsiniz.

#### S: Belirli form alanlarını türlerine göre (örneğin, metin alanları, onay kutuları) nasıl filtreleyebilir ve alabilirim?

 C: Türlerine göre belirli form alanlarını almak için, ilgi alanlarını filtrelemek üzere koşullu ifadeleri veya LINQ sorgularını kullanabilirsiniz. Her form alanının türünü, alanın`FieldType` özelliği ve ardından buna göre değerleri alın.

#### S: PDF belgesinde form alanı yoksa ne olur?

 C: PDF belgesi herhangi bir form alanı içermiyorsa,`pdfDocument.Form` özellik boş bir koleksiyon döndürecektir. Bu gibi durumlarda, değerlerin alınmasına yönelik döngü yürütülmeyecek ve hiçbir değer görüntülenmeyecektir.

#### S: Form alanı değerlerini belirli bir sıraya göre çıkarabilir miyim veya bunları alfabetik olarak sıralayabilir miyim?

C: Form alanlarının alınma sırası PDF belgesinin temel yapısına bağlıdır. Aspose.PDF for .NET form alanlarını belgeye eklendikleri sıraya göre döndürür. Form alanlarını belirli bir sırayla görüntülemek veya işlemek istiyorsanız gereksinimlerinize göre özel sıralama mantığı uygulayabilirsiniz.

#### S: Şifre korumalı form alanlarıyla şifrelenmiş PDF belgelerini nasıl işleyebilirim?

 C: Aspose.PDF for .NET, şifrelenmiş PDF belgeleri ve parola korumalı form alanlarıyla çalışma özellikleri sağlar. Belgeyi yüklemeden önce, parolayı kullanarak ayarlayabilirsiniz.`pdfDocument.Password` Güvenli PDF belgesine ve form alanlarına erişim özelliği.