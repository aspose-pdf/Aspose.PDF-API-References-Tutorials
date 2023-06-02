---
title: حذف حقل النموذج
linktitle: حذف حقل النموذج
second_title: Aspose.PDF لمرجع .NET API
description: قم بإزالة حقول النماذج غير المرغوب فيها بسهولة من مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/programming-with-forms/delete-form-field/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية حذف حقل نموذج باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF الموجود:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## الخطوة 3: حذف حقل معين

حذف حقل نموذج معين باستخدام اسمه:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## الخطوة 4: احفظ المستند المحرر

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لحذف حقل النموذج باستخدام Aspose.Words for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// حذف حقل معين بالاسم
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// احفظ المستند المعدل
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية حذف حقل نموذج باستخدام Aspose.PDF for .NET. باتباع هذه الخطوات ، يمكنك بسهولة إزالة حقول النماذج غير المرغوب فيها من مستندات PDF الخاصة بك باستخدام Aspose.PDF.