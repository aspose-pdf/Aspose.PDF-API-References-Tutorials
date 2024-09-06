---
title: إضافة صورة إلى ملف PDF
linktitle: إضافة صورة إلى ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة إضافة صورة إلى ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-images/add-image/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية إضافة صورة إلى ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من إعداد البيئة الخاصة بك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستندات

قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

 في هذه الخطوة سوف نقوم بفتح مستند PDF باستخدام`Document` فئة Aspose.PDF. استخدم`Document` منشئ ومرر المسار إلى مستند PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: تعيين إحداثيات الصورة

 قم بتعيين إحداثيات الصورة التي تريد إضافتها. المتغيرات`lowerLeftX`, `lowerLeftY`, `upperRightX` و`upperRightY` تمثل إحداثيات الزاوية السفلية اليسرى والزاوية العلوية اليمنى للصورة على التوالي.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## الخطوة 4: احصل على الصفحة التي يجب إضافة الصورة إليها

لإضافة الصورة إلى صفحة معينة من مستند PDF، نحتاج أولاً إلى استرداد تلك الصفحة. في هذا المثال، نضيف الصورة إلى الصفحة الثانية (الفهرس 1) من المستند.

```csharp
Page page = pdfDocument.Pages[1];
```

## الخطوة 5: تحميل الصورة من الدفق

 سنقوم الآن بتحميل الصورة التي نريد إضافتها إلى مستند PDF. يفترض هذا المثال أن لديك ملف صورة باسم`aspose-logo.jpg` في نفس الدليل الذي يوجد به مستندك. استبدل اسم الملف إذا لزم الأمر.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## الخطوة 6: إضافة الصورة إلى أصول الصفحة

لاستخدام الصورة في مستند PDF، نحتاج إلى إضافتها إلى مجموعة صور الموارد الخاصة بالصفحة.

```csharp
page.Resources.Images.Add(imageStream);
```

## الخطوة 7: حفظ حالة الرسومات الحالية

 قبل رسم الصورة، نحتاج إلى حفظ حالة الرسومات الحالية باستخدام`GSave` المشغل. يضمن هذا إمكانية التراجع عن التغييرات التي طرأت على حالة الرسومات في وقت لاحق.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## الخطوة 8: إنشاء كائنات المستطيل والمصفوفة

 سنقوم الآن بإنشاء`Rectangle` كائن و`Matrix` الكائن. يمثل المستطيل موضع وحجم الصورة، بينما تحدد المصفوفة كيفية وضع الصورة.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## الخطوة 9: ربط المصفوفة لوضع الصورة

 لتحديد كيفية وضع الصورة في المستطيل، نستخدم`ConcatenateMatrix` المشغل. يحدد هذا المشغل مصفوفة التحويل التي تقوم بتعيين مساحة إحداثيات الصورة إلى مساحة إحداثيات الصفحة.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## الخطوة 10: ارسم الصورة

 في هذه الخطوة سوف نقوم برسم الصورة على الصفحة باستخدام`Do` المشغل.`Do`يأخذ المشغل اسم الصورة من الموارد ويضعها على الصفحة.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## الخطوة 11: استعادة حالة الرسومات

 بعد رسم الصورة، نحتاج إلى استعادة حالة الرسومات السابقة باستخدام`GRestore` المشغل.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## الخطوة 12: احفظ المستند المحدث

 أخيرًا، سنحفظ المستند المحدث في ملف جديد. قم بتحديث`dataDir` متغير مع دليل الإخراج المطلوب واسم الملف.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### عينة من كود المصدر لإضافة صورة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// تعيين الإحداثيات
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// احصل على الصفحة التي تحتاج إلى إضافة الصورة إليها
Page page = pdfDocument.Pages[1];
// تحميل الصورة إلى الدفق
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// أضف صورة إلى مجموعة الصور في موارد الصفحة
page.Resources.Images.Add(imageStream);
// استخدام عامل GSave: يحفظ هذا العامل حالة الرسومات الحالية
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// إنشاء كائنات المستطيل والمصفوفة
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// استخدام عامل ConcatenateMatrix (مصفوفة متسلسلة): يحدد كيفية وضع الصورة
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// استخدام عامل Do: يقوم هذا العامل برسم الصورة
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// استخدام عامل GRestore: يقوم هذا العامل باستعادة حالة الرسومات
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة صورة إلى مستند PDF باستخدام Aspose.PDF لـ .NET. لقد قمنا بتغطية كل خطوة بالتفصيل، من فتح المستند إلى حفظ الإصدار المحدث. باتباع هذا الدليل، يجب أن تتمكن الآن من تضمين الصور في ملفات PDF الخاصة بك برمجيًا باستخدام C# وAspose.PDF.

