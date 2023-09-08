---
title: إضافة صورة في ملف PDF
linktitle: إضافة صورة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بإضافة صورة بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-images/add-image/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية إضافة صورة في ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من أنك قمت بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود الذي يحتوي على المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

في هذه الخطوة، سنقوم بفتح مستند PDF باستخدام الملف`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ وتمرير المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: تعيين إحداثيات الصورة

 قم بتعيين إحداثيات الصورة التي تريد إضافتها. المتغيرات`lowerLeftX`, `lowerLeftY`, `upperRightX` و`upperRightY` تمثل إحداثيات الزاوية اليسرى السفلى والزاوية اليمنى العليا من الصورة على التوالي.

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

 سنقوم الآن بتحميل الصورة التي نريد إضافتها إلى مستند PDF. يفترض هذا المثال أن لديك ملف صورة اسمه`aspose-logo.jpg` في نفس الدليل مثل المستند الخاص بك. استبدل اسم الملف إذا لزم الأمر.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## الخطوة 6: إضافة الصورة إلى أصول الصفحة

لاستخدام الصورة في مستند PDF، نحتاج إلى إضافتها إلى مجموعة صور موارد الصفحة.

```csharp
page.Resources.Images.Add(imageStream);
```

## الخطوة 7: حفظ حالة الرسومات الحالية

 قبل رسم الصورة، نحتاج إلى حفظ حالة الرسومات الحالية باستخدام ملف`GSave` المشغل أو العامل. وهذا يضمن إمكانية التراجع عن التغييرات التي تم إجراؤها على حالة الرسومات لاحقًا.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## الخطوة 8: إنشاء كائنات مستطيلة ومصفوفة

 سنقوم الآن بإنشاء ملف`Rectangle` كائن و`Matrix`هدف. يمثل المستطيل موضع الصورة وحجمها، بينما تحدد المصفوفة كيفية وضع الصورة.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## الخطوة 9: قم بتسلسل المصفوفة لوضع الصورة

 لتحديد كيفية وضع الصورة في المستطيل، نستخدم`ConcatenateMatrix` المشغل أو العامل. يحدد هذا العامل مصفوفة التحويل التي تعين المساحة الإحداثية للصورة إلى المساحة الإحداثية للصفحة.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## الخطوة 10: ارسم الصورة

 في هذه الخطوة سوف نقوم برسم الصورة على الصفحة باستخدام`Do` المشغل أو العامل. ال`Do` يأخذ عامل التشغيل اسم الصورة من الموارد ويرسمه على الصفحة.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## الخطوة 11: استعادة حالة الرسومات

 بعد رسم الصورة، نحتاج إلى استعادة حالة الرسومات السابقة باستخدام الأمر`GRestore` المشغل أو العامل.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## الخطوة 12: احفظ المستند المحدث

 وأخيرًا، سنقوم بحفظ المستند المحدث في ملف جديد. تحديث`dataDir` متغير مع دليل الإخراج واسم الملف المطلوب.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لإضافة صورة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// تعيين الإحداثيات
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//احصل على الصفحة التي تريد إضافة الصورة إليها
Page page = pdfDocument.Pages[1];
// تحميل الصورة في الدفق
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// إضافة صورة إلى مجموعة الصور لموارد الصفحة
page.Resources.Images.Add(imageStream);
// استخدام عامل تشغيل GSave: يقوم هذا المشغل بحفظ حالة الرسومات الحالية
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// إنشاء كائنات مستطيلة ومصفوفة
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// استخدام عامل ConcatenateMatrix (مصفوفة متسلسلة): يحدد كيفية وضع الصورة
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// استخدام عامل التشغيل Do: يقوم هذا العامل برسم الصورة
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// استخدام مشغل GRestore: يقوم هذا المشغل باستعادة حالة الرسومات
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة صورة إلى مستند PDF باستخدام Aspose.PDF لـ .NET. لقد قمنا بتغطية كل خطوة بالتفصيل، بدءًا من فتح المستند وحتى حفظ النسخة المحدثة. باتباع هذا الدليل، يجب أن تكون الآن قادرًا على تضمين الصور في ملفات PDF الخاصة بك برمجيًا باستخدام C# وAspose.PDF.

### الأسئلة الشائعة لإضافة صورة في ملف PDF

#### س: لماذا أرغب في إضافة صورة إلى مستند PDF؟

ج: يمكن أن تؤدي إضافة الصور إلى مستند PDF إلى تحسين المحتوى المرئي أو توفير سياق إضافي أو تضمين شعارات ورسومات في ملفات PDF الخاصة بك.

#### س: هل يمكنني إضافة صور إلى صفحات معينة داخل مستند PDF؟

ج: نعم، يمكنك تحديد الصفحة التي تريد إضافة الصورة إليها. في الكود المقدم، تتم إضافة الصورة إلى الصفحة الثانية من مستند PDF.

#### س: كيف يمكنني ضبط موضع وحجم الصورة المضافة؟

 ج: يمكنك تعديل`lowerLeftX`, `lowerLeftY`, `upperRightX` ، و`upperRightY` المتغيرات الموجودة في الكود لتعيين إحداثيات الصورة والتحكم في حجمها وموضعها في الصفحة.

#### س: ما نوع تنسيقات الصور التي يمكنني إضافتها باستخدام هذه الطريقة؟

ج: يفترض مثال التعليمات البرمجية المقدم أنك تقوم بتحميل صورة JPG (`aspose-logo.jpg`). يدعم Aspose.PDF for .NET العديد من تنسيقات الصور، بما في ذلك PNG وBMP وGIF والمزيد.

#### س: كيف أتأكد من أن الصورة المضافة تتناسب ضمن الإحداثيات المحددة؟

 ج: تأكد من ضبط إحداثيات وحجم`Rectangle` هدف (`rectangle`لتتناسب مع أبعاد الصورة وموضعها المطلوب في الصفحة.

#### س: هل يمكنني إضافة صور متعددة إلى صفحة PDF واحدة؟

ج: نعم، يمكنك إضافة صور متعددة إلى صفحة PDF واحدة عن طريق تكرار العملية لكل صورة وضبط الإحداثيات والمعلمات الأخرى وفقًا لذلك.

####  س: كيف`GSave` and `GRestore` operator work in the code?

 ج: ال`GSave` يقوم المشغل بحفظ حالة الرسومات الحالية، مما يسمح لك بإجراء تغييرات دون التأثير على سياق الرسومات العام. ال`GRestore` يقوم المشغل باستعادة حالة الرسومات السابقة بعد إجراء التغييرات.

#### س: ماذا يحدث إذا لم يتم العثور على ملف الصورة في المسار المحدد؟

ج: إذا لم يتم العثور على ملف الصورة في المسار المحدد، فسيطرح الكود استثناءً عند محاولة تحميل دفق الصورة. تأكد من وجود ملف الصورة في الدليل الصحيح.

#### س: هل يمكنني تخصيص موضع الصورة ومظهرها بشكل أكبر؟

 ج: نعم، يمكنك تخصيص مظهر الصورة عن طريق تعديل`Matrix`الكائن وضبط العوامل الأخرى داخل الكود. راجع وثائق Aspose.PDF للتخصيص المتقدم.

#### س: كيف يمكنني اختبار ما إذا تمت إضافة الصورة بنجاح إلى ملف PDF؟

ج: بعد تطبيق الكود المقدم لإضافة الصورة، افتح ملف PDF المعدل وتأكد من عرض الصورة على الصفحة المحددة بالموضع الصحيح.

#### س: هل تؤثر إضافة الصور على المحتوى الأصلي لمستند PDF؟

ج: لا تؤثر إضافة الصور على المحتوى الأصلي لمستند PDF. إنه يعزز الوثيقة من خلال تضمين العناصر المرئية.