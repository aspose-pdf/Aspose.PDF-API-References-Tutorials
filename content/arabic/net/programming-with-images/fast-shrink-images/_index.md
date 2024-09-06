---
title: صور سريعة الانكماش
linktitle: صور سريعة الانكماش
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: قم بتقليل حجم الصور بسرعة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 130
url: /ar/net/programming-with-images/fast-shrink-images/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية تقليل حجم الصور بسرعة في ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من إعداد البيئة الخاصة بك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تهيئة الوقت

قبل أن نبدأ، سنقوم بتهيئة الوقت لقياس أداء الضغط. أضف الكود التالي لتسجيل وقت البدء:

```csharp
var time = DateTime.Now.Ticks;
```

## الخطوة 2: تحديد دليل المستند

 تأكد من تعيين دليل المستند الصحيح. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

 في هذه الخطوة سوف نقوم بفتح مستند PDF باستخدام`Document` فئة Aspose.PDF. استخدم`Document` منشئ ومرر المسار إلى مستند PDF.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## الخطوة 4: تهيئة خيارات التحسين

 في هذه الخطوة، سنقوم بتهيئة خيارات التحسين لضغط الصور. قم بإنشاء مثيل لـ`OptimizationOptions` وضبط الخيارات المناسبة. في هذا المثال، نقوم بتمكين ضغط الصورة، وضبط جودة الصورة على 75، واستخدام إصدار الضغط السريع.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## الخطوة 5: تحسين مستند PDF

في هذه الخطوة، سنقوم بتحسين مستند PDF باستخدام خيارات التحسين المحددة مسبقًا.`OptimizeResources` طريقة`pdfDocument` الكائن وتمرير خيارات التحسين.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 6: احفظ مستند PDF المحدث

 احفظ مستند PDF المحدث باستخدام`Save` طريقة`pdfDocument` الكائن. حدد مسار الإخراج لملف PDF.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### عينة من كود المصدر لصور الانكماش السريع باستخدام Aspose.PDF لـ .NET 
```csharp
// وقت التهيئة
var time = DateTime.Now.Ticks;
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// تهيئة خيارات التحسين
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// تعيين خيار ضغط الصور
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// تعيين خيار جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// ضبط إصدار ضغط الصور على سريع
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

تهانينا! لقد قمت بسرعة بتقليل حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ ملف PDF المحسن في الدليل المحدد. يمكنك الآن استخدام ملف PDF هذا مع الصور المصغرة لتلبية احتياجات التخزين أو المشاركة الأكثر كفاءة.

### الأسئلة الشائعة

#### س: لماذا أرغب في تقليل حجم الصور بسرعة في ملف PDF باستخدام Aspose.PDF لـ .NET؟

أ: إن تقليل حجم الصور بسرعة في ملف PDF يمكن أن يساعد في تحسين الملف للتخزين أو المشاركة أو النقل، مما يؤدي إلى تحسين الأداء وتقليل استهلاك الموارد.

#### س: ما هي المزايا التي توفرها عملية ضغط الصور في مستند PDF؟

أ: يساعد ضغط الصور في مستند PDF على تقليل حجم الملف مع الحفاظ على جودة الصورة المقبولة، مما يؤدي إلى أوقات تحميل أسرع ومتطلبات تخزين أقل وتحسين كفاءة نقل البيانات.

#### س: كيف يعمل Aspose.PDF for .NET على تسهيل تقليل حجم الصورة بسرعة في ملف PDF؟

ج: يوفر Aspose.PDF لـ .NET عملية مبسطة لفتح مستند PDF وتطبيق خيارات ضغط الصور وحفظ ملف PDF المحسن مع أحجام صور مخفضة.

####  س: ما هي أهمية`OptimizationOptions` class in fast image size reduction?

 أ: ال`OptimizationOptions` تتيح لك الفئة تحديد إعدادات تحسين مختلفة، بما في ذلك خيارات ضغط الصور، لتقليل حجم الصور داخل مستند PDF بشكل فعال.

#### س: هل يمكنني تخصيص إعدادات ضغط الصورة للتحكم في التوازن بين حجم الملف وجودة الصورة؟

ج: نعم، يمكنك تخصيص إعدادات ضغط الصورة عن طريق ضبط المعلمات مثل جودة الصورة وإصدار الضغط لتحقيق التوازن المطلوب بين حجم الملف ومظهر الصورة.

####  س: كيف يتم ذلك؟`pdfDocument.OptimizeResources` method work to reduce image sizes?

 أ: ال`OptimizeResources` تقوم الطريقة بتحليل مستند PDF وتطبيق خيارات التحسين المحددة، بما في ذلك إعدادات ضغط الصور، لتقليل حجم الصور والموارد الأخرى.

#### س: هل من الممكن تطبيق تقليل حجم الصورة بسرعة على نطاق محدد من الصفحات داخل مستند PDF؟

 أ: ال`OptimizeResources` تطبق الطريقة خيارات التحسين على مستند PDF بأكمله. إذا كنت تريد تطبيق التحسين على صفحات معينة، فيتعين عليك استخراج تلك الصفحات في مستند جديد قبل التحسين.

#### س: ما هي بعض السيناريوهات التي قد يكون فيها تقليل حجم الصورة بسرعة مفيدًا؟

يمكن أن يكون تقليل حجم الصورة بسرعة مفيدًا عند إعداد ملفات PDF للتوزيع عبر الإنترنت، أو مرفقات البريد الإلكتروني، أو الأرشفة، أو عند العمل مع مستندات كبيرة تحتوي على العديد من الصور.

#### س: هل يؤثر تقليل حجم الصور على الجودة المرئية للصور في مستند PDF؟

ج: قد يؤثر تقليل أحجام الصور من خلال الضغط على جودة الصورة إلى حد ما. من المهم إيجاد توازن بين تقليل الحجم وجودة الصورة المقبولة.

#### س: كيف يمكنني قياس أداء عملية تقليل حجم الصورة بسرعة؟

 أ: يمكنك قياس الأداء عن طريق تسجيل وقت البدء باستخدام`DateTime.Now.Ticks` الطريقة قبل عملية التحسين وحساب الوقت المنقضي بعد العملية.