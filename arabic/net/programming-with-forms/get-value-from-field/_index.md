---
title: الحصول على قيمة من الميدان
linktitle: الحصول على قيمة من الميدان
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على قيمة حقل النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 140
url: /ar/net/programming-with-forms/get-value-from-field/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية الحصول على قيمة حقل النموذج باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## الخطوة 3: احصل على الميدان

احصل على حقل النموذج المطلوب (في هذا المثال ، نستخدم حقل "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 4: الحصول على قيمة الحقل

 احصل على قيمة الحقل باستخدام`Value` ملكية:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### نموذج التعليمات البرمجية المصدر لـ Get Value From Field باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// احصل على حقل
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// احصل على قيمة الحقل
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على قيمة حقل النموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة استخراج قيمة حقل نموذج معين في مستندات PDF الخاصة بك باستخدام Aspose.PDF.