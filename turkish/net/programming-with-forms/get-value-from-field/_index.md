---
title: PDF Belgesinde Alandan Değer Alın
linktitle: PDF Belgesinde Alandan Değer Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgesindeki bir form alanının değerini kolayca elde edin.
type: docs
weight: 140
url: /tr/net/programming-with-forms/get-value-from-field/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir form alanının değerini nasıl alacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi açın

PDF belgesini açın:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## 3. Adım: Alanı Alın

İstediğiniz form alanını alın (bu örnekte "textbox1" alanını kullanıyoruz):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 4. Adım: Alan değerini alın

 kullanarak alan değerini alın.`Value` mülk:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Aspose.PDF for .NET kullanarak Get Value From Field için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// bir alan al
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Alan değerini al
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir form alanının değerini nasıl alacağımızı öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinizdeki belirli bir form alanının değerini kolayca çıkarabilirsiniz.

### SSS

#### S: Adını önceden bilmeden bir form alanının değerini alabilir miyim?

 C: Hayır, Aspose.PDF for .NET kullanarak değerini almak için form alanının adını veya kısmi adını bilmeniz gerekir. bu`pdfDocument.Form["fieldname"]` sözdizimi, değer de dahil olmak üzere özelliklerine erişmek için form alanının tam adını veya kısmi adını gerektirir.

#### S: PDF belgesinde form alanı yoksa ne olur?

 C: PDF belgesinde form alanı yoksa,`pdfDocument.Form["fieldname"]` sözdizimi geri dönecek`null` . Bu tür durumları kontrol ederek ele almak çok önemlidir.`null` istisnaları önlemek için form alanının özelliklerine erişmeden önce.

#### S: Değerlerini almak için farklı türdeki form alanlarını (ör. onay kutuları, radyo düğmeleri) nasıl kullanabilirim?

 C: Farklı türde form alanlarını işlemek için Aspose.PDF for .NET'te bulunan uygun alan sınıflarını kullanabilirsiniz. Örneğin, kullan`CheckBoxField` onay kutularıyla çalışmak ve`RadioButtonField`radyo düğmeleriyle çalışmak için. Doğru alan nesnesine sahip olduğunuzda, değer de dahil olmak üzere özelliklerine erişebilirsiniz.

#### S: Birden çok form alanının değerlerini aynı anda alabilir miyim?

C: Evet, bir döngü veya LINQ sorguları kullanarak form alanları koleksiyonunu yineleyerek birden çok form alanının değerlerini aynı anda alabilirsiniz. Bu şekilde, PDF belgesindeki her bir form alanının değerine programlı olarak erişebilirsiniz.

#### S: Bir form alanının değerini değiştirmek ve değişiklikleri tekrar PDF belgesine kaydetmek mümkün müdür?

 C: Evet, Aspose.PDF for .NET kullanarak bir form alanının değerini değiştirebilir ve değişiklikleri tekrar PDF belgesine kaydedebilirsiniz. güncelledikten sonra`Value` form alanının özelliğini kullanabilirsiniz`pdfDocument.Save()` değişiklikleri orijinal PDF belgesine kaydetme yöntemi.