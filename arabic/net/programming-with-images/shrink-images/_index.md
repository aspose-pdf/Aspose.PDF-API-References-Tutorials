---
title: تقليص الصور في ملف PDF
linktitle: تقليص الصور في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل تفصيلي خطوة بخطوة لتقليل حجم الصور في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 280
url: /ar/net/programming-with-images/shrink-images/
---
في هذا البرنامج التعليمي ، سنخبرك بكيفية تقليل حجم الصور في ملف PDF باستخدام Aspose.PDF for .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تحميل مستند PDF

للبدء ، استخدم الكود التالي لتحميل مستند PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

تأكد من توفير المسار الصحيح لوثيقة PDF الخاصة بك.

## الخطوة 2: تهيئة خيارات التحسين

بعد ذلك ، سنقوم بتهيئة خيارات التحسين لتقليل حجم الصور. استخدم الكود التالي:

```csharp
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// قم بتنشيط خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// ضبط جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

يمكنك ضبط إعدادات التحسين وفقًا لاحتياجاتك.

## الخطوة 3: تحسين مستند PDF

سنقوم الآن بتحسين مستند PDF عن طريق تقليل حجم الصور. استخدم الكود التالي:

```csharp
// قم بتحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

تأكد من توفير المسار المطلوب واسم الملف لمستند PDF المحدث.

### عينة من التعليمات البرمجية المصدر لـ Shrink Images باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// قم بتعيين خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// تعيين خيار ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد نجحت في تقليل حجم الصور في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لتحسين حجم الصور في ملفات PDF.

### التعليمات

#### س: لماذا أرغب في تقليل حجم الصور في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: يساعد تقليل حجم الصور في مستند PDF على تحسين الحجم الكلي للملف ، مما يسهل مشاركة المستند وتخزينه وتوزيعه. يمكنه أيضًا تحسين أداء تحميل وعرض المستند.

#### س: كيف تعمل عملية تقليل حجم الصور في مستند PDF؟

ج: تتضمن العملية تهيئة خيارات التحسين التي تتحكم في الضغط وإعدادات الجودة للصور في ملف PDF. يتم بعد ذلك تطبيق هذه الخيارات على مستند PDF ، والذي يضغط الصور بناءً على الإعدادات المحددة.

#### س: ما هي إعدادات التحسين الرئيسية التي يمكن تعديلها لتقليل حجم الصورة في ملف PDF؟

 ج: تتضمن الإعدادات الرئيسية تفعيل ملف`CompressImages` الخيار وضبط`ImageQuality` قيمة. ال`CompressImages` يتحكم الخيار في ما إذا كان يجب ضغط الصور أم لا`ImageQuality` تحدد القيمة مستوى ضغط الصورة.

#### س: هل يمكنني تخصيص مستوى ضغط الصورة بشكل أكبر بناءً على متطلبات محددة؟

 ج: نعم ، يمكنك ضبط ملف`ImageQuality` قيمة لتخصيص مستوى ضغط الصورة. تؤدي القيمة الأعلى (على سبيل المثال ، 75) إلى جودة صورة أفضل ولكن حجم ملف أكبر ، بينما تؤدي القيمة الأقل (على سبيل المثال ، 25) إلى تقليل جودة الصورة ولكن ينتج عنها حجم ملف أصغر.

#### س: هل هناك أي قيود أو اعتبارات عند تقليل حجم الصورة في مستند PDF؟

ج: في حين أن تقليل حجم الصورة يمكن أن يقلل بشكل كبير من الحجم الكلي لملف PDF ، فإن تقليل جودة الصورة بشكل مفرط قد يؤدي إلى تدهور تفاصيل الصورة. من المهم تحقيق التوازن بين حجم الملف وجودة الصورة بناءً على احتياجاتك الخاصة.

#### س: كيف تؤثر هذه الطريقة على المحتوى الآخر في مستند PDF ، مثل النص أو الرسومات المتجهة؟

ج: تركز هذه الطريقة بشكل أساسي على تحسين حجم الصور. لا يتأثر النص والرسومات المتجهة بشكل عام بعملية تحسين الصورة ، لذلك تظل جودة هذه العناصر غير متأثرة.

#### س: هل يمكنني تطبيق تقليل حجم الصورة بشكل انتقائي على صور معينة داخل مستند PDF؟

ج: كما هو موضح في الكود المقدم ، يتم تطبيق خيارات التحسين على مستند PDF بأكمله. إذا كنت تريد تطبيق تقليل حجم الصورة بشكل انتقائي على صور معينة ، فستحتاج إلى ضبط الكود لاستهداف تلك الصور فقط.

####  س: هل هناك نطاق موصى به لـ`ImageQuality` value to balance between image size and quality?

 ج: الموصى به`ImageQuality` تعتمد القيمة على المتطلبات المحددة لمشروعك. بشكل عام ، توفر القيم بين 50 و 75 توازنًا جيدًا بين جودة الصورة وتقليل حجم الملف. يمكنك تجربة قيم مختلفة للعثور على الإعداد الأمثل لاحتياجاتك.