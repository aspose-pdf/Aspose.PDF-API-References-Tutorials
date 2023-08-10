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

### مثال على كود المصدر لـ PDF إلى XLS باستخدام Aspose.PDF لـ .NET

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

### التعليمات

#### س: هل يمكن لـ Aspose.PDF for .NET تحويل ملفات PDF بجداول معقدة وتنسيق إلى تنسيق XLS؟

ج: نعم ، تم تصميم Aspose.PDF for .NET للتعامل مع ملفات PDF بجداول وتنسيقات معقدة. أثناء عملية التحويل إلى تنسيق XLS ، يحاول Aspose.PDF for .NET الحفاظ على تخطيط وهيكل الجداول بأكبر قدر ممكن من الدقة ، مما يضمن استخراج البيانات الجدولية بشكل فعال.

#### س: ماذا يحدث إذا احتوى ملف PDF على صور أو محتوى غير مجدول؟

ج: عند تحويل PDF إلى تنسيق XLS ، يركز Aspose.PDF for .NET بشكل أساسي على استخراج البيانات المجدولة. قد لا يتم الاحتفاظ بالمحتوى غير المجدول ، مثل الصور أو التعليقات التوضيحية أو النص الحر ، في ملف XLS. سيحتوي ملف XLS الناتج بشكل أساسي على بيانات مجدولة مستخرجة من ملف PDF.

#### س: هل من الممكن تخصيص مظهر وتخطيط ملف XLS أثناء التحويل؟

 ج: يوفر Aspose.PDF for .NET خيارات لتخصيص مظهر وتخطيط ملف XLS الناتج. يمكنك ضبط الإعدادات المختلفة باستخدام خصائص`ExcelSaveOptions` class ، مثل تحديد خلية البداية للجدول ، وتعيين تشفير النص ، والتحكم في الخيارات الأخرى المتعلقة بالإخراج.

#### س: هل يمكنني تحويل ملفات PDF المحمية بكلمة مرور إلى تنسيق XLS باستخدام Aspose.PDF لـ .NET؟

 ج: نعم ، يدعم Aspose.PDF for .NET تحويل ملفات PDF المحمية بكلمة مرور إلى تنسيق XLS. عند تحميل ملف PDF محمي بكلمة مرور ، يمكنك توفير كلمة المرور باستخدام ملف`Document` منشئ فئة أو عن طريق تحديد`Password` قبل تحميل ملف PDF.