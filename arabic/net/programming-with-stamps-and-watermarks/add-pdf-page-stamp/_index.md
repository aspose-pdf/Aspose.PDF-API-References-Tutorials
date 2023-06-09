---
title: أضف طابع صفحة PDF
linktitle: أضف طابع صفحة PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة طابع صفحة PDF بسهولة إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---

في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية إضافة طابع صفحة PDF إلى مستند PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لإضافة طابع مخصص إلى صفحة معينة من مستند PDF.

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
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: إنشاء المخزن المؤقت للصفحة

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك إنشاء ختم الصفحة لإضافته. هيريس كيفية القيام بذلك:

```csharp
// قم بإنشاء المخزن المؤقت للصفحة
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

يقوم الكود أعلاه بإنشاء مخزن مؤقت للصفحة جديد باستخدام الصفحة الأولى من مستند PDF.

## الخطوة 4: تكوين خصائص المخزن المؤقت للصفحة

قبل إضافة ختم الصفحة إلى مستند PDF ، يمكنك تكوين خصائص متنوعة للختم ، مثل الخلفية والموضع والدوران وما إلى ذلك ، وإليك الطريقة:

```csharp
// تكوين خصائص المخزن المؤقت للصفحة
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

يمكنك تعديل هذه الخصائص وفقًا لاحتياجاتك.

## الخطوة 5: إضافة طابع الصفحة إلى ملف PDF

الآن وبعد أن أصبح ختم الصفحة جاهزًا ، يمكنك إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// إضافة المخزن المؤقت للصفحة إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(pageStamp);
```

يضيف الكود أعلاه طابع الصفحة إلى الصفحة الأولى من مستند PDF. يمكنك تحديد صفحة أخرى إذا لزم الأمر.

## الخطوة 6: احفظ المستند الناتج

بمجرد إضافة ختم الصفحة ، يمكنك حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ المستند الناتج
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Add PDFPage Stamp باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

// إنشاء طابع الصفحة
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

// أضف طابعًا إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة طابع صفحة PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لإضافة طوابع مخصصة إلى صفحات معينة من مستندات PDF الخاصة بك.
