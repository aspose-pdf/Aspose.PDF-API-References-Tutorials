---
title: إضافة صورة
linktitle: إضافة صورة
second_title: Aspose.PDF لمرجع .NET API
description: أضف صورة بسهولة إلى مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-images/add-image/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية إضافة صورة إلى مستند PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

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

 سنقوم الآن بإنشاء ملف`Rectangle` كائن و`Matrix` هدف. يمثل المستطيل موضع الصورة وحجمها ، بينما تحدد المصفوفة كيفية وضع الصورة.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## الخطوة 9: المصفوفة المتسلسلة لوضع الصورة

 لتحديد كيفية وضع الصورة في المستطيل ، نستخدم الامتداد`ConcatenateMatrix`المشغل أو العامل. يحدد هذا المشغل مصفوفة التحويل التي تعين مساحة إحداثيات الصورة لمساحة إحداثيات الصفحة.

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
// احصل على الصفحة حيث يجب إضافة الصورة
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
//باستخدام عامل ConcatenateMatrix (مصفوفة متسلسلة): يحدد كيفية وضع الصورة
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