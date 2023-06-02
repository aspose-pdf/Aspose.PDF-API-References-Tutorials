---
title: Form Alanını Değiştir
linktitle: Form Alanını Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki form alanlarını kolayca düzenleyin.
type: docs
weight: 190
url: /tr/net/programming-with-forms/modify-form-field/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki form alanını nasıl düzenleyeceğinizi göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Mevcut PDF belgesini yükleyin:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## 3. Adım: Form alanını alın

Düzenlemek istediğiniz form alanını alın:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 4. Adım: Alan değerini değiştirin

Form alanı değerini değiştirin:

```csharp
textBoxField.Value = "New Value";
```

## 5. Adım: Alan Özelliklerini Düzenleyin

Ek form alanı özelliklerini gerektiği gibi değiştirin. Örneğin, salt okunur yapabilirsiniz:

```csharp
textBoxField.ReadOnly = true;
```

## 6. Adım: Düzenlenen belgeyi kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.Words for .NET kullanarak Modify Form Field için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// bir alan al
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Alan değerini değiştir
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki form alanını nasıl düzenleyeceğimizi öğrendik. Bu adımları izleyerek belirli bir alana kolayca gidebilir, değerini değiştirebilir ve özelliklerini gerektiği gibi ayarlayabilirsiniz.