---
title: SVG إلى PDF
linktitle: SVG إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: تحويل SVG إلى PDF سهل وسريع باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 280
url: /ar/net/document-conversion/svg-to-pdf/
---
سيرشدك هذا البرنامج التعليمي خلال خطوات تحويل ملف SVG إلى ملف PDF باستخدام Aspose.PDF for .NET. يقدم Aspose.PDF حلاً بسيطًا وفعالاً لتحويل ملفات SVG إلى PDF مع الحفاظ على جودة المحتوى وتخطيطه. اتبع الخطوات أدناه لإجراء هذا التحويل.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل ملف SVG
تتمثل الخطوة الأولى في تحميل ملف SVG في ملف`Document` كائن باستخدام خيار تحميل SVG (`SvgLoadOptions`). استخدم الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن LoadOption باستخدام خيار تحميل SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// إنشاء كائن المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف SVG الخاص بك.

## الخطوة الثانية: التحويل إلى PDF
 الخطوة الثانية هي تحويل مستند SVG إلى مستند PDF باستخدام امتداد الملف`Save` طريقة`Document` هدف. استخدم الكود التالي:

```csharp
// احفظ مستند PDF الناتج
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

تأكد من تحديد المسار المطلوب واسم الملف لملف PDF الناتج.

### مثال على كود المصدر لـ SVG إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن LoadOption باستخدام خيار تحميل SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// إنشاء كائن المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// احفظ مستند PDF الناتج
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل ملف SVG إلى ملف PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات المذكورة أعلاه ، يمكنك بسهولة إجراء هذا التحويل. استخدم هذه الطريقة لتحويل ملفات SVG إلى PDF واستمتع بمرونة وجودة Aspose.PDF.

### التعليمات

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET مكتبة قوية تمكن المطورين من العمل مع مستندات PDF في تطبيقات C #. يوفر وظائف مختلفة ، بما في ذلك تحويل ملفات SVG إلى PDF.

#### س: لماذا أرغب في تحويل ملف SVG إلى PDF؟

ج: تُستخدم ملفات SVG (Scalable Vector Graphics) بشكل شائع للرسومات المتجهة على الويب. يتيح تحويل ملف SVG إلى تنسيق PDF مشاركة أسهل وطباعة ودمج محتوى الرسوم.

#### س: كيف يمكنني تحميل ملف SVG وتحويله إلى PDF باستخدام Aspose.PDF لـ .NET؟

 ج: لتحميل ملف SVG ، يمكنك استخدام الامتداد`SvgLoadOptions` فئة لتحديد خيار تحميل SVG. ثم قم بإنشاء ملف`Document` كائن وتحميل ملف SVG فيه. أخيرًا ، استخدم ملف`Save` طريقة`Document` كائن لتحويل وحفظ SVG كملف PDF.

#### س: هل يمكنني تخصيص ملف PDF الناتج أثناء التحويل؟

ج: نعم ، يمكنك تخصيص ملف PDF الناتج أثناء عملية التحويل. يوفر Aspose.PDF for .NET خيارات وخصائص متنوعة للتحكم في مظهر وتخطيط مستند PDF.

#### س: هل جودة محتوى SVG محفوظة في ملف PDF الناتج؟

ج: نعم ، يضمن Aspose.PDF for .NET الحفاظ على جودة المحتوى والتخطيط أثناء تحويل SVG إلى PDF ، مما يضمن انتقالًا سلسًا بين التنسيقات.