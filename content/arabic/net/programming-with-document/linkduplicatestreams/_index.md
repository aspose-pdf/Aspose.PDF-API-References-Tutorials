---
title: ربط التدفقات المكررة
linktitle: ربط التدفقات المكررة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام ميزة Aspose.PDF for .NET Link Duplicate Streams لتحسين مستندات PDF الخاصة بك باستخدام هذا الدليل خطوة بخطوة.
type: docs
weight: 230
url: /ar/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF for .NET هي مكتبة شاملة وقوية توفر مجموعة متنوعة من الميزات للعمل مع ملفات PDF. إحدى ميزاتها الرئيسية هي القدرة على تحسين ملفات PDF. في هذه المقالة، سنشرح كيفية استخدام ميزة Link Duplicate Streams في Aspose.PDF for .NET لتحسين ملفات PDF. سنقدم تعليمات خطوة بخطوة وندرج مثالاً كاملاً لرمز المصدر لتسهيل متابعة المطورين.

## الخطوة 1: فتح مستند PDF

لفتح مستند PDF باستخدام Aspose.PDF لـ .NET، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

في الكود أعلاه، استبدل "YOUR DOCUMENT DIRECTORY" بالمسار إلى دليل مشروعك.

## الخطوة 2: ضبط خيار LinkDuplicateStreams

لتعيين خيار LinkDuplicateStreams، اتبع الخطوات التالية:

```csharp
// تعيين خيار LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

في الكود أعلاه، قمنا بإنشاء مثيل جديد لـ OptimizationOptions وتعيين خيار LinkDuplicateStreams إلى true.

## الخطوة 3: تحسين مستند PDF

لتحسين مستند PDF، اتبع الخطوات التالية:

```csharp
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

في الكود أعلاه، استخدمنا طريقة OptimizeResources الخاصة بكائن pdfDocument لتحسين مستند PDF باستخدام OptimizationOptions الذي أنشأناه سابقًا.

## الخطوة 4: حفظ المستند المحدث

لحفظ المستند المحدث، اتبع الخطوات التالية:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
```

في الكود أعلاه، استخدمنا طريقة الحفظ الخاصة بكائن pdfDocument لحفظ المستند المحدث في ملف جديد يسمى "OptimizeDocument_out.pdf" في دليل المشروع.

### مثال على كود المصدر لربط التدفقات المكررة باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// تعيين خيار LinkDuplcateStreams
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

توفر ميزة ربط التدفقات المكررة في Aspose.PDF for .NET طريقة فعّالة لتحسين ملفات PDF عن طريق تقليل حجمها. من خلال تحديد التدفقات المكررة وربطها، تساعد المكتبة في إنشاء مستندات PDF أكثر كفاءة دون التضحية بسلامة البيانات أو الجودة المرئية. يمكن للمطورين تنفيذ هذه الميزة بسهولة باستخدام الخطوات المقدمة ومثال التعليمات البرمجية المصدر، مما يعزز أداء وكفاءة تخزين ملفات PDF الخاصة بهم.

### الأسئلة الشائعة

#### س: ما هو الغرض من ميزة Link Duplicate Streams في Aspose.PDF لـ .NET؟

ج: تُستخدم ميزة ربط التدفقات المكررة في Aspose.PDF لـ .NET لتحسين ملفات PDF من خلال تحديد التدفقات المكررة وربطها داخل المستند. في ملف PDF، قد تكون هناك تدفقات مكررة (مثل الصور أو الخطوط) تستهلك مساحة غير ضرورية. من خلال ربط هذه التدفقات المكررة، يمكن تقليل حجم الملف، مما يؤدي إلى إنشاء مستند PDF أكثر كفاءة وأصغر حجمًا.

#### س: كيف تعمل ميزة ربط التدفقات المكررة؟

ج: تعمل ميزة ربط التدفقات المكررة من خلال تحليل تدفقات المحتوى في مستند PDF وتحديد التدفقات المكررة التي تحتوي على نفس المحتوى. وبدلاً من تخزين هذه التدفقات المكررة بشكل منفصل، تعمل الميزة على إنشاء رابط بينها، ومشاركة نفس المحتوى بشكل فعال. تعمل تقنية التحسين هذه على تقليل الحجم الإجمالي لمستند PDF دون التأثير على مظهره المرئي أو وظائفه.

#### س: هل يمكن أن تتسبب ميزة Link Duplicate Streams في أي فقدان للبيانات أو الجودة في مستند PDF؟

ج: لا، لا تتسبب ميزة ربط التدفقات المكررة في أي فقدان للبيانات أو الجودة في مستند PDF. فهي تعمل فقط على تحسين حجم الملف من خلال ربط التدفقات المكررة، دون تغيير المحتوى أو المظهر المرئي للمستند. تم تصميم الميزة لضمان بقاء مستند PDF سليمًا والحفاظ على جودته الأصلية.