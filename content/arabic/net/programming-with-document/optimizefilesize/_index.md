---
title: تحسين حجم الملف في ملف PDF
linktitle: تحسين حجم الملف في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تحسين حجم الملف في ملف PDF باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل خطوة بخطوة.
type: docs
weight: 250
url: /ar/net/programming-with-document/optimizefilesize/
---
Aspose.PDF for .NET هي مكتبة تتيح للمطورين إنشاء ملفات PDF وتحريرها ومعالجتها في تطبيقات .NET الخاصة بهم. إحدى الميزات الأكثر فائدة لهذه المكتبة هي القدرة على تحسين حجم ملف مستند PDF. في هذه المقالة، سنقدم دليلًا خطوة بخطوة لتحسين حجم ملف PDF باستخدام Aspose.PDF for .NET.

## الخطوة 1: تحميل مستند PDF

 الخطوة الأولى لتحسين حجم ملف مستند PDF هي تحميل المستند إلى التطبيق الخاص بك. يمكنك القيام بذلك باستخدام`Document`الفئة التي توفرها مكتبة Aspose.PDF لـ .NET. فيما يلي مثال لكيفية تحميل مستند PDF:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// فتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 تأكد من الاستبدال`YOUR DOCUMENT DIRECTORY` مع المسار إلى الدليل الذي يحتوي على مستند PDF الخاص بك.

## الخطوة 2: تعيين خيارات التحسين

 بمجرد تحميل مستند PDF، يمكنك ضبط خيارات التحسين لتحديد أجزاء المستند التي تريد تحسينها.`OptimizationOptions` تتيح لك الفئة التي توفرها مكتبة Aspose.PDF لـ .NET تحديد مجموعة متنوعة من الخيارات لتحسين حجم ملف مستند PDF. فيما يلي مثال لكيفية تعيين بعض خيارات التحسين:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

في هذا المثال، نقوم بتعيين الخيارات التالية:
- `LinkDuplcateStreams`:يساعدك هذا الخيار على إزالة التدفقات المكررة في مستند PDF، مما قد يساعد في تقليل حجم الملف.
- `RemoveUnusedObjects`:يسمح هذا الخيار بإزالة أي كائنات غير مستخدمة في مستند PDF، مما قد يساعد أيضًا في تقليل حجم الملف.
- `RemoveUnusedStreams`:يسمح هذا الخيار بإزالة أي تدفقات غير مستخدمة في مستند PDF، مما قد يؤدي إلى تقليل حجم الملف بشكل أكبر.
- `CompressImages`:يساعدك هذا الخيار على ضغط الصور الموجودة في مستند PDF، مما قد يؤدي إلى تقليل حجم الملف بشكل كبير.
- `ImageQuality`:يحدد هذا الخيار جودة الصور المضغوطة. سيؤدي ضبط الجودة المنخفضة إلى حجم ملف أصغر، ولكن قد يؤدي أيضًا إلى جودة صورة أقل.

## الخطوة 4: تحسين مستند PDF

 الآن بعد أن قمت بتعيين خيارات التحسين، يمكنك تحسين مستند PDF باستخدام`OptimizeResources` الطريقة التي تقدمها`Document` فيما يلي مثال لكيفية تحسين مستند PDF:

```csharp
// تحسين حجم الملف عن طريق إزالة الكائنات غير المستخدمة
pdfDocument.OptimizeResources(optimizationOptions);
```

## الخطوة 5: احفظ مستند PDF المحسّن

بمجرد تحسين مستند PDF، يمكنك حفظ الإصدار المحسن في ملف جديد. فيما يلي مثال لكيفية حفظ مستند PDF المحسن:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// حفظ المستند الناتج
pdfDocument.Save(dataDir);
```

### مثال على كود المصدر لتحسين حجم الملف باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// فتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
// تحسين حجم الملف عن طريق إزالة الكائنات غير المستخدمة
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// حفظ المستند الناتج
pdfDocument.Save(dataDir);
```

## خاتمة

يعد تحسين حجم ملفات مستندات PDF أمرًا بالغ الأهمية لتحسين الأداء وتجربة المستخدم عند التعامل مع ملفات PDF في تطبيقات .NET. يبسط Aspose.PDF for .NET عملية التحسين من خلال توفير مجموعة واسعة من خيارات التحسين. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم، يمكن للمطورين تحسين مستندات PDF بسهولة، مما يؤدي إلى أحجام ملفات أصغر وتحسين أداء التطبيق.

### الأسئلة الشائعة

#### س: كيف يستفيد المطورون من تحسين حجم ملف مستند PDF؟

أ: إن تحسين حجم ملف مستند PDF يعود بالفائدة على المطورين من خلال تقليل حجم ملفات PDF التي يتم إنشاؤها بواسطة تطبيقاتهم. وتؤدي أحجام الملفات الأصغر إلى أوقات تحميل أسرع وتحسين الأداء، وخاصة عند مشاركة أو توزيع ملفات PDF عبر الويب أو عبر البريد الإلكتروني.

#### س: ما خيارات التحسين التي يمكن للمطورين تعيينها باستخدام Aspose.PDF لـ .NET؟

ج: يوفر Aspose.PDF for .NET للمطورين خيارات تحسين متنوعة لتخصيص عملية تقليل حجم ملف مستند PDF. تتضمن بعض الخيارات المتاحة إزالة التدفقات المكررة، وإزالة الكائنات غير المستخدمة، وإزالة التدفقات غير المستخدمة، وضغط الصور مع التحكم في جودة الصورة.

#### س: هل يمكن للمطورين الموازنة بين تقليل حجم الملف وجودة الصورة عند تحسين مستندات PDF؟

ج: نعم، يتمتع المطورون بالتحكم في خيارات ضغط الصورة، مثل ضبط جودة الصورة. ويمكنهم اختيار التوازن بين تقليل حجم الملف وجودة الصورة بناءً على متطلباتهم المحددة.