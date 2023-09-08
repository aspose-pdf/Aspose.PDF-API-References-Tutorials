---
title: PDF إلى SVG
linktitle: PDF إلى SVG
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PDF إلى SVG باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 180
url: /ar/net/document-conversion/pdf-to-svg/
---
في هذا البرنامج التعليمي، سنرشدك خلال عملية تحويل ملف PDF إلى تنسيق SVG باستخدام Aspose.PDF لـ .NET. SVG (Scalable Vector Graphics) هو تنسيق صور متجه يساعد في الحفاظ على جودة الرسومات وقياسها. باتباع الخطوات أدناه، ستتمكن من تحويل ملف PDF إلى تنسيق SVG.

## المتطلبات الأساسية
قبل البدء، تأكد من استيفاء المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
- مكتبة Aspose.PDF لـ .NET مثبتة على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل وثيقة PDF
في هذه الخطوة سنقوم بتحميل ملف PDF المصدر باستخدام Aspose.PDF لـ .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند PDF
Document doc = new Document(dataDir + "input.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي الذي يوجد به ملف PDF الخاص بك.

## الخطوة 2: إنشاء خيارات حفظ SVG
بعد تحميل ملف PDF، سنقوم بإنشاء خيارات حفظ SVG. استخدم الكود التالي:

```csharp
// إنشاء مثيل لكائن SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// لا تقم بضغط صورة SVG في أرشيف مضغوط
saveOptions.CompressOutputToZipArchive = false;
```

## الخطوة 3: حفظ ملف SVG الناتج
سنقوم الآن بحفظ ملف PDF المحول بتنسيق SVG. استخدم الكود التالي:

```csharp
// حفظ الإخراج إلى ملفات SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 يحفظ الكود أعلاه ملف PDF المحول إلى تنسيق SVG باسم الملف`"PDFToSVG_out.svg"`.

### مثال على الكود المصدري لتحويل PDF إلى SVG باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// تحميل وثيقة PDF
Document doc = new Document(dataDir + "input.pdf");
// إنشاء مثيل لكائن SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// لا تقم بضغط صورة SVG في أرشيف Zip
saveOptions.CompressOutputToZipArchive = false;
// احفظ الإخراج في ملفات SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية عملية تحويل ملف PDF إلى تنسيق SVG خطوة بخطوة باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه، يجب أن تكون الآن قادرًا على تحويل ملف PDF إلى تنسيق SVG. تكون هذه الميزة مفيدة عندما تريد الحفاظ على جودة الرسومات وقياسها عند التحويل إلى صور متجهة.

### الأسئلة الشائعة

#### س: هل يمكنني التحكم في دقة أو حجم ملفات SVG الناتجة أثناء تحويل PDF إلى SVG؟

 ج: نعم، يمكنك التحكم في دقة أو حجم ملفات SVG الناتجة أثناء تحويل PDF إلى SVG باستخدام Aspose.PDF لـ .NET. ال`SvgSaveOptions` يوفر الفصل خصائص مثل`PageSavingCallback` و`SaveFormat` التي تسمح لك بتعيين الدقة أو حجم الصفحة أو المعلمات الأخرى المتعلقة بمخرجات SVG. يمكنك تخصيص هذه الخيارات وفقًا لمتطلباتك للتحكم في جودة وحجم ملفات SVG.

#### س: هل يدعم Aspose.PDF for .NET تحويل ملفات PDF المشفرة أو المحمية بكلمة مرور إلى SVG؟

ج: نعم، يدعم Aspose.PDF for .NET تحويل ملفات PDF المشفرة أو المحمية بكلمة مرور إلى تنسيق SVG. عندما تقوم بتحميل ملف PDF محمي بكلمة مرور، يمكنك توفير كلمة المرور باستخدام`Document` منشئ الفصل أو عن طريق تعيين`Password` الخاصية قبل تحميل ملف PDF. سيتعامل Aspose.PDF for .NET مع فك التشفير أثناء عملية تحويل PDF إلى SVG.

#### س: هل يمكنني تحويل صفحات محددة فقط من ملف PDF إلى SVG بدلاً من المستند بأكمله؟

ج: نعم، يمكنك تحويل صفحات محددة فقط من ملف PDF إلى SVG بدلاً من المستند بأكمله باستخدام Aspose.PDF لـ .NET. قبل حفظ المخرجات كملفات SVG، يمكنك تحديد الصفحات التي تريد تحويلها عن طريق تحديد أرقام الصفحات أو نطاقاتها. بهذه الطريقة، يمكنك استخراج وتحويل الصفحات المطلوبة فقط من تنسيق PDF إلى SVG.

#### س: هل يتوافق Aspose.PDF for .NET مع كافة إصدارات SVG؟

ج: تم تصميم Aspose.PDF for .NET ليكون متوافقًا مع مواصفات SVG 1.1 (رسومات متجهة قابلة للتحجيم). وهو يدعم إنشاء ملفات SVG وفقًا لمعيار SVG 1.1. ومع ذلك، يرجى ملاحظة أنه تم تقديم SVG 2.0 كأحدث إصدار من مواصفات SVG. على الرغم من أن Aspose.PDF for .NET قد لا يزال يعمل بشكل جيد مع SVG 2.0 في العديد من الحالات، فمن المستحسن التحقق من التوافق والقيود المحتملة مع ميزات SVG المحددة التي تنوي استخدامها.