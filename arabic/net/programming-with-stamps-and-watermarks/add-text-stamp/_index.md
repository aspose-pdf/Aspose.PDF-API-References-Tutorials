---
title: إضافة طابع نصي
linktitle: إضافة طابع نصي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة طابع نصي بسهولة إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية إضافة طابع نصي إلى مستند PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لإضافة طابع نصي مخصص إلى صفحة معينة من مستند PDF.

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
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: إنشاء المخزن المؤقت للنص

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك إنشاء طابع نصي لإضافته. هيريس كيفية القيام بذلك:

```csharp
// قم بإنشاء المخزن المؤقت للنص
TextStamp textStamp = new TextStamp("Example Stamp");
```

يقوم الكود أعلاه بإنشاء مخزن نص جديد يحتوي على النص المحدد.

## الخطوة 4: تكوين خصائص ختم النص

قبل إضافة طابع النص إلى مستند PDF ، يمكنك تكوين خصائص متنوعة للختم ، مثل الخلفية ، والموضع ، والدوران ، والخط ، والحجم ، وما إلى ذلك ، وإليك الطريقة:

```csharp
// تكوين خصائص المخزن المؤقت للنص
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

يمكنك تعديل هذه الخصائص وفقًا لاحتياجاتك.

## الخطوة 5: أضف طابع نصي إلى ملف PDF

الآن وبعد أن أصبح ختم النص جاهزًا ، يمكنك إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// إضافة مخزن النص إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(textStamp);
```

يضيف الرمز أعلاه طابع النص إلى الصفحة الأولى من مستند PDF. يمكنك تحديد صفحة أخرى إذا لزم الأمر.

## الخطوة 6: احفظ المستند الناتج

بمجرد إضافة الطابع النصي ، يمكنك حفظ مستند PDF الذي تم تحريره. إليك الطريقة:

```csharp
// احفظ المستند الناتج
pdfDocument.Save(dataDir);
```

يحفظ الكود أعلاه مستند PDF المعدل في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Add Text Stamp باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// إنشاء طابع نصي
TextStamp textStamp = new TextStamp("Sample Stamp");

// تعيين ما إذا كان الطابع هو الخلفية
textStamp.Background = true;

// تحديد الأصل
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// تدوير الختم
textStamp.Rotate = Rotation.on90;

// تعيين خصائص النص
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// أضف طابعًا إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة طابع نصي باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لإضافة أختام نصية مخصصة إلى مستندات PDF.
