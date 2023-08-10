---
title: وضع نص حول الصورة
linktitle: وضع نص حول الصورة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية وضع نص حول صورة في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 260
url: /ar/net/programming-with-text/placing-text-around-image/
---

في هذا البرنامج التعليمي ، سنشرح كيفية وضع نص حول صورة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنمر في عملية إنشاء جدول خطوة بخطوة ، وإضافة صورة ، ووضع النص حول الصورة باستخدام كود المصدر C # المقدم.

## متطلبات

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى الدليل حيث تريد حفظ ملف PDF الذي تم إنشاؤه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بإنشاء مستند وصفحة

 بعد ذلك ، نقوم بإنشاء ملف`Document` كائن وإضافة صفحة إليه باستخدام`Pages.Add()` طريقة.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 3: قم بإنشاء جدول

 نقوم بإنشاء جدول باستخدام`Table` فئة وإضافتها إلى مجموعة فقرات الصفحة.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## الخطوة 4: تعيين عرض عمود الجدول والهوامش

 قمنا بتعيين عرض أعمدة الجدول وإنشاء ملف`MarginInfo` كائن لتعيين الهوامش.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## الخطوة 5: أضف صورة إلى الجدول

 نقوم بإنشاء ملف`Image` كائن ، حدد مسار ملف الصورة ، واضبط الارتفاع والعرض الثابتين للصورة. ثم نضيف الصورة إلى مجموعة الفقرات لخلية الجدول.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## الخطوة 6: أضف نصًا حول الصورة

نقوم بإنشاء متغيرات سلسلة تحتوي على نص بتنسيق HTML وإنشاء ملف`HtmlFragment` هدف. ثم نضيف نص HTML إلى خلية الجدول التي تحتوي على الصورة.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## الخطوة 7: أضف نصًا إضافيًا

 نحن نصنع آخر`HtmlFragment` كائن يحتوي على نص إضافي بتنسيق HTML وإضافته إلى خلية جدول منفصلة.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## الخطوة 8: احفظ مستند PDF

أخيرًا ، نحفظ مستند PDF في ملف الإخراج المحدد.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Placing Text Around Image باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// قم بإنشاء صفحة في ملف Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// إنشاء كائن جدول
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// أضف الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(table1);
// اضبط مع عرض أعمدة الجدول
table1.ColumnWidths = "120 270";
// قم بإنشاء كائن MarginInfo وقم بتعيين هوامشه اليسرى والسفلية واليمنى والعليا
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// قم بتعيين مساحة الخلية الافتراضية إلى كائن MarginInfo
table1.DefaultCellPadding = margin;
// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
Aspose.Pdf.Row row1 = table1.Rows.Add();
// قم بإنشاء كائن صورة
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// حدد مسار ملف الصورة
logo.File = dataDir + "aspose-logo.jpg";
// حدد الصورة ذات الارتفاع الثابت
logo.FixHeight = 120;
// حدد الصورة ذات العرض الثابت
logo.FixWidth = 110;
row1.Cells.Add();
// أضف الصورة إلى مجموعة فقرات خلية الجدول
row1.Cells[0].Paragraphs.Add(logo);
//إنشاء متغيرات سلسلة مع نص يحتوي على علامات html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
// أنشئ كائنًا نصيًا لإضافته إلى يمين الصورة
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// أضف فقرات النص التي تحتوي على نص HTML إلى خلية الجدول
row1.Cells[1].Paragraphs.Add(TitleText);
// عيّن المحاذاة الرأسية لمحتويات الصف على أنها Top
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// قم بتعيين قيمة امتداد الصف للصف الثاني على 2
SecondRow.Cells[0].ColSpan = 2;
// عيّن المحاذاة الرأسية للصف الثاني على أنها Top
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// أضف فقرات النص التي تحتوي على نص HTML إلى خلية الجدول
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// احفظ ملف Pdf
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية وضع نص حول صورة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك إنشاء جدول وإضافة صورة ووضع نص حول الصورة في مستند PDF.