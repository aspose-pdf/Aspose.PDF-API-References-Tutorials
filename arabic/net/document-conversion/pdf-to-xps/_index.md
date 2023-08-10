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

### التعليمات

#### س: هل تنسيق XPS مناسب للتوافق عبر الأنظمة الأساسية؟

ج: تنسيق XPS ، كونه تنسيق ملف قائم على XML ، لا يعتمد على النظام الأساسي ويمكن عرضه على أنظمة تشغيل وأجهزة مختلفة. يتم دعم ملفات XPS على أنظمة Windows الأساسية افتراضيًا ، وقد تتوفر بعض تطبيقات وعارضات الجهات الخارجية لأنظمة أساسية أخرى.

#### س: هل يمكن لـ Aspose.PDF for .NET التعامل مع ملفات PDF المعقدة بصفحات وصور متعددة أثناء تحويل XPS؟

ج: نعم ، يمكن لـ Aspose.PDF for .NET التعامل مع ملفات PDF المعقدة بصفحات وصور متعددة أثناء تحويل XPS. إنه يحتفظ بدقة بالتخطيط والصور والمحتوى النصي لملف PDF أثناء تحويله إلى تنسيق XPS.

#### س: هل من الممكن تحديد إعدادات أو خيارات إضافية أثناء عملية تحويل XPS؟

 ج: نعم ، يوفر Aspose.PDF for .NET خيارات وإعدادات متنوعة يمكن تخصيصها أثناء عملية تحويل XPS. يمكنك التحكم في ضغط الصورة وتضمين الخط والإعدادات الأخرى باستخدام ملف`XpsSaveOptions` فصل.

#### س: هل يمكن تحويل ملفات PDF المحمية بكلمة مرور إلى تنسيق XPS باستخدام Aspose.PDF لـ .NET؟

 ج: نعم ، يدعم Aspose.PDF for .NET تحويل ملفات PDF المحمية بكلمة مرور إلى تنسيق XPS. عند تحميل ملف PDF محمي بكلمة مرور ، يمكنك توفير كلمة المرور باستخدام ملف`Document` منشئ فئة أو عن طريق تحديد`Password` قبل تحميل ملف PDF.