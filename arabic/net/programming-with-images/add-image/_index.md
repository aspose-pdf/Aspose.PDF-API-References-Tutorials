---
title: إضافة صورة في ملف PDF
linktitle: إضافة صورة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: أضف صورة بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-images/add-image/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية إضافة صورة في ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: تعيين إحداثيات الصورة

 قم بتعيين إحداثيات الصورة التي تريد إضافتها. المتغيرات`lowerLeftX`, `lowerLeftY`, `upperRightX` و`upperRightY` تمثل إحداثيات الزاوية اليسرى السفلية والزاوية اليمنى العليا للصورة على التوالي.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## الخطوة 4: احصل على الصفحة حيث يجب إضافة الصورة

لإضافة الصورة إلى صفحة معينة من مستند PDF ، نحتاج أولاً إلى استرداد تلك الصفحة. في هذا المثال ، نضيف الصورة إلى الصفحة الثانية (الفهرس 1) من المستند.

```csharp
Page page = pdfDocument.Pages[1];
```

## الخطوة 5: قم بتحميل الصورة من دفق

 سنقوم الآن بتحميل الصورة التي نريد إضافتها إلى مستند PDF. يفترض هذا المثال أن لديك ملف صورة باسم`aspose-logo.jpg` في نفس الدليل مثل المستند الخاص بك. استبدل اسم الملف إذا لزم الأمر.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## الخطوة 6: أضف الصورة إلى Page Assets

لاستخدام الصورة في مستند PDF ، نحتاج إلى إضافتها إلى مجموعة صور موارد الصفحة.

```csharp
page.Resources.Images.Add(imageStream);
```

## الخطوة 7: حفظ حالة الرسومات الحالية

 قبل رسم الصورة ، نحتاج إلى حفظ حالة الرسومات الحالية باستخدام امتداد`GSave` المشغل أو العامل. وهذا يضمن إمكانية التراجع عن التغييرات التي تم إجراؤها على حالة الرسومات لاحقًا.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## الخطوة 8: إنشاء كائنات مستطيلة ومصفوفة

 سنقوم الآن بإنشاء ملف`Rectangle` كائن و`Matrix`هدف. يمثل المستطيل موضع الصورة وحجمها ، بينما تحدد المصفوفة كيفية وضع الصورة.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## الخطوة 9: المصفوفة المتسلسلة لوضع الصورة

 لتحديد كيفية وضع الصورة في المستطيل ، نستخدم الامتداد`ConcatenateMatrix` المشغل أو العامل. يحدد هذا المشغل مصفوفة التحويل التي تعين مساحة إحداثيات الصورة لمساحة إحداثيات الصفحة.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## الخطوة 10: ارسم الصورة

 في هذه الخطوة سنقوم برسم الصورة على الصفحة باستخدام ملف`Do` المشغل أو العامل. ال`Do` يأخذ عامل التشغيل اسم الصورة من الموارد ويرسمها على الصفحة.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## الخطوة 11: استعادة حالة الرسومات

 بعد رسم الصورة ، نحتاج إلى استعادة حالة الرسومات السابقة باستخدام امتداد`GRestore` المشغل أو العامل.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## الخطوة 12: احفظ المستند المحدث

 أخيرًا ، سنقوم بحفظ المستند المحدث في ملف جديد. قم بتحديث ملف`dataDir` متغير مع دليل الإخراج المطلوب واسم الملف.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Add Image باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// ضبط الإحداثيات
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//احصل على الصفحة حيث يجب إضافة الصورة
Page page = pdfDocument.Pages[1];
// تحميل الصورة في تيار
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// أضف صورة إلى مجموعة الصور لمصادر الصفحة
page.Resources.Images.Add(imageStream);
// باستخدام عامل تشغيل GSave: يحفظ هذا المشغل حالة الرسومات الحالية
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// إنشاء كائنات مستطيل ومصفوفة
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// باستخدام عامل ConcatenateMatrix (مصفوفة متسلسلة): يحدد كيفية وضع الصورة
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// باستخدام عامل التشغيل: يقوم هذا العامل برسم الصورة
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// باستخدام عامل GRestore: يستعيد هذا المشغل حالة الرسومات
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إضافة صورة إلى مستند PDF باستخدام Aspose.PDF لـ .NET. لقد غطينا كل خطوة بالتفصيل ، من فتح المستند إلى حفظ الإصدار المحدث. باتباع هذا الدليل ، يجب أن تكون الآن قادرًا على تضمين الصور في ملفات PDF الخاصة بك برمجيًا باستخدام C # و Aspose.PDF.

