---
title: احصل على القيم من جميع المجالات
linktitle: احصل على القيم من جميع المجالات
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على قيم جميع حقول النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 150
url: /ar/net/programming-with-forms/get-values-from-all-fields/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية الحصول على قيم جميع حقول النموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## الخطوة 3: احصل على قيم لجميع الحقول

قم بالتكرار خلال جميع حقول النموذج في المستند واحصل على أسمائها وقيمها:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### نموذج التعليمات البرمجية المصدر للحصول على قيم من كافة الحقول باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// احصل على القيم من جميع المجالات
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على قيم جميع حقول النموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة استخراج قيم جميع حقول النموذج من مستندات PDF الخاصة بك باستخدام Aspose.PDF.