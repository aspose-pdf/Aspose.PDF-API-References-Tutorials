---
title: نقل حقل النموذج
linktitle: نقل حقل النموذج
second_title: Aspose.PDF لمرجع .NET API
description: انقل حقول النموذج بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 200
url: /ar/net/programming-with-forms/move-form-field/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية نقل حقل نموذج في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

قم بتحميل مستند PDF الحالي:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## الخطوة 3: احصل على حقل النموذج

احصل على حقل النموذج الذي تريد نقله:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 4: تغيير موقع الحقل

قم بتغيير موقع حقل النموذج عن طريق تحديد منطقة مستطيلة جديدة:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## الخطوة 5: احفظ المستند المحرر

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Move Form Field باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// احصل على حقل
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// تعديل موقع الحقل
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// احفظ المستند المعدل
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية نقل حقل نموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك التنقل بسهولة إلى حقل معين وتغيير موقعه حسب الحاجة.