---
title: PDF إلى XPS
linktitle: PDF إلى XPS
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PDF إلى XPS باستخدام Aspose.PDF for .NET.
type: docs
weight: 220
url: /ar/net/document-conversion/pdf-to-xps/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحويل ملف PDF إلى تنسيق XPS (مواصفات ورق XML) باستخدام Aspose.PDF for .NET. تنسيق XPS هو تنسيق ملف مستند إلى XML يُستخدم لتمثيل المستندات إلكترونيًا. باتباع الخطوات أدناه ، ستتمكن من تحويل ملف PDF إلى تنسيق XPS.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل مستند PDF
في هذه الخطوة سنقوم بتحميل ملف PDF المصدر باستخدام Aspose.PDF for .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف PDF الخاص بك.

## الخطوة 2: إنشاء خيارات حفظ XPS
بعد تحميل ملف PDF ، سنقوم بإنشاء مثيل لخيارات حفظ XPS. استخدم الكود التالي:

```csharp
// إنشاء خيارات حفظ XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## الخطوة 3: حفظ ملف XPS الناتج
سنقوم الآن بحفظ ملف PDF المحول بتنسيق XPS. استخدم الكود التالي:

```csharp
// احفظ مستند XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 يحفظ الكود أعلاه ملف PDF المحول بتنسيق XPS باسم الملف`"PDFToXPS_out.xps"`.


### مثال على شفرة المصدر لـ PDF إلى XPS باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل مستند PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// إنشاء خيارات حفظ XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// احفظ مستند XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف PDF إلى تنسيق XPS باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون قادرًا الآن على تحويل ملف PDF إلى تنسيق XPS. هذه الميزة مفيدة عندما تريد عرض أو طباعة مستندات PDF بتنسيق XPS.