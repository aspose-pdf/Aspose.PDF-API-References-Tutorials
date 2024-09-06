---
title: تغيير حجم الصور في ملف PDF
linktitle: تغيير حجم الصور في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لتغيير حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 250
url: /ar/net/programming-with-images/resize-images/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية تغيير حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. اتبع الخطوات التالية لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت وتكوين Visual Studio أو أي بيئة تطوير أخرى.
- المعرفة الأساسية للغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي.

## الخطوة 1: تحميل مستند PDF

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

// قم بتفعيل خيار ضغط الصور
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// ضبط جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// قم بتفعيل خيار تغيير حجم الصور
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// تعيين الحد الأقصى للدقة
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

يمكنك ضبط إعدادات التحسين وفقًا لاحتياجاتك.

## الخطوة 3: تحسين مستند PDF

الآن سنقوم بتحسين مستند PDF باستخدام خيارات التحسين التي حددناها. استخدم الكود التالي:

```csharp
// تحسين مستند PDF باستخدام خيارات التحسين
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

تأكد من توفير المسار واسم الملف المطلوبين لمستند PDF المحدث.

### عينة من كود المصدر لتغيير حجم الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// وقت التهيئة
var time = DateTime.Now.Ticks;
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// تهيئة خيارات التحسين
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// تعيين خيار ضغط الصور
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// تعيين خيار جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// تعيين خيار تغيير حجم الصورة
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// تعيين خيار الحد الأقصى للدقة
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهانينا! لقد نجحت في تغيير حجم الصور في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لتغيير حجم الصور في ملفات PDF.

### الأسئلة الشائعة

#### س: لماذا أرغب في تغيير حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يساعد تغيير حجم الصور في ملف PDF في تحسين حجم المستند وتحسين أدائه. وهو مفيد بشكل خاص عندما تريد تقليل حجم الملف لتسهيل المشاركة أو تحميل مستندات PDF بشكل أسرع.

#### س: كيف يؤثر تغيير حجم الصورة على جودة الصور في مستند PDF؟

 ج: تتضمن عملية تغيير حجم الصورة تقليل أبعاد الصور ودقتها، مما قد يؤدي إلى تقليل حجم الملف. وفي حين أن هذا قد يقلل من جودة الصورة إلى حد ما،`ImageQuality` المعلمة (`optimizeOptions.ImageCompressionOptions.ImageQuality`) يسمح لك بالتحكم في التوازن بين حجم الصورة وجودتها.

####  س: ما هو الغرض من`MaxResolution` option in the optimization settings?

 أ: ال`MaxResolution` خيار (`optimizeOptions.ImageCompressionOptions.MaxResolution`) يحدد الدقة القصوى للصور في مستند PDF. سيتم تصغير الصور ذات الدقة الأعلى إلى هذه القيمة المحددة أثناء عملية التحسين.

#### س: كيف أقوم بتعديل إعدادات التحسين لتغيير حجم الصورة؟

 ج: في الكود المقدم، يمكنك تعديل قيم خيارات التحسين لتحقيق تغيير حجم الصورة وضغطها بالشكل المطلوب. على سبيل المثال، يمكنك تغيير`ImageQuality` و`MaxResolution` القيم لتخصيص عملية التحسين وفقًا لمتطلباتك.

#### س: هل يمكنني تغيير حجم صور محددة بشكل انتقائي ضمن مستند PDF؟

ج: يعمل الكود المقدم على تحسين جميع الصور في مستند PDF باستخدام نفس إعدادات التحسين. إذا كنت تريد تغيير حجم صور معينة بشكل انتقائي، فقد تحتاج إلى تعديل الكود لاستهداف تلك الصور بشكل فردي.

####  س: كيف يتم ذلك؟`pdfDocument.OptimizeResources` method work in resizing images?

 أ: ال`OptimizeResources` تطبق الطريقة خيارات التحسين المحددة على مستند PDF، بما في ذلك تغيير حجم الصورة وضغطها. وتساعد في تقليل حجم ملف مستند PDF من خلال تطبيق إعدادات التحسين المحددة على موارده.

#### س: هل من الممكن معاينة الصور التي تم تغيير حجمها قبل حفظ مستند PDF؟

ج: يقوم الكود المقدم بتحسين وحفظ مستند PDF مباشرةً مع الصور التي تم تغيير حجمها. إذا كنت تريد معاينة الصور التي تم تغيير حجمها قبل الحفظ، فقد تحتاج إلى تعديل الكود لإنشاء صور معاينة أيضًا.

#### س: كيف يمكنني دمج طريقة تغيير حجم الصورة هذه في مشاريعي الخاصة؟

ج: لدمج هذه الطريقة في مشاريعك، اتبع الخطوات الموضحة وقم بتعديل الكود حسب الحاجة. يمكنك أتمتة عملية تغيير حجم الصور في مستندات PDF من خلال دمج هذا الكود في تطبيقك.

#### س: هل توفر مكتبة Aspose.PDF for .NET أي إمكانيات أخرى لتحسين PDF؟

ج: نعم، توفر مكتبة Aspose.PDF for .NET خيارات تحسين متنوعة تتجاوز تغيير حجم الصورة، مثل تحسين الخط والنص، وإزالة الكائنات غير المستخدمة، والحد من البيانات المكررة. يمكنك استكشاف وثائق المكتبة وأمثلتها لاكتشاف مجموعتها الكاملة من ميزات التحسين.