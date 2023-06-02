---
title: ملء حقل النموذج
linktitle: ملء حقل النموذج
second_title: Aspose.PDF لمرجع .NET API
description: قم بملء حقول النموذج بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/programming-with-forms/fill-form-field/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية ملء حقل نموذج باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF الموجود:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## الخطوة 3: احصل على الميدان

احصل على حقل النموذج المطلوب (في هذا المثال ، نستخدم حقل "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 4: قم بتغيير قيمة الحقل

قم بتعديل قيمة الحقل بالقيمة المطلوبة:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## الخطوة 5: احفظ المستند المحدث

احفظ مستند PDF المحدث:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج لشفرة مصدر لملء حقل النموذج باستخدام Aspose.Words for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// احصل على حقل
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// تعديل قيمة الحقل
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية ملء حقل نموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة تغيير قيم حقل النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF.