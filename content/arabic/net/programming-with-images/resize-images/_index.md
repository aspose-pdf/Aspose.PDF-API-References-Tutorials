---
title: تغيير حجم الصور في ملف PDF
linktitle: تغيير حجم الصور في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتغيير حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 250
url: /ar/net/programming-with-images/resize-images/
---
في هذا البرنامج التعليمي، سنرشدك إلى كيفية تغيير حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. اتبع هذه الخطوات لتنفيذ هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت وتكوين Visual Studio أو أي بيئة تطوير أخرى.
- معرفة أساسية بلغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تحميل وثيقة PDF

للبدء، استخدم الكود التالي لتحميل مستند PDF:

```csharp
// تهيئة الوقت
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

تأكد من توفير المسار الصحيح لمستند PDF الخاص بك.

## الخطوة 2: تهيئة خيارات التحسين

قبل تغيير حجم الصور، نحتاج إلى تهيئة خيارات التحسين. استخدم الكود التالي:

```csharp
// تهيئة خيارات التحسين
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// تفعيل خيار ضغط الصور
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// ضبط جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// قم بتنشيط خيار تغيير حجم الصور
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// تعيين الحد الأقصى للدقة
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

يمكنك ضبط إعدادات التحسين وفقًا لاحتياجاتك.

## الخطوة 3: تحسين وثيقة PDF

سنقوم الآن بتحسين مستند PDF باستخدام خيارات التحسين التي حددناها. استخدم الكود التالي:

```csharp
// قم بتحسين مستند PDF باستخدام خيارات التحسين
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

تأكد من توفير المسار واسم الملف المطلوبين لمستند PDF المحدث.

### نموذج التعليمات البرمجية المصدر لتغيير حجم الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// تهيئة الوقت
var time = DateTime.Now.Ticks;
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// تهيئة خيارات التحسين
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// اضبط خيار ضغط الصور
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// ضبط خيار جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// اضبط خيار تغيير حجم الصورة
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// اضبط خيار MaxResolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد نجحت في تغيير حجم الصور في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لتغيير حجم الصور في ملفات PDF.

### الأسئلة الشائعة

#### س: لماذا أرغب في تغيير حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يساعد تغيير حجم الصور في ملف PDF في تحسين حجم المستند وتحسين أدائه. يكون هذا مفيدًا بشكل خاص عندما تريد تقليل حجم الملف لتسهيل المشاركة أو تحميل مستندات PDF بشكل أسرع.

#### س: كيف يؤثر تغيير حجم الصورة على جودة الصور في مستند PDF؟

 ج: يتضمن تغيير حجم الصورة تقليل أبعاد الصور ودقتها، مما قد يؤدي إلى حجم ملف أصغر. في حين أن هذا يمكن أن يقلل من جودة الصورة إلى حد ما، فإن`ImageQuality` معامل (`optimizeOptions.ImageCompressionOptions.ImageQuality`) يسمح لك بالتحكم في التوازن بين حجم الصورة وجودتها.

####  س: ما هو الغرض من`MaxResolution` option in the optimization settings?

 ج: ال`MaxResolution` خيار (`optimizeOptions.ImageCompressionOptions.MaxResolution`) يضبط الحد الأقصى لدقة الصور في مستند PDF. سيتم تصغير الصور ذات الدقة الأعلى إلى هذه القيمة المحددة أثناء عملية التحسين.

#### س: كيف يمكنني ضبط إعدادات التحسين لتغيير حجم الصورة؟

 ج: في الكود المقدم، يمكنك تعديل قيم خيارات التحسين لتحقيق تغيير حجم الصورة وضغطها المطلوب. على سبيل المثال، يمكنك تغيير`ImageQuality` و`MaxResolution` القيم لتخصيص عملية التحسين وفقًا لمتطلباتك.

#### س: هل يمكنني تغيير حجم صور معينة بشكل انتقائي داخل مستند PDF؟

ج: يعمل الكود المقدم على تحسين جميع الصور في مستند PDF باستخدام نفس إعدادات التحسين. إذا كنت تريد تغيير حجم صور معينة بشكل انتقائي، فقد تحتاج إلى تعديل التعليمات البرمجية لاستهداف تلك الصور بشكل فردي.

####  س: كيف`pdfDocument.OptimizeResources` method work in resizing images?

 ج: ال`OptimizeResources` تطبق الطريقة خيارات التحسين المحددة على مستند PDF، بما في ذلك تغيير حجم الصورة وضغطها. فهو يساعد على تقليل حجم ملف مستند PDF عن طريق تطبيق إعدادات التحسين المحددة على موارده.

#### س: هل من الممكن معاينة الصور التي تم تغيير حجمها قبل حفظ مستند PDF؟

ج: يعمل الكود المقدم مباشرة على تحسين مستند PDF وحفظه بصور تم تغيير حجمها. إذا كنت تريد معاينة الصور التي تم تغيير حجمها قبل الحفظ، فقد تحتاج إلى تعديل الكود لإنشاء صور المعاينة أيضًا.

#### س: كيف يمكنني دمج طريقة تغيير حجم الصورة هذه في مشاريعي الخاصة؟

ج: لدمج هذه الطريقة في مشاريعك، اتبع الخطوات الموضحة وقم بتعديل الكود حسب الحاجة. يمكنك أتمتة عملية تغيير حجم الصور في مستندات PDF من خلال دمج هذا الرمز في التطبيق الخاص بك.

#### س: هل توفر مكتبة Aspose.PDF لـ .NET أي إمكانات أخرى لتحسين ملفات PDF؟

ج: نعم، توفر مكتبة Aspose.PDF لـ .NET خيارات تحسين متعددة تتجاوز تغيير حجم الصورة، مثل تحسين الخط والنص، وإزالة الكائنات غير المستخدمة، وتقليل البيانات الزائدة عن الحاجة. يمكنك استكشاف وثائق المكتبة وأمثلتها لاكتشاف المجموعة الكاملة من ميزات التحسين.