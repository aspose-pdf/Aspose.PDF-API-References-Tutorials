---
title: تقليص الصور بسرعة
linktitle: تقليص الصور بسرعة
second_title: Aspose.PDF لمرجع .NET API
description: قم بتقليل حجم الصور في ملف PDF بسرعة باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 130
url: /ar/net/programming-with-images/fast-shrink-images/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية تقليل حجم الصور بسرعة في ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من أنك قمت بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تهيئة الوقت

قبل أن نبدأ، سنقوم بتهيئة الوقت لقياس أداء الضغط. أضف الكود التالي لتسجيل وقت البدء:

```csharp
var time = DateTime.Now.Ticks;
```

## الخطوة 2: تحديد دليل المستند

 تأكد من تعيين دليل المستند الصحيح. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود الذي يحتوي على المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

في هذه الخطوة، سنقوم بفتح مستند PDF باستخدام الملف`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ وتمرير المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## الخطوة 4: تهيئة خيارات التحسين

في هذه الخطوة، سنقوم بتهيئة خيارات التحسين لضغط الصور. إنشاء مثيل ل`OptimizationOptions` وضبط الخيارات المناسبة. في هذا المثال، نقوم بتمكين ضغط الصور، وضبط جودة الصورة على 75، واستخدام إصدار الضغط السريع.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## الخطوة 5: تحسين مستند PDF

 في هذه الخطوة، سنقوم بتحسين مستند PDF باستخدام خيارات التحسين المحددة مسبقًا. اتصل ب`OptimizeResources` طريقة`pdfDocument` الكائن وتمرير خيارات التحسين.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 6: احفظ مستند PDF المحدث

 احفظ مستند PDF المحدث باستخدام الملف`Save` طريقة`pdfDocument` هدف. حدد مسار الإخراج لملف PDF.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لصور التقليص السريع باستخدام Aspose.PDF لـ .NET 
```csharp
// تهيئة الوقت
var time = DateTime.Now.Ticks;
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// تهيئة خيارات التحسين
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// اضبط خيار ضغط الصور
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// ضبط خيار جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// اضبط إصدار ضغط الصور على الصيام
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد قمت بسرعة بتقليل حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ ملف PDF الأمثل في الدليل المحدد. يمكنك الآن استخدام ملف PDF هذا مع صور مصغرة لتلبية احتياجات التخزين أو المشاركة الأكثر كفاءة.

### الأسئلة الشائعة

#### س: لماذا أرغب في تقليل حجم الصور بسرعة في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يساعد تقليل حجم الصور في ملف PDF بسرعة في تحسين الملف للتخزين أو المشاركة أو النقل، مما يؤدي إلى تحسين الأداء وتقليل استهلاك الموارد.

#### س: ما هي المزايا التي يقدمها ضغط الصور في مستند PDF؟

ج: يساعد ضغط الصور في مستند PDF على تقليل حجم الملف مع الحفاظ على جودة الصورة المقبولة، مما يؤدي إلى أوقات تحميل أسرع وتقليل متطلبات التخزين وتحسين كفاءة نقل البيانات.

#### س: كيف يسهل Aspose.PDF for .NET تقليل حجم الصورة بسرعة في ملف PDF؟

ج: يوفر Aspose.PDF for .NET عملية مبسطة لفتح مستند PDF، وتطبيق خيارات ضغط الصور، وحفظ ملف PDF المُحسّن بأحجام صور منخفضة.

####  س: ما أهمية`OptimizationOptions` class in fast image size reduction?

 ج: ال`OptimizationOptions`يتيح لك class إمكانية تحديد إعدادات التحسين المختلفة، بما في ذلك خيارات ضغط الصور، لتقليل حجم الصور بشكل فعال داخل مستند PDF.

#### س: هل يمكنني تخصيص إعدادات ضغط الصور للتحكم في التوازن بين حجم الملف وجودة الصورة؟

ج: نعم، يمكنك تخصيص إعدادات ضغط الصورة عن طريق ضبط المعلمات مثل جودة الصورة وإصدار الضغط لتحقيق التوازن المطلوب بين حجم الملف ومظهر الصورة.

####  س: كيف`pdfDocument.OptimizeResources` method work to reduce image sizes?

 ج: ال`OptimizeResources` تقوم هذه الطريقة بتحليل مستند PDF وتطبيق خيارات التحسين المحددة، بما في ذلك إعدادات ضغط الصور، لتقليل حجم الصور والموارد الأخرى.

#### س: هل من الممكن تطبيق تقليل سريع لحجم الصورة على نطاق محدد من الصفحات داخل مستند PDF؟

 ج: ال`OptimizeResources` تطبق الطريقة خيارات التحسين على مستند PDF بأكمله. إذا كنت تريد تطبيق التحسين على صفحات معينة، فستحتاج إلى استخراج تلك الصفحات في مستند جديد قبل التحسين.

#### س: ما هي بعض السيناريوهات التي يمكن أن يكون فيها تقليل حجم الصورة بسرعة مفيدًا؟

ج: يمكن أن يكون تقليل حجم الصورة بسرعة مفيدًا عند إعداد ملفات PDF للتوزيع عبر الإنترنت، أو مرفقات البريد الإلكتروني، أو الأرشفة، أو عند العمل مع مستندات كبيرة تحتوي على العديد من الصور.

#### س: هل يؤثر تقليل أحجام الصور على الجودة المرئية للصور في مستند PDF؟

ج: يمكن أن يؤثر تقليل أحجام الصور من خلال الضغط على جودة الصورة إلى حد ما. من المهم إيجاد توازن بين تقليل الحجم وجودة الصورة المقبولة.

#### س: كيف يمكنني قياس أداء عملية تقليل حجم الصورة السريعة؟

 ج: يمكنك قياس الأداء عن طريق تسجيل وقت البدء باستخدام`DateTime.Now.Ticks` الطريقة قبل عملية التحسين وحساب الوقت المنقضي بعد العملية.