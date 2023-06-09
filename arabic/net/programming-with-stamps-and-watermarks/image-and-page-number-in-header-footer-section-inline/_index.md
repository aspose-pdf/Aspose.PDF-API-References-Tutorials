---
title: الصورة ورقم الصفحة في قسم تذييل الرأس مضمن
linktitle: الصورة ورقم الصفحة في قسم تذييل الرأس مضمن
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة صورة ورقم الصفحة في الرأس والتذييل باستخدام فقرات مضمنة مع Aspose.PDF for .NET.
type: docs
weight: 120
url: /ar/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية إضافة صورة ورقم الصفحة في قسم الرأس والتذييل في مستند PDF باستخدام Aspose.PDF for .NET. سنستخدم الكود المصدري C # المقدم لإنشاء صفحة ، وتعيين رأس وتذييل ، وإضافة صورة ونص باستخدام فقرات مضمنة في رأس مستند PDF.

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
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// قم بإنشاء صفحة في المستند
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

يقوم الكود أعلاه بإنشاء كائن مستند جديد وصفحة فارغة في مستند PDF.

## الخطوة 3: إضافة الرأس بصورة ونص مضمّن

الآن بعد أن تم إنشاء الصفحة ، يمكننا إضافة قسم رأس مع صورة ونص باستخدام فقرات مضمنة. إليك الطريقة:

```csharp
// قم بإنشاء قسم رأس
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// اضبط رأس الصفحة
page. Header = header;

// قم بإنشاء كائن TextFragment لأول نص مضمّن
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// حدد لون النص
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//قم بإنشاء كائن صورة للصورة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// حدد مسار الصورة
image1.File = dataDir + "aspose-logo.jpg";

// حدد أبعاد الصورة
image1.FixWidth = 50;
image1.FixHeight = 20;

// أشر إلى أن أول نص مضمّن عبارة عن صورة
image1.IsInLineParagraph = true;

// قم بإنشاء نص مضمّن ثانٍ
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// إضافة العناصر إلى العنوان
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

تقوم الكود أعلاه بإنشاء قسم رأس ، وتعيين رأس الصفحة مع هذا القسم ، وإضافة جزء نص مع نص مضمن وكائن صورة مضمنة.

## الخطوة 4: حفظ مستند PDF المعدل

بمجرد إضافة رأس الصورة والنص المضمن ، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر للصورة ورقم الصفحة في مقطع رأس الصفحة مضمنًا باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند عن طريق استدعاء المُنشئ الفارغ الخاص به
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// قم بإنشاء صفحة في كائن Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// إنشاء قسم رأس من المستند
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// قم بتعيين رأس ملف PDF
page.Header = header;

// قم بإنشاء كائن نص
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// حدد اللون
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// قم بإنشاء كائن صورة في القسم
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// حدد مسار ملف الصورة
image1.File = dataDir + "aspose-logo.jpg";

// اضبط معلومات عرض الصورة
image1.FixWidth = 50;
image1.FixHeight = 20;

// الإشارة إلى أن InlineParagraph الخاص بـ seg1 هو صورة.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// احفظ ملف PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة صورة ورقم الصفحة في قسم الرأس والتذييل في مستند PDF باستخدام فقرات مضمنة مع Aspose.PDF for .NET. يمكنك الآن تخصيص رأس وتذييل مستندات PDF الخاصة بك بمرونة.
