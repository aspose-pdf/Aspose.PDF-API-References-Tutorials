---
title: تحسين حجم الملف في ملف PDF
linktitle: تحسين حجم الملف في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحسين حجم الملف في ملف PDF باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 250
url: /ar/net/programming-with-document/optimizefilesize/
---
Aspose.PDF for .NET هي مكتبة تمكن المطورين من إنشاء ملفات PDF وتحريرها ومعالجتها في تطبيقات .NET الخاصة بهم. إحدى الميزات الأكثر فائدة لهذه المكتبة هي القدرة على تحسين حجم ملف مستند PDF. في هذه المقالة، سنقدم دليلًا خطوة بخطوة لتحسين حجم ملف PDF باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: قم بتحميل مستند PDF

 الخطوة الأولى في تحسين حجم ملف مستند PDF هي تحميل المستند في التطبيق الخاص بك. يمكنك القيام بذلك باستخدام`Document`فئة مقدمة من Aspose.PDF لمكتبة .NET. فيما يلي مثال لكيفية تحميل مستند PDF:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 تأكد من استبدال`YOUR DOCUMENT DIRECTORY` مع المسار إلى الدليل الذي يحتوي على مستند PDF الخاص بك.

## الخطوة 2: ضبط خيارات التحسين

 بمجرد قيامك بتحميل مستند PDF، يمكنك ضبط خيارات التحسين لتحديد أجزاء المستند التي تريد تحسينها. ال`OptimizationOptions` تتيح لك الفئة التي توفرها مكتبة Aspose.PDF لـ .NET تحديد مجموعة متنوعة من الخيارات لتحسين حجم ملف مستند PDF. فيما يلي مثال لكيفية تعيين بعض خيارات التحسين:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

في هذا المثال، نقوم بتعيين الخيارات التالية:
- `LinkDuplcateStreams`: يتيح هذا الخيار إمكانية إزالة التدفقات المكررة في مستند PDF، مما قد يساعد في تقليل حجم الملف.
- `RemoveUnusedObjects`: يتيح هذا الخيار إزالة أي كائنات غير مستخدمة في مستند PDF، مما قد يساعد أيضًا في تقليل حجم الملف.
- `RemoveUnusedStreams`يتيح هذا الخيار إزالة أي تدفقات غير مستخدمة في مستند PDF، مما قد يؤدي إلى تقليل حجم الملف بشكل أكبر.
- `CompressImages`: يتيح هذا الخيار ضغط الصور في مستند PDF، مما قد يؤدي إلى تقليل حجم الملف بشكل كبير.
- `ImageQuality`: يضبط هذا الخيار جودة الصور المضغوطة. سيؤدي إعداد الجودة الأقل إلى حجم ملف أصغر، ولكنه قد يؤدي أيضًا إلى انخفاض جودة الصورة.

## الخطوة 4: تحسين مستند PDF

 الآن بعد أن قمت بتعيين خيارات التحسين، يمكنك تحسين مستند PDF باستخدام`OptimizeResources` الطريقة المقدمة من`Document` فصل. فيما يلي مثال لكيفية تحسين مستند PDF:

```csharp
// قم بتحسين حجم الملف عن طريق إزالة الكائنات غير المستخدمة
pdfDocument.OptimizeResources(optimizationOptions);
```

## الخطوة 5: احفظ مستند PDF المحسن

بمجرد الانتهاء من تحسين مستند PDF، يمكنك حفظ النسخة المحسنة في ملف جديد. فيما يلي مثال لكيفية حفظ مستند PDF المحسن:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// حفظ مستند الإخراج
pdfDocument.Save(dataDir);
```

### مثال على كود المصدر لتحسين حجم الملف باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
// قم بتحسين حجم الملف عن طريق إزالة الكائنات غير المستخدمة
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// حفظ مستند الإخراج
pdfDocument.Save(dataDir);
```

## خاتمة

يعد تحسين حجم ملف مستندات PDF أمرًا ضروريًا لتحسين الأداء وتجربة المستخدم عند التعامل مع ملفات PDF في تطبيقات .NET. يعمل Aspose.PDF for .NET على تبسيط عملية التحسين من خلال توفير نطاق واسع من خيارات التحسين. من خلال اتباع الدليل خطوة بخطوة واستخدام رمز المصدر المقدم، يمكن للمطورين بسهولة تحسين مستندات PDF، مما يؤدي إلى أحجام ملفات أصغر وتحسين أداء التطبيق.

### الأسئلة الشائعة

#### س: كيف يفيد تحسين حجم ملف مستند PDF المطورين؟

ج: إن تحسين حجم ملف مستند PDF يفيد المطورين عن طريق تقليل حجم ملفات PDF التي تم إنشاؤها بواسطة تطبيقاتهم. تؤدي أحجام الملفات الأصغر إلى أوقات تحميل أسرع وتحسين الأداء، خاصة عند مشاركة ملفات PDF أو توزيعها عبر الويب أو عبر البريد الإلكتروني.

#### س: ما هي خيارات التحسين التي يمكن للمطورين تعيينها باستخدام Aspose.PDF لـ .NET؟

ج: يوفر Aspose.PDF for .NET للمطورين خيارات تحسين متنوعة لتخصيص عملية تقليل حجم ملف مستند PDF. تتضمن بعض الخيارات المتاحة إزالة التدفقات المكررة وإزالة الكائنات غير المستخدمة وإزالة التدفقات غير المستخدمة وضغط الصور مع التحكم في جودة الصورة.

#### س: هل يستطيع المطورون تحقيق التوازن بين تقليل حجم الملف وجودة الصورة عند تحسين مستندات PDF؟

ج: نعم، يتمتع المطورون بالتحكم في خيارات ضغط الصورة، مثل ضبط جودة الصورة. يمكنهم اختيار التوازن بين تقليل حجم الملف وجودة الصورة بناءً على متطلباتهم المحددة.