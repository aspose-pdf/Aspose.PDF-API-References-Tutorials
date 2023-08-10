---
title: تغيير حجم الصور في ملف PDF
linktitle: تغيير حجم الصور في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتغيير حجم الصور في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 250
url: /ar/net/programming-with-images/resize-images/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تغيير حجم الصور في ملف PDF باستخدام Aspose.PDF for .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تحميل مستند PDF

للبدء ، استخدم الكود التالي لتحميل مستند PDF:

```csharp
// تهيئة الوقت
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

تأكد من توفير المسار الصحيح لوثيقة PDF الخاصة بك.

## الخطوة 2: تهيئة خيارات التحسين

قبل تغيير حجم الصور ، نحتاج إلى تهيئة خيارات التحسين. استخدم الكود التالي:

```csharp
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// قم بتنشيط خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// ضبط جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// قم بتنشيط خيار ResizeImages
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// تعيين الدقة القصوى
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

يمكنك ضبط إعدادات التحسين وفقًا لاحتياجاتك.

## الخطوة 3: تحسين مستند PDF

سنقوم الآن بتحسين مستند PDF باستخدام خيارات التحسين التي حددناها. استخدم الكود التالي:

```csharp
// قم بتحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

تأكد من توفير المسار المطلوب واسم الملف لمستند PDF المحدث.

### نموذج التعليمات البرمجية المصدر لتغيير حجم الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// تهيئة الوقت
var time = DateTime.Now.Ticks;
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// قم بتعيين خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// تعيين خيار ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// تعيين خيار ResizeImage
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// تعيين خيار MaxResolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد نجحت في تغيير حجم الصور في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لتغيير حجم الصور في ملفات PDF.

### التعليمات

#### س: لماذا أرغب في تغيير حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يساعد تغيير حجم الصور في ملف PDF في تحسين حجم المستند وتحسين أدائه. إنه مفيد بشكل خاص عندما تريد تقليل حجم الملف لتسهيل مشاركة مستندات PDF أو تحميلها بشكل أسرع.

#### س: كيف يؤثر تغيير حجم الصورة على جودة الصور في مستند PDF؟

 ج: يتضمن تغيير حجم الصورة تقليل أبعاد ودقة الصور ، مما قد ينتج عنه حجم ملف أصغر. في حين أن هذا يمكن أن يقلل من جودة الصورة إلى حد ما ، فإن`ImageQuality` معامل (`optimizeOptions.ImageCompressionOptions.ImageQuality`) يسمح لك بالتحكم في التوازن بين حجم الصورة وجودتها.

####  س: ما هو الغرض من`MaxResolution` option in the optimization settings?

 ج: إن`MaxResolution` خيار (`optimizeOptions.ImageCompressionOptions.MaxResolution`) يضبط أقصى دقة للصور في وثيقة PDF. سيتم تصغير الصور ذات الدقة العالية إلى هذه القيمة المحددة أثناء عملية التحسين.

#### س: كيف أقوم بضبط إعدادات التحسين لتغيير حجم الصورة؟

 ج: في الكود المقدم ، يمكنك تعديل قيم خيارات التحسين لتحقيق الحجم المطلوب للصورة وضغطها. على سبيل المثال ، يمكنك تغيير ملف`ImageQuality` و`MaxResolution` القيم لتخصيص عملية التحسين وفقًا لمتطلباتك.

#### س: هل يمكنني تغيير حجم صور محددة بشكل انتقائي داخل مستند PDF؟

ج: يعمل الكود المقدم على تحسين جميع الصور في مستند PDF باستخدام نفس إعدادات التحسين. إذا كنت ترغب في تغيير حجم صور معينة بشكل انتقائي ، فقد تحتاج إلى تعديل الكود لاستهداف تلك الصور بشكل فردي.

####  س: كيف يعمل ملف`pdfDocument.OptimizeResources` method work in resizing images?

 ج: إن`OptimizeResources` يطبق الأسلوب خيارات التحسين المحددة على مستند PDF ، بما في ذلك تغيير حجم الصورة وضغطها. يساعد في تقليل حجم ملف مستند PDF من خلال تطبيق إعدادات التحسين المحددة على موارده.

#### س: هل من الممكن معاينة الصور التي تم تغيير حجمها قبل حفظ مستند PDF؟

ج: يعمل الكود المقدم مباشرة على تحسين وحفظ مستند PDF بالصور التي تم تغيير حجمها. إذا كنت ترغب في معاينة الصور التي تم تغيير حجمها قبل الحفظ ، فقد تحتاج إلى تعديل الكود لإنشاء صور المعاينة أيضًا.

#### س: كيف يمكنني دمج طريقة تغيير حجم الصورة هذه في مشاريعي الخاصة؟

ج: لدمج هذه الطريقة في مشاريعك ، اتبع الخطوات الموضحة وقم بتعديل الكود حسب الحاجة. يمكنك أتمتة عملية تغيير حجم الصور في مستندات PDF من خلال دمج هذا الرمز في التطبيق الخاص بك.

#### س: هل توفر مكتبة Aspose.PDF for .NET أية إمكانيات أخرى لتحسين PDF؟

ج: نعم ، توفر مكتبة Aspose.PDF for .NET خيارات تحسين متنوعة تتجاوز تغيير حجم الصورة ، مثل تحسين الخط والنص ، وإزالة الكائنات غير المستخدمة ، وتقليل البيانات الزائدة عن الحاجة. يمكنك استكشاف وثائق المكتبة وأمثلة لاكتشاف مجموعة كاملة من ميزات التحسين.