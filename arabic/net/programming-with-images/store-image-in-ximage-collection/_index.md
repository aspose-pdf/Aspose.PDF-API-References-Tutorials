---
title: تخزين الصورة في مجموعة XImage
linktitle: تخزين الصورة في مجموعة XImage
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتخزين صورة في مجموعة XImage باستخدام Aspose.PDF for .NET.
type: docs
weight: 290
url: /ar/net/programming-with-images/store-image-in-ximage-collection/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تخزين صورة في مجموعة XImage باستخدام Aspose.PDF لـ .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تهيئة مستند PDF

للبدء ، استخدم الكود التالي لتهيئة مستند PDF جديد:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//قم بتهيئة المستند
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## الخطوة 2: إضافة الصورة إلى مجموعة XImage

بعد ذلك ، سنضيف الصورة إلى مجموعة XImage لمستند PDF. استخدم الكود التالي:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

تأكد من توفير المسار الصحيح لملف الصورة المصدر.

## الخطوة 3: وضع الصورة على الصفحة

الآن دعنا نضع الصورة على صفحة وثيقة PDF. استخدم الكود التالي:

```csharp
page. Contents. Add(new GSave());

// ضبط الإحداثيات
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

// باستخدام عامل التشغيل ConcatenateMatrix: حدد كيفية وضع الصورة
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

سيؤدي هذا إلى وضع الصورة في الإحداثيات المحددة على الصفحة.

## الخطوة 4: حفظ مستند PDF

أخيرًا ، سنقوم بحفظ مستند PDF المحدث. استخدم الكود التالي:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

تأكد من توفير المسار المطلوب واسم الملف لمستند PDF النهائي.

### نموذج التعليمات البرمجية المصدر لـ Store Image In XImage Collection باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة المستند
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// ضبط الإحداثيات
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
// باستخدام عامل ConcatenateMatrix (مصفوفة متسلسلة): يحدد كيفية وضع الصورة
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## خاتمة

تهنئة ! لقد نجحت في تخزين صورة في مجموعة XImage باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لمعالجة الصور وتخصيصها في ملفات PDF.

### التعليمات

#### س: ما هو الغرض من تخزين صورة في مجموعة XImage باستخدام Aspose.PDF لـ .NET؟

ج: يتيح لك تخزين صورة في مجموعة XImage إدارة الصور واستخدامها بكفاءة داخل مستند PDF. يمكّنك هذا الأسلوب من معالجة الصور وتخصيصها وتخصيصها قبل وضعها على صفحات معينة.

#### س: كيف يختلف تخزين صورة في مجموعة XImage عن وضع صورة مباشرة على صفحة PDF؟

ج: يوفر تخزين صورة في مجموعة XImage طريقة أكثر تنظيماً وقابلة لإعادة الاستخدام لإدارة الصور. بدلاً من وضع صورة مباشرة على الصفحة ، يمكنك تخزينها في المجموعة ويمكنك بعد ذلك الرجوع إليها بالاسم عند الحاجة ، مما يسمح بإدارة وتعديل أسهل.

#### س: هل يمكنني إضافة صور متعددة إلى مجموعة XImage داخل مستند PDF واحد؟

ج: نعم ، يمكنك إضافة صور متعددة إلى مجموعة XImage داخل نفس مستند PDF. يتم تعيين اسم فريد لكل صورة في المجموعة ، والذي يمكن استخدامه للإشارة إلى الصور ووضعها على صفحات مختلفة.

#### س: كيف يمكنني تحديد موضع وحجم الصورة عند وضعها على صفحة PDF من مجموعة XImage؟

ج: لتحديد موضع الصورة وحجمها ، تحتاج إلى تحديد مستطيل وتحويل مصفوفة. يحدد المستطيل حدود الصورة ، ويحدد تحويل المصفوفة كيفية وضع الصورة داخل ذلك المستطيل.

####  س: ما هو الغرض من`GSave()` and `GRestore()` operators in the code for placing the image?

 ج: إن`GSave()` و`GRestore()` تُستخدم عوامل التشغيل لحفظ واستعادة حالة الرسومات لصفحة PDF. يضمن ذلك أن العمليات التي يتم إجراؤها على الصفحة ، مثل وضع الصورة ، لا تؤثر على حالة الصفحة بعد وضع الصورة.

#### س: هل يمكنني تطبيق تعديلات أو تحويلات إضافية على الصور المخزنة في مجموعة XImage؟

ج: نعم ، يمكنك تطبيق العديد من التعديلات والتحولات على الصور المخزنة في مجموعة XImage. يمكنك تدوير ، وقياس ، واقتصاص ، وإجراء عمليات تحويل أخرى باستخدام العمليات والتقنيات المناسبة التي يوفرها Aspose.PDF لـ .NET.

#### س: كيف يمكنني دمج هذه الطريقة في مشاريعي الخاصة لتخزين الصور ووضعها في مجموعة XImage لمستند PDF؟

ج: لدمج هذه الطريقة ، اتبع الخطوات الموضحة وقم بتعديل الكود لتلبية متطلبات مشروعك. يمكنك استخدام مجموعة XImage لتخزين الصور وإدارتها ، ثم وضعها في صفحات محددة باستخدام الإحداثيات والتحولات المحددة.

#### س: هل هناك أي اعتبارات أو قيود عند العمل مع مجموعة XImage في Aspose.PDF for .NET؟

ج: بينما توفر مجموعة XImage طريقة قوية لإدارة الصور ومعالجتها ، فمن المهم مراعاة عوامل مثل استخدام الذاكرة وتعقيد العمليات التي يتم إجراؤها على الصور. يوصى بالإدارة الدقيقة للمجموعة والاستخدام الفعال للموارد.

#### س: هل يمكنني إعادة استخدام الصور المخزنة في مجموعة XImage عبر مستندات PDF متعددة؟

ج: مجموعة XImage خاصة بكل مستند PDF وليست مصممة لإعادة استخدام المستندات المشتركة. إذا كنت بحاجة إلى إعادة استخدام الصور عبر مستندات متعددة ، فستحتاج إلى تخزينها وإدارتها بشكل منفصل لكل مستند.