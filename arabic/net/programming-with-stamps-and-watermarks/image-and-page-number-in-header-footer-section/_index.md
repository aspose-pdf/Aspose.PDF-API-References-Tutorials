---
title: الصورة ورقم الصفحة في قسم تذييل الرأس
linktitle: الصورة ورقم الصفحة في قسم تذييل الرأس
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة صورة ورقم صفحة في رأس وتذييل مستند PDF باستخدام Aspose.
type: docs
weight: 110
url: /ar/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية إضافة صورة ورقم الصفحة في قسم الرأس والتذييل في مستند PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لإنشاء صفحة ، وتعيين رأس وتذييل ، وإضافة صورة إلى الرأس والنص برقم الصفحة لتذييل المستند بتنسيق PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة 2: إنشاء مستند PDF وصفحة

تتمثل الخطوة الأولى في إنشاء كائن مستند جديد وصفحة في مستند PDF. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء كائن مستند جديد
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// قم بإنشاء صفحة في المستند
Aspose.Pdf.Page page = doc.Pages.Add();
```

يقوم الكود أعلاه بإنشاء كائن مستند جديد وصفحة فارغة في مستند PDF.

## الخطوة 3: إضافة الرأس بصورة

الآن بعد أن تم إنشاء الصفحة ، يمكننا إضافة قسم رأس مع صورة. إليك الطريقة:

```csharp
// قم بإنشاء قسم رأس
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// اضبط رأس الصفحة
page. Header = header;

// قم بإنشاء كائن صورة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// حدد مسار الصورة
image1.File = dataDir + "aspose-logo.jpg";

// أضف الصورة إلى رأس الصفحة الخاص بمستند PDF
header.Paragraphs.Add(image1);
```

يقوم الكود أعلاه بإنشاء قسم رأس ، وتعيين رأس الصفحة مع هذا القسم ، وإضافة صورة إلى الرأس.

## الخطوة 4: إضافة التذييل برقم الصفحة

الآن بعد أن تمت إضافة الرأس ، يمكننا إضافة قسم تذييل برقم صفحة. إليك الطريقة:

```csharp
// قم بإنشاء قسم تذييل
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// حدد تذييل مستند PDF
page. Footer = footer;

// قم بإنشاء كائن TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// أضف النص مع رقم الصفحة إلى تذييل مستند PDF
footer.Paragraphs.Add(txt);
```

يقوم الكود أعلاه بإنشاء قسم تذييل ، وتعيين تذييل الصفحة مع هذا القسم وإضافة جزء نص يحتوي على النص "الصفحة: ($ p of $ P)"

  الذي يعرض رقم الصفحة.

## الخطوة 5: حفظ مستند PDF المعدل

بمجرد إضافة الرأس والتذييل ، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر للصورة ورقم الصفحة في رأس تذييل الصفحة باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// قم بإنشاء صفحة في كائن المستند
Aspose.Pdf.Page page = doc.Pages.Add();

// إنشاء قسم رأس من المستند
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// قم بتعيين رأس ملف PDF
page.Header = header;

// قم بإنشاء كائن صورة في الصفحة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// حدد مسار ملف الصورة
image1.File = dataDir + "aspose-logo.jpg";

// أضف صورة إلى صفحة رأس ملف Pdf
header.Paragraphs.Add(image1);

// قم بإنشاء مقطع تذييل للمستند
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// قم بتعيين تذييل ملف PDF
page.Footer = footer;

// قم بإنشاء كائن نص
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// أضف نصًا إلى قسم الرأس في ملف Pdf
footer.Paragraphs.Add(txt);

// احفظ ملف Pdf
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة صورة ورقم الصفحة في قسم الرأس والتذييل في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه الطريقة لتخصيص رأس الصفحة وتذييلها في مستندات PDF الخاصة بك.
