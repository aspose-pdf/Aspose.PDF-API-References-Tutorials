---
title: صور الانكماش السريع
linktitle: صور الانكماش السريع
second_title: Aspose.PDF لمرجع .NET API
description: تقليل حجم الصور في ملف PDF بسرعة باستخدام Aspose.PDF for .NET.
type: docs
weight: 130
url: /ar/net/programming-with-images/fast-shrink-images/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية تقليل حجم الصور بسرعة في ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تهيئة الوقت

قبل أن نبدأ ، سنقوم بتهيئة الوقت لقياس أداء الضغط. أضف الكود التالي لتسجيل وقت البدء:

```csharp
var time = DateTime.Now.Ticks;
```

## الخطوة 2: تحديد دليل المستند

 تأكد من تعيين دليل المستند الصحيح. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## الخطوة 4: تهيئة خيارات التحسين

في هذه الخطوة ، سنقوم بتهيئة خيارات التحسين لضغط الصور. قم بإنشاء مثيل لـ`OptimizationOptions` وحدد الخيارات المناسبة. في هذا المثال ، نقوم بتمكين ضغط الصور ، وضبط جودة الصورة على 75 ، واستخدام إصدار الضغط السريع.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## الخطوة 5: تحسين مستند PDF

 في هذه الخطوة ، سنقوم بتحسين مستند PDF باستخدام خيارات التحسين المحددة مسبقًا. اتصل ب`OptimizeResources` طريقة`pdfDocument` كائن وتمرير خيارات التحسين.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 6: احفظ مستند PDF المحدث

 احفظ مستند PDF المحدث باستخدام ملف`Save` طريقة`pdfDocument` هدف. حدد مسار الإخراج لملف PDF.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### عينة من التعليمات البرمجية المصدر لـ Fast Shrink Images باستخدام Aspose.PDF لـ .NET 
```csharp
// تهيئة الوقت
var time = DateTime.Now.Ticks;
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// قم بتعيين خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// تعيين خيار ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// قم بتعيين إصدار ضغط Imagae على السرعة
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد قمت بسرعة بتقليل حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ ملف PDF المحسن في الدليل المحدد. يمكنك الآن استخدام ملف PDF هذا مع صور مخفضة للحصول على احتياجات تخزين أو مشاركة أكثر كفاءة.

### التعليمات

#### س: لماذا أرغب في تقليل حجم الصور بسرعة في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يساعد تقليل حجم الصور في ملف PDF بسرعة في تحسين الملف للتخزين أو المشاركة أو النقل ، مما يؤدي إلى تحسين الأداء وتقليل استهلاك الموارد.

#### س: ما هي المزايا التي يوفرها ضغط الصور في مستند PDF؟

ج: يساعد ضغط الصور في مستند PDF على تقليل حجم الملف مع الحفاظ على جودة الصورة المقبولة ، مما يؤدي إلى أوقات تحميل أسرع ، وتقليل متطلبات التخزين ، وتحسين كفاءة نقل البيانات.

#### س: كيف يسهل Aspose.PDF for .NET تقليل حجم الصورة بسرعة في ملف PDF؟

ج: يوفر Aspose.PDF for .NET عملية مبسطة لفتح مستند PDF وتطبيق خيارات ضغط الصور وحفظ ملف PDF المحسن بأحجام صور أقل.

####  س: ما اهمية ال`OptimizationOptions` class in fast image size reduction?

 ج: إن`OptimizationOptions`تمكنك class من تحديد إعدادات تحسين متنوعة ، بما في ذلك خيارات ضغط الصور ، لتقليل حجم الصور بشكل فعال داخل مستند PDF.

#### س: هل يمكنني تخصيص إعدادات ضغط الصورة للتحكم في التوازن بين حجم الملف وجودة الصورة؟

ج: نعم ، يمكنك تخصيص إعدادات ضغط الصورة عن طريق ضبط المعلمات مثل جودة الصورة وإصدار الضغط لتحقيق التوازن المطلوب بين حجم الملف ومظهر الصورة.

####  س: كيف يعمل ملف`pdfDocument.OptimizeResources` method work to reduce image sizes?

 ج: إن`OptimizeResources` الطريقة تحلل وثيقة PDF وتطبق خيارات التحسين المحددة ، بما في ذلك إعدادات ضغط الصورة ، لتقليل حجم الصور والموارد الأخرى.

#### س: هل من الممكن تطبيق تصغير سريع لحجم الصورة على نطاق معين من الصفحات داخل مستند PDF؟

 ج: إن`OptimizeResources` تطبق الطريقة خيارات التحسين على مستند PDF بأكمله. إذا كنت ترغب في تطبيق التحسين على صفحات معينة ، فأنت بحاجة إلى استخراج تلك الصفحات في مستند جديد قبل التحسين.

#### س: ما هي بعض السيناريوهات التي يمكن أن يكون فيها تقليل حجم الصورة السريع مفيدًا؟

ج: يمكن أن يكون تقليل حجم الصورة السريع مفيدًا عند إعداد ملفات PDF للتوزيع عبر الإنترنت أو مرفقات البريد الإلكتروني أو الأرشفة أو عند العمل مع مستندات كبيرة تحتوي على العديد من الصور.

#### س: هل يؤثر تقليل أحجام الصور على الجودة المرئية للصور في مستند PDF؟

ج: إن تقليل أحجام الصور من خلال الضغط يمكن أن يؤثر على جودة الصورة إلى حد ما. من المهم إيجاد توازن بين تقليل الحجم وجودة الصورة المقبولة.

#### س: كيف يمكنني قياس أداء عملية تصغير حجم الصورة السريعة؟

 ج: يمكنك قياس الأداء عن طريق تسجيل وقت البدء باستخدام ملف`DateTime.Now.Ticks` قبل عملية التحسين وحساب الوقت المنقضي بعد العملية.