---
title: أضف طابع التاريخ والوقت
linktitle: أضف طابع التاريخ والوقت
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة طابع التاريخ والوقت بسهولة إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
في هذه المقالة ، سوف نأخذك خطوة بخطوة حول كيفية إضافة طابع التاريخ والوقت باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لإضافة طابع التاريخ والوقت إلى مستند PDF موجود.

## متطلبات

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الأولى: تهيئة البيئة

قبل أن تتمكن من إضافة طابع التاريخ والوقت إلى مستند PDF ، تحتاج إلى إعداد بيئة التطوير الخاصة بك. فيما يلي الخطوات التي يجب اتباعها:

1. افتح IDE المفضل لديك (بيئة التطوير المتكاملة).
2. إنشاء مشروع C # جديد.
3. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: إضافة مكتبة Aspose.PDF

مطلوب مكتبة Aspose.PDF لـ .NET للعمل مع مستندات PDF في مشروعك.

## الخطوة 3: تحميل مستند PDF

تتمثل الخطوة الأولى لإضافة طابع التاريخ والوقت في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 4: إنشاء طابع التاريخ والوقت

الآن بعد أن قمت بتحميل المستند

  PDF ، يمكنك إنشاء طابع التاريخ والوقت لإضافته. هيريس كيفية القيام بذلك:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// قم بإنشاء مخزن نصي
TextStamp textStamp = new TextStamp(annotationText);
```

يقوم الكود أعلاه بإنشاء مخزن نص جديد يحتوي على التاريخ والوقت الحاليين.

## الخطوة 5: تكوين خصائص الطوابع

قبل إضافة الختم إلى مستند PDF ، يمكنك تكوين خصائص متنوعة للختم ، مثل الهامش ، والمحاذاة الأفقية والرأسية ، وما إلى ذلك ، وإليك الطريقة:

```csharp
// تعيين خصائص المخزن المؤقت
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

يمكنك تعديل هذه الخصائص وفقًا لاحتياجاتك.

## الخطوة السادسة: إضافة طابع إلى ملف PDF

الآن وبعد أن أصبح طابع التاريخ والوقت جاهزًا ، يمكنك إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// أضف الختم إلى مجموعة طوابع الصفحة
pdfDocument.Pages[1].AddStamp(textStamp);
```

يضيف الرمز أعلاه الطابع إلى الصفحة الأولى من مستند PDF. يمكنك تحديد صفحة أخرى إذا لزم الأمر.

## الخطوة 7: احفظ المستند الناتج

بمجرد إضافة طابع التاريخ والوقت ، يمكنك حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ المستند الناتج
pdfDocument.Save(dataDir);
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Add Date Time Stamp باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// إنشاء طابع نصي
TextStamp textStamp = new TextStamp(annotationText);

// تعيين خصائص الطابع
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// إضافة الطوابع على جمع الطوابع
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة طابع التاريخ والوقت باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لإضافة طوابع التاريخ والوقت إلى مستندات PDF.