### الأسئلة الشائعة لإضافة صورة في ملف PDF

#### س: لماذا أرغب في إضافة صورة إلى مستند PDF؟

ج: يمكن أن تؤدي إضافة الصور إلى مستند PDF إلى تحسين المحتوى المرئي أو توفير سياق إضافي أو تضمين الشعارات والرسومات في ملفات PDF الخاصة بك.

#### س: هل يمكنني إضافة صور إلى صفحات معينة داخل مستند PDF؟

ج: نعم ، يمكنك تحديد الصفحة التي تريد إضافة الصورة إليها. في الكود المقدم ، تتم إضافة الصورة إلى الصفحة الثانية من مستند PDF.

#### س: كيف أقوم بضبط موضع وحجم الصورة المضافة؟

 ج: يمكنك تعديل ملف`lowerLeftX`, `lowerLeftY`, `upperRightX` ، و`upperRightY` المتغيرات في الكود لتعيين إحداثيات الصورة والتحكم في حجمها وموضعها على الصفحة.

#### س: ما نوع تنسيقات الصور التي يمكنني إضافتها باستخدام هذه الطريقة؟

ج: يفترض مثال الرمز المقدم أنك تقوم بتحميل صورة JPG (`aspose-logo.jpg`). يدعم Aspose.PDF for .NET تنسيقات الصور المختلفة ، بما في ذلك PNG و BMP و GIF والمزيد.

#### س: كيف يمكنني التأكد من أن الصورة المضافة تناسب الإحداثيات المحددة؟

 ج: تأكد من ضبط إحداثيات وحجم ملف`Rectangle` هدف (`rectangle`لمطابقة أبعاد الصورة وموضعها المطلوب على الصفحة.

#### س: هل يمكنني إضافة صور متعددة إلى صفحة PDF واحدة؟

ج: نعم ، يمكنك إضافة صور متعددة إلى صفحة PDF واحدة عن طريق تكرار العملية لكل صورة وضبط الإحداثيات والمعلمات الأخرى وفقًا لذلك.

####  س: كيف يعمل ملف`GSave` and `GRestore` operator work in the code?

 ج: إن`GSave` يحفظ عامل التشغيل حالة الرسومات الحالية ، مما يسمح لك بإجراء تغييرات دون التأثير على سياق الرسومات العام. ال`GRestore` يستعيد المشغل حالة الرسومات السابقة بعد إجراء التغييرات.

#### س: ماذا يحدث إذا لم يتم العثور على ملف الصورة في المسار المحدد؟

ج: إذا لم يتم العثور على ملف الصورة في المسار المحدد ، فسيقوم الرمز بطرح استثناء عند محاولة تحميل دفق الصورة. تأكد من وجود ملف الصورة في الدليل الصحيح.

#### س: هل يمكنني تخصيص موضع الصورة ومظهرها بشكل أكبر؟

 ج: نعم ، يمكنك تخصيص مظهر الصورة عن طريق تعديل ملف`Matrix`الكائن وتعديل العوامل الأخرى داخل الكود. راجع وثائق Aspose.PDF للتخصيص المتقدم.

#### س: كيف يمكنني اختبار ما إذا كانت الصورة قد تمت إضافتها بنجاح إلى ملف PDF؟

ج: بعد تطبيق الكود المقدم لإضافة الصورة ، افتح ملف PDF المعدل وتحقق من عرض الصورة على الصفحة المحددة بالموضع الصحيح.

#### س: هل تؤثر إضافة الصور على المحتوى الأصلي لوثيقة PDF؟

ج: لا تؤثر إضافة الصور على المحتوى الأصلي لوثيقة PDF. يعزز المستند من خلال تضمين العناصر المرئية.