### الأسئلة الشائعة حول إضافة صورة إلى ملف PDF

#### س: لماذا أرغب في إضافة صورة إلى مستند PDF؟

أ: قد يؤدي إضافة الصور إلى مستند PDF إلى تحسين المحتوى المرئي أو توفير سياق إضافي أو تضمين شعارات ورسومات في ملفات PDF الخاصة بك.

#### س: هل يمكنني إضافة صور إلى صفحات محددة داخل مستند PDF؟

ج: نعم، يمكنك تحديد الصفحة التي تريد إضافة الصورة إليها. في الكود المقدم، تتم إضافة الصورة إلى الصفحة الثانية من مستند PDF.

#### س: كيف أقوم بتعديل موضع وحجم الصورة المضافة؟

 أ: يمكنك تعديل`lowerLeftX`, `lowerLeftY`, `upperRightX` ، و`upperRightY` المتغيرات في الكود لتعيين إحداثيات الصورة والتحكم في حجمها وموقعها على الصفحة.

#### س: ما هي أنواع تنسيقات الصور التي يمكنني إضافتها باستخدام هذه الطريقة؟

أ: يفترض مثال الكود المقدم أنك تقوم بتحميل صورة JPG (`aspose-logo.jpg`يدعم Aspose.PDF لـ .NET تنسيقات الصور المختلفة، بما في ذلك PNG، وBMP، وGIF، والمزيد.

#### س: كيف يمكنني التأكد من أن الصورة المضافة تتناسب مع الإحداثيات المحددة؟

 أ: تأكد من ضبط إحداثيات وحجم`Rectangle` هدف (`rectangle`) لتتناسب مع أبعاد الصورة وموضعها المطلوب على الصفحة.

#### س: هل يمكنني إضافة صور متعددة إلى صفحة PDF واحدة؟

ج: نعم، يمكنك إضافة صور متعددة إلى صفحة PDF واحدة عن طريق تكرار العملية لكل صورة وضبط الإحداثيات والمعلمات الأخرى وفقًا لذلك.

####  س: كيف يتم ذلك؟`GSave` and `GRestore` operator work in the code?

 أ: ال`GSave` يحفظ المشغل حالة الرسومات الحالية، مما يسمح لك بإجراء تغييرات دون التأثير على سياق الرسومات الإجمالي.`GRestore` يقوم المشغل باستعادة حالة الرسومات السابقة بعد إجراء التغييرات.

#### س: ماذا يحدث إذا لم يتم العثور على ملف الصورة في المسار المحدد؟

ج: إذا لم يتم العثور على ملف الصورة في المسار المحدد، فسيقوم الكود بإلقاء استثناء عند محاولة تحميل مجرى الصورة. تأكد من أن ملف الصورة موجود في الدليل الصحيح.

#### س: هل يمكنني تخصيص وضع الصورة ومظهرها بشكل أكبر؟

 ج: نعم، يمكنك تخصيص مظهر الصورة عن طريق تعديل`Matrix` الكائن وضبط المشغلات الأخرى داخل الكود. راجع وثائق Aspose.PDF للتخصيص المتقدم.

#### س: كيف يمكنني اختبار ما إذا تمت إضافة الصورة بنجاح إلى ملف PDF؟

ج: بعد تطبيق الكود المقدم لإضافة الصورة، افتح ملف PDF المعدل وتأكد من عرض الصورة على الصفحة المحددة بالموضع الصحيح.

#### س: هل يؤثر إضافة الصور على المحتوى الأصلي لمستند PDF؟

ج: لا تؤثر إضافة الصور على المحتوى الأصلي لمستند PDF، بل تعمل على تحسين المستند من خلال تضمين عناصر مرئية.