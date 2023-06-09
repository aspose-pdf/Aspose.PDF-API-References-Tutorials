---
title: أضف طابع الصورة
linktitle: أضف طابع الصورة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة طابع صورة بسهولة إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 20
url: /ar/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية إضافة مخزن مؤقت للصور إلى مستند PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لإضافة مخزن مؤقت للصور إلى صفحة معينة في مستند PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الثانية: تحميل مستند PDF

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: إنشاء الإطار المؤقت

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك إنشاء ختم الصورة لإضافته. هيريس كيفية القيام بذلك:

```csharp
// إنشاء المخزن المؤقت للإطار
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

يقوم الكود أعلاه بإنشاء مخزن مؤقت للصور جديد باستخدام ملف "aspose-logo.jpg". تأكد من صحة مسار ملف الصورة.

## الخطوة 4: تكوين خصائص المخزن المؤقت للصور

قبل إضافة طابع الصورة إلى مستند PDF ، يمكنك تكوين خصائص متنوعة للختم ، مثل العتامة والحجم والموضع وما إلى ذلك ، وإليك الطريقة:

```csharp
// تكوين خصائص المخزن المؤقت للصور
imageStamp. Background = true;
imageStamp. XIndent = 100;
imageStamp. YIndent = 100;
imageStamp. Height = 300;
imageStamp. Width = 300;
imageStamp.Rotate = Rotate.on270;
imageStamp. Opacity = 0.5;
```

يمكنك تعديل هذه الخصائص وفقًا لاحتياجاتك.

## الخطوة 5: إضافة طابع الصورة إلى ملف PDF

الآن وبعد أن أصبح ختم الصورة جاهزًا ، يمكنك إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// أضف المخزن المؤقت للإطار إلى الصفحة المحددة
pdfDocument.Pages[1].AddStamp(imageStamp);
```

يضيف الكود أعلاه مخزن الصورة المؤقت إلى الصفحة الأولى من مستند PDF. يمكنك تحديد صفحة أخرى إذا لزم الأمر.

## الخطوة 6: احفظ المستند الناتج

بمجرد إضافة المخزن المؤقت للصور ، يمكنك حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ المستند الناتج
pdfDocument.Save(dataDir);
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Add Image Stamp باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "AddImageStamp.pdf");

// إنشاء طابع الصورة
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
imageStamp.Background = true;
imageStamp.XIndent = 100;
imageStamp.YIndent = 100;
imageStamp.Height = 300;
imageStamp.Width = 300;
imageStamp.Rotate = Rotation.on270;
imageStamp.Opacity = 0.5;

// أضف طابعًا إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(imageStamp);
dataDir = dataDir + "AddImageStamp_out.pdf";

// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة مخزن مؤقت للصور باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لإضافة أختام صور مخصصة إلى مستندات PDF.
