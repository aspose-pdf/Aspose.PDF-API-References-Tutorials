---
title: PDF إلى SVG
linktitle: PDF إلى SVG
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PDF إلى SVG باستخدام Aspose.PDF for .NET.
type: docs
weight: 180
url: /ar/net/document-conversion/pdf-to-svg/
---
في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحويل ملف PDF إلى تنسيق SVG باستخدام Aspose.PDF لـ .NET. SVG (Scalable Vector Graphics) هو تنسيق صورة متجه يساعد في الحفاظ على جودة الرسومات وقياسها. باتباع الخطوات أدناه ، ستتمكن من تحويل ملف PDF إلى تنسيق SVG.

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
Document doc = new Document(dataDir + "input.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف PDF الخاص بك.

## الخطوة 2: إنشاء مثيل لخيارات حفظ SVG
بعد تحميل ملف PDF ، سنقوم بإنشاء مثيل لخيارات حفظ SVG. استخدم الكود التالي:

```csharp
// إنشاء كائن SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// لا تضغط صورة SVG في أرشيف مضغوط
saveOptions.CompressOutputToZipArchive = false;
```

## الخطوة 3: حفظ ملف SVG الناتج
سنقوم الآن بحفظ ملف PDF المحول بتنسيق SVG. استخدم الكود التالي:

```csharp
// حفظ الإخراج إلى ملفات SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 يحفظ الكود أعلاه ملف PDF المحول إلى تنسيق SVG باسم الملف`"PDFToSVG_out.svg"`.

### مثال على كود المصدر لـ PDF إلى SVG باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل مستند PDF
Document doc = new Document(dataDir + "input.pdf");
// إنشاء كائن من SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// لا تضغط صورة SVG على أرشيف مضغوط
saveOptions.CompressOutputToZipArchive = false;
// احفظ الإخراج في ملفات SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف PDF إلى تنسيق SVG باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون قادرًا الآن على تحويل ملف PDF إلى تنسيق SVG. هذه الميزة مفيدة عندما تريد الحفاظ على جودة الرسومات والقياس عند التحويل إلى صور متجهة.

### التعليمات

#### س: هل يمكنني التحكم في دقة أو حجم ملفات SVG الناتجة أثناء تحويل PDF إلى SVG؟

 ج: نعم ، يمكنك التحكم في دقة أو حجم ملفات SVG الناتجة أثناء تحويل PDF إلى SVG باستخدام Aspose.PDF لـ .NET. ال`SvgSaveOptions` فئة توفر خصائص مثل`PageSavingCallback` و`SaveFormat` التي تسمح لك بتعيين الدقة أو حجم الصفحة أو غيرها من المعلمات المتعلقة بإخراج SVG. يمكنك تخصيص هذه الخيارات وفقًا لمتطلباتك للتحكم في جودة وحجم ملفات SVG.

#### س: هل يدعم Aspose.PDF for .NET تحويل ملفات PDF المشفرة أو المحمية بكلمة مرور إلى SVG؟

ج: نعم ، يدعم Aspose.PDF for .NET تحويل ملفات PDF المشفرة أو المحمية بكلمة مرور إلى تنسيق SVG. عند تحميل ملف PDF محمي بكلمة مرور ، يمكنك توفير كلمة المرور باستخدام ملف`Document` منشئ فئة أو عن طريق تحديد`Password` قبل تحميل ملف PDF. Aspose.PDF for .NET سوف يتعامل مع فك التشفير أثناء عملية تحويل PDF إلى SVG.

#### س: هل يمكنني تحويل صفحات معينة فقط من PDF إلى SVG بدلاً من المستند بأكمله؟

ج: نعم ، يمكنك تحويل صفحات معينة فقط من PDF إلى SVG بدلاً من المستند بأكمله باستخدام Aspose.PDF لـ .NET. قبل حفظ المخرجات كملفات SVG ، يمكنك تحديد الصفحات التي تريد تحويلها عن طريق تحديد أرقام الصفحات أو النطاقات الخاصة بها. بهذه الطريقة ، يمكنك استخراج وتحويل الصفحات المطلوبة فقط من تنسيق PDF إلى SVG.

#### س: هل Aspose.PDF for .NET متوافق مع كافة إصدارات SVG؟

ج: تم تصميم Aspose.PDF for .NET ليكون متوافقًا مع مواصفات SVG 1.1 (Scalable Vector Graphics). يدعم إنشاء ملفات SVG وفقًا لمعيار SVG 1.1. ومع ذلك ، يرجى ملاحظة أنه تم تقديم SVG 2.0 كأحدث إصدار من مواصفات SVG. بينما قد يستمر Aspose.PDF for .NET العمل بشكل جيد مع SVG 2.0 في كثير من الحالات ، يوصى بالتحقق من التوافق والقيود المحتملة مع ميزات SVG المحددة التي تنوي استخدامها.