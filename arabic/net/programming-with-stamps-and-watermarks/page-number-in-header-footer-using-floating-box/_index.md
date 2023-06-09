---
title: رقم الصفحة في رأس تذييل باستخدام مربع عائم
linktitle: رقم الصفحة في رأس تذييل باستخدام مربع عائم
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة رقم الصفحة في رأس وتذييل مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 150
url: /ar/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية إضافة رقم الصفحة في رأس وتذييل مستند PDF باستخدام FloatingBox مع Aspose.PDF for .NET. سنستخدم الكود المصدري C # المقدم لإنشاء مستند PDF وإضافة صفحة وإنشاء FloatingBox وتعيين موضعه وإضافة رقم الصفحة إليه ثم حفظ مستند PDF المعدل.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة 2: إنشاء مستند PDF وإضافة صفحة

تتمثل الخطوة الأولى في إنشاء مثيل لمستند PDF وإضافة صفحة إليه. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء مستند PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// أضف صفحة إلى مستند PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث تريد حفظ مستند PDF.

## الخطوة 3: إنشاء FloatingBox وإضافة رقم الصفحة

الآن بعد أن تمت إضافة الصفحة إلى مستند PDF ، يمكننا إنشاء FloatingBox وتعيين موضعه وإضافة رقم الصفحة إليه. إليك الطريقة:

```csharp
// قم بإنشاء FloatingBox بعرض 140 وارتفاع 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// عيّن الموضع الأيسر للفقرة
box1. Left = 2;

// اضبط الموضع العلوي للفقرة
box1. Top = 10;

// أضف رقم الصفحة إلى FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// أضف FloatingBox إلى الصفحة
page.Paragraphs.Add(box1);
```

يقوم الكود أعلاه بإنشاء FloatingBox بعرض 140 وارتفاع 80. بعد ذلك ، قمنا بتعيين موضعه عن طريق تحديد القيم اليسرى والعليا. أخيرًا ، نضيف رقم الصفحة إلى FloatingBox باستخدام TextFragment يحتوي على الصيغة "($ p / $ P)" والتي سيتم استبدالها برقم الصفحة الحالية والعدد الإجمالي للصفحات.

## الخطوة 4: حفظ مستند PDF المعدل

بمجرد إضافة رقم الصفحة إلى الرأس أو التذييل باستخدام FloatingBox ، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Page Numberin Header Footer استخدام Floating Box باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// مثيل المستند
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// أضف صفحة إلى مستند pdf
Aspose.Pdf.Page page = pdf.Pages.Add();

// تهيئة مثيل جديد لفئة FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// قيمة عائمة تشير إلى الموضع الأيسر للفقرة
box1.Left = 2;

// قيمة عائمة تشير إلى الموضع العلوي للفقرة
box1.Top = 10;

// أضف وحدات الماكرو إلى مجموعة الفقرات من FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// أضف FloatingBox إلى الصفحة
page.Paragraphs.Add(box1);

// احفظ المستند
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة رقم الصفحة في رأس وتذييل مستند PDF باستخدام FloatingBox مع Aspose.PDF لـ .NET. يمكنك الآن تخصيص الرؤوس والتذييلات عن طريق إضافة معلومات ديناميكية مثل رقم الصفحة.
