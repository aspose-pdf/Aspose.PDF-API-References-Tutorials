---
title: ربط التدفقات المكررة
linktitle: ربط التدفقات المكررة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام ميزة Aspose.PDF for .NET Link Duplicate Streams لتحسين مستندات PDF الخاصة بك باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 230
url: /ar/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF for .NET هي مكتبة شاملة وقوية توفر مجموعة متنوعة من الميزات للعمل مع ملفات PDF. إحدى ميزاته الرئيسية هي القدرة على تحسين ملفات PDF. سنشرح في هذه المقالة كيفية استخدام ميزة Link Duplicate Streams في Aspose.PDF لـ .NET لتحسين ملفات PDF. سنقدم تعليمات خطوة بخطوة وندرج مثالًا كاملاً لكود المصدر لتسهيل متابعة المطورين.

## الخطوة 1: فتح مستند PDF

لفتح مستند PDF باستخدام Aspose.PDF لـ .NET، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

في الكود أعلاه، استبدل "YOUR DOCUMENT DIRECTORY" بالمسار إلى دليل مشروعك.

## الخطوة 2: إعداد خيار LinkDuplicateStreams

لتعيين خيار LinkDuplicateStreams، اتبع الخطوات التالية:

```csharp
// قم بتعيين خيار LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

في الكود أعلاه، أنشأنا مثيلًا جديدًا لـ OptimizationOptions وقمنا بتعيين خيار LinkDuplicateStreams على true.

## الخطوة 3: تحسين مستند PDF

لتحسين مستند PDF، اتبع الخطوات التالية:

```csharp
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

في الكود أعلاه، استخدمنا طريقة OptimizeResources لكائن pdfDocument لتحسين مستند PDF باستخدام OptimizationOptions الذي أنشأناه سابقًا.

## الخطوة 4: حفظ المستند المحدث

لحفظ المستند المحدث، اتبع الخطوات التالية:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
```

في الكود أعلاه، استخدمنا طريقة Save لكائن pdfDocument لحفظ المستند المحدث في ملف جديد يسمى "OptimizeDocument_out.pdf" في دليل المشروع.

### مثال على كود المصدر لربط التدفقات المكررة باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// قم بتعيين خيار LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
```

## خاتمة

توفر ميزة ربط التدفقات المكررة في Aspose.PDF لـ .NET طريقة فعالة لتحسين ملفات PDF عن طريق تقليل حجمها. من خلال تحديد التدفقات المكررة وربطها، تساعد المكتبة في إنشاء مستندات PDF أكثر كفاءة دون التضحية بتكامل البيانات أو الجودة المرئية. يمكن للمطورين تنفيذ هذه الميزة بسهولة باستخدام الخطوات المتوفرة ومثال التعليمات البرمجية المصدر، مما يعزز الأداء وكفاءة تخزين ملفات PDF الخاصة بهم.

### الأسئلة الشائعة

#### س: ما هو الغرض من ميزة ربط التدفقات المكررة في Aspose.PDF لـ .NET؟

ج: يتم استخدام ميزة ربط التدفقات المكررة في Aspose.PDF لـ .NET لتحسين ملفات PDF عن طريق تحديد التدفقات المكررة وربطها داخل المستند. في ملف PDF، قد يكون هناك تدفقات مكررة (مثل الصور أو الخطوط) التي تستهلك مساحة غير ضرورية. من خلال ربط هذه التدفقات المكررة، يمكن تقليل حجم الملف، مما يؤدي إلى مستند PDF أصغر حجمًا وأكثر كفاءة.

#### س: كيف تعمل ميزة ربط التدفقات المكررة؟

ج: تعمل ميزة ربط التدفقات المكررة من خلال تحليل تدفقات المحتوى الخاصة بمستند PDF وتحديد التدفقات المكررة التي لها نفس المحتوى. بدلاً من تخزين هذه التدفقات المكررة بشكل منفصل، تقوم الميزة بإنشاء رابط بينها، ومشاركة نفس المحتوى بشكل فعال. تعمل تقنية التحسين هذه على تقليل الحجم الإجمالي لمستند PDF دون التأثير على مظهره المرئي أو وظيفته.

#### س: هل يمكن أن تتسبب ميزة ربط التدفقات المكررة في فقدان البيانات أو الجودة في مستند PDF؟

ج: لا، لا تتسبب ميزة ربط التدفقات المكررة في أي فقدان للبيانات أو الجودة في مستند PDF. فهو يعمل فقط على تحسين حجم الملف عن طريق ربط التدفقات المكررة، دون تغيير المحتوى أو المظهر المرئي للمستند. تم تصميم هذه الميزة لضمان بقاء مستند PDF سليمًا ويحافظ على جودته الأصلية.