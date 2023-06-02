---
title: PDF إلى XLS
linktitle: PDF إلى XLS
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PDF إلى XLS باستخدام Aspose.PDF for .NET.
type: docs
weight: 200
url: /ar/net/document-conversion/pdf-to-xls/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحويل ملف PDF إلى تنسيق XLS (Microsoft Excel) باستخدام Aspose.PDF for .NET. باتباع الخطوات أدناه ، ستتمكن من تحويل ملف PDF إلى تنسيق XLS.

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

## الخطوة 2: إنشاء خيارات النسخ الاحتياطي في Excel
بعد تحميل ملف PDF ، سنقوم بإنشاء مثيل لخيارات حفظ Excel. استخدم الكود التالي:

```csharp
// إنشاء كائن ExcelSaveOptions
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## الخطوة 3: حفظ ملف XLS الناتج
سنقوم الآن بحفظ ملف PDF المحول بتنسيق XLS. استخدم الكود التالي:

```csharp
// احفظ الإخراج بتنسيق XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 يحفظ الكود أعلاه ملف PDF المحول بتنسيق XLS باسم الملف`"PDFToXLS_out.xls"`.

### مثال على شفرة المصدر لـ PDF إلى XLS باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل مستند PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// إنشاء كائن خيار ExcelSave
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// احفظ الإخراج بتنسيق XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف PDF إلى تنسيق XLS باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون الآن قادرًا على تحويل ملف PDF إلى تنسيق XLS. هذه الميزة مفيدة عندما تريد استخراج بيانات جدولية من ملف PDF واستخدامها في Microsoft Excel.