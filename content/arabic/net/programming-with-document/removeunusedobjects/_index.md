---
title: إزالة الكائنات غير المستخدمة في ملف PDF
linktitle: إزالة الكائنات غير المستخدمة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET لإزالة الكائنات غير المستخدمة في ملف PDF باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 260
url: /ar/net/programming-with-document/removeunusedobjects/
---
إذا كنت تبحث عن طريقة لإزالة الكائنات غير المستخدمة في ملف PDF الخاص بك باستخدام Aspose.PDF لـ .NET، فأنت في المكان الصحيح. سيوضح لك هذا الدليل خطوة بخطوة كيفية استخدام كود مصدر C# المقدم لإنجاز هذه المهمة.

## الخطوة 1: قم بتعيين مسار الدليل

أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك عن طريق استبدال "YOUR DOCUMENT DIRECTORY" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

بعد ذلك، تحتاج إلى فتح مستند PDF الذي تريد تحسينه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## الخطوة 3: قم بتعيين خيار RemoveUnusedObjects

لإزالة الكائنات غير المستخدمة في مستند PDF الخاص بك، تحتاج إلى ضبط خيار RemoveUnusedObjects على "true" كما يلي:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## الخطوة 4: تحسين مستند PDF باستخدام OptimizationOptions

الآن، يمكنك تحسين مستند PDF الخاص بك باستخدام طريقة OptimizeResources مع خيارات التحسين التي قمت بتعيينها للتو:

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 5: احفظ المستند المحدث

وأخيرًا، يمكنك حفظ المستند المحدث بالكود التالي:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

هذا كل شيء! لقد نجحت في إزالة الكائنات غير المستخدمة من مستند PDF الخاص بك باستخدام Aspose.PDF لـ .NET.

### مثال على التعليمات البرمجية المصدر لإزالة الكائنات غير المستخدمة باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// قم بتعيين خيار RemoveUsedObject
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
```

## خاتمة

 يعد تحسين مستندات PDF عن طريق إزالة الكائنات غير المستخدمة خطوة أساسية لتحسين حجم الملف والأداء العام. يعمل Aspose.PDF for .NET على تبسيط هذه العملية من خلال توفير طريقة مباشرة لإزالة الكائنات غير المستخدمة باستخدام`OptimizationOptions`. باتباع الدليل الموضح خطوة بخطوة واستخدام كود مصدر C# المقدم، يمكن للمطورين تحسين مستندات PDF الخاصة بهم بسهولة وتحقيق معالجة أكثر كفاءة وسرعة لملفات PDF في تطبيقات .NET الخاصة بهم.

### الأسئلة الشائعة لإزالة الكائنات غير المستخدمة في ملف PDF

#### س: ما هي الكائنات غير المستخدمة في وثيقة PDF؟

ج: الكائنات غير المستخدمة في مستند PDF هي عناصر مثل الخطوط أو الصور أو التعليقات التوضيحية أو الموارد الأخرى التي لم يعد يتم الرجوع إليها أو استخدامها في محتوى المستند. يمكن أن تؤدي إزالة هذه الكائنات غير المستخدمة إلى تقليل حجم الملف بشكل كبير وتحسين مستند PDF.

#### س: كيف تفيد إزالة الكائنات غير المستخدمة مستندات PDF؟

ج: تؤدي إزالة الكائنات غير المستخدمة من مستند PDF إلى تقليل حجم الملف، مما يؤدي إلى أوقات تحميل أسرع وتحسين الأداء وتقليل مساحة التخزين. كما أنه يساعد في ضمان تجربة مستخدم أكثر كفاءة عند مشاركة ملفات PDF أو توزيعها.

#### س: هل يمكن للمطورين التحكم في الكائنات غير المستخدمة التي سيتم إزالتها باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكن للمطورين التحكم في إزالة الكائنات غير المستخدمة عن طريق تعيين`RemoveUnusedObjects` الخيار في`OptimizationOptions`. يتيح لهم ذلك تحديد ما إذا كانوا يريدون إزالة جميع الكائنات غير المستخدمة أو الاحتفاظ بكائنات معينة بناءً على متطلباتهم المحددة.