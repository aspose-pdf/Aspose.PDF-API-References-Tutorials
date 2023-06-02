---
title: Form Alanını Taşı
linktitle: Form Alanını Taşı
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki form alanlarını kolayca taşıyın.
type: docs
weight: 200
url: /tr/net/programming-with-forms/move-form-field/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki form alanını nasıl taşıyacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Mevcut PDF belgesini yükleyin:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## 3. Adım: Form alanını alın

Taşımak istediğiniz form alanını alın:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 4. Adım: Alan Konumunu Değiştirin

Yeni bir dikdörtgen alan tanımlayarak form alanının konumunu değiştirin:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## 5. Adım: Düzenlenen belgeyi kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.Words for .NET kullanarak Form Alanını Taşı için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// bir alan al
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Alan konumunu değiştir
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Değiştirilen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki form alanını nasıl taşıyacağımızı öğrendik. Bu adımları izleyerek, belirli bir alana kolayca gidebilir ve gerektiğinde konumunu değiştirebilirsiniz.