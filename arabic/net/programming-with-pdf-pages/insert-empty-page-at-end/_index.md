---
title: أدخل صفحة فارغة في النهاية
linktitle: أدخل صفحة فارغة في النهاية
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإدراج صفحة فارغة في نهاية مستند PDF باستخدام Aspose.PDF for .NET. سهل وسريع!
type: docs
weight: 130
url: /ar/net/programming-with-pdf-pages/insert-empty-page-at-end/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لإدراج صفحة فارغة في نهاية مستند PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية إدراج صفحة فارغة في نهاية مستند PDF باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد به ملف PDF الأصلي الخاص بك والمكان الذي تريد حفظ ملف PDF المعدل فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح مستند PDF
 ثم يمكنك فتح مستند PDF باستخدام ملف`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لوثيقة PDF الأصلية.

```csharp
Document pdfDocument1 = new Document(dataDir + "InsertEmptyPageAtEnd.pdf");
```

## الخطوة 3: أدخل صفحة فارغة
 يمكنك الآن إدراج صفحة فارغة في نهاية مستند PDF باستخدام ملف`Add()` طريقة`Pages` ممتلكات`pdfDocument1` هدف.

```csharp
pdfDocument1.Pages.Add();
```

## الخطوة 4: احفظ المستند المعدل
 أخيرًا ، يمكنك حفظ مستند PDF المعدل في ملف باستخدام امتداد`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف لملف الإخراج.

```csharp
dataDir = dataDir + "InsertEmptyPageAtEnd_out.pdf";
pdfDocument1.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Insert Empty Page At End باستخدام Aspose.PDF for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument1 = new Document(dataDir + "InsertEmptyPageAtEnd.pdf");
// أدخل صفحة فارغة في نهاية ملف PDF
pdfDocument1.Pages.Add();
dataDir = dataDir + "InsertEmptyPageAtEnd_out.pdf";
// حفظ ملف الإخراج
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nEmpty page inserted successfully at the end of document.\nFile saved at " + dataDir);

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إدراج صفحة فارغة في نهاية مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة إضافة صفحة فارغة في نهاية مستند PDF الخاص بك. يوفر Aspose.PDF واجهة برمجة تطبيقات قوية ومرنة للعمل مع ملفات PDF ، مما يسمح لك بمعالجة وتعديل وإنشاء مستندات PDF وفقًا لاحتياجاتك الخاصة.
