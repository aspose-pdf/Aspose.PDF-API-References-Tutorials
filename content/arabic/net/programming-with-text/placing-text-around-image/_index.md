---
title: وضع النص حول الصورة في ملف PDF
linktitle: وضع النص حول الصورة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية وضع نص حول صورة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 260
url: /ar/net/programming-with-text/placing-text-around-image/
---
سنشرح في هذا البرنامج التعليمي كيفية وضع نص حول صورة في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنجري عملية خطوة بخطوة لإنشاء جدول وإضافة صورة وتحديد موضع النص حول الصورة باستخدام كود مصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir`متغير مع المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وصفحة

 بعد ذلك، نقوم بإنشاء`Document` كائن وإضافة صفحة إليه باستخدام`Pages.Add()` طريقة.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء جدول

 نقوم بإنشاء جدول باستخدام`Table` class وإضافته إلى مجموعة الفقرات بالصفحة.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## الخطوة 4: تعيين عرض وهوامش أعمدة الجدول

 قمنا بتعيين عرض أعمدة الجدول وإنشاء`MarginInfo` كائن لتعيين الهوامش.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## الخطوة 5: إضافة صورة إلى الجدول

 نحن ننشئ`Image` الكائن، وحدد مسار ملف الصورة، وقم بتعيين الارتفاع والعرض الثابتين للصورة. ثم نقوم بإضافة الصورة إلى مجموعة الفقرات لخلية الجدول.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## الخطوة 6: إضافة نص حول الصورة

 نقوم بإنشاء متغيرات سلسلة تحتوي على نص بتنسيق HTML وإنشاء ملف`HtmlFragment`هدف. ثم نقوم بإضافة نص HTML إلى خلية الجدول التي تحتوي على الصورة.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## الخطوة 7: إضافة نص إضافي

 نحن نخلق آخر`HtmlFragment` كائن يحتوي على نص إضافي بتنسيق HTML وإضافته إلى خلية جدول منفصلة.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## الخطوة 8: احفظ مستند PDF

وأخيرًا، نقوم بحفظ مستند PDF في ملف الإخراج المحدد.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لوضع نص حول الصورة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل لكائن المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// إنشاء صفحة في قوات الدفاع الشعبي
Aspose.Pdf.Page page = doc.Pages.Add();
// إنشاء مثيل لكائن الجدول
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// إضافة الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(table1);
// تعيين مع عرض أعمدة الجدول
table1.ColumnWidths = "120 270";
// قم بإنشاء كائن MarginInfo وقم بتعيين الهوامش اليسرى والسفلى واليمنى والعليا
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// قم بتعيين حشوة الخلية الافتراضية لكائن MarginInfo
table1.DefaultCellPadding = margin;
// قم بإنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row row1 = table1.Rows.Add();
// إنشاء كائن الصورة
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// حدد مسار ملف الصورة
logo.File = dataDir + "aspose-logo.jpg";
// حدد ارتفاع الصورة الثابت
logo.FixHeight = 120;
// حدد عرض الصورة الثابت
logo.FixWidth = 110;
row1.Cells.Add();
// إضافة الصورة إلى مجموعة الفقرات لخلية الجدول
row1.Cells[0].Paragraphs.Add(logo);
// قم بإنشاء متغيرات سلسلة تحتوي على نص يحتوي على علامات html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//قم بإنشاء كائن نصي لإضافته إلى يمين الصورة
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// أضف فقرات النص التي تحتوي على نص HTML إلى خلية الجدول
row1.Cells[1].Paragraphs.Add(TitleText);
// قم بتعيين المحاذاة الرأسية لمحتويات الصف على أنها أعلى
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// قم بإنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// قم بتعيين قيمة امتداد الصف للصف الثاني على 2
SecondRow.Cells[0].ColSpan = 2;
// قم بتعيين المحاذاة العمودية للصف الثاني كأعلى
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// أضف فقرات النص التي تحتوي على نص HTML إلى خلية الجدول
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// احفظ ملف PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية وضع نص حول صورة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل الموضح خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك إنشاء جدول وإضافة صورة ووضع نص حول الصورة في مستند PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "وضع نص حول الصورة في ملف PDF"؟

ج: يوضح البرنامج التعليمي "وضع نص حول الصورة في ملف PDF" كيفية استخدام مكتبة Aspose.PDF لـ .NET لوضع نص حول صورة في مستند PDF. يوفر البرنامج التعليمي دليلاً خطوة بخطوة وكود مصدر C# لمساعدتك في إنشاء جدول وإضافة صورة وتحديد موضع النص حول الصورة.

#### س: لماذا أرغب في وضع نص حول صورة في مستند PDF؟

ج: يؤدي وضع نص حول صورة إلى تحسين العرض المرئي لمستندات PDF الخاصة بك، مما يجعلها أكثر جاذبية وغنية بالمعلومات. تُستخدم هذه التقنية غالبًا في المستندات والكتيبات والتقارير والمواد الأخرى التي تريد دمج الصور والنصوص فيها بطريقة جمالية ممتعة.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه.

#### س: كيف أقوم بإنشاء جدول وإضافة صورة إليه؟

 ج: يرشدك البرنامج التعليمي خلال عملية إنشاء جدول باستخدام`Table` فئة وإضافة صورة إلى الجدول باستخدام`Image` فصل. ستحدد مسار ملف الصورة وارتفاعه وعرضه قبل إضافته إلى خلية جدول.

#### س: كيف يمكنني وضع النص حول الصورة؟

 ج: لتحديد موضع النص حول الصورة، ستقوم بإنشاء نص بتنسيق HTML باستخدام`HtmlFragment` فصل. سيحتوي هذا النص على عنوان ونص أساسي. ستقوم بعد ذلك بإضافة نص HTML هذا إلى خلية جدول مجاورة لخلية الصورة.

#### س: هل يمكنني تخصيص مظهر النص والصورة؟

ج: نعم، يمكنك تخصيص مظهر النص والصورة باستخدام علامات HTML وخصائصها. على سبيل المثال، يمكنك تعيين أحجام الخطوط والألوان والأنماط والمحاذاة للنص. بالإضافة إلى ذلك، يمكنك ضبط حجم وأبعاد الصورة.

#### س: كيف أحفظ وثيقة PDF؟

 ج: بعد إضافة الصورة والنص إلى الجدول، يمكنك حفظ مستند PDF باستخدام الملف`Save` طريقة`Document` فصل. قم بتوفير مسار ملف الإخراج المطلوب كوسيطة لملف`Save` طريقة.

#### س: ما هو الناتج المتوقع من هذا البرنامج التعليمي؟

ج: باتباع البرنامج التعليمي وتنفيذ كود C# المقدم، سوف تقوم بإنشاء مستند PDF يوضح كيفية وضع نص حول الصورة. سيحتوي مستند الإخراج على جدول يحتوي على صورة ونص حوله.

#### س: هل يمكنني استخدام تنسيقات صور مختلفة غير JPG؟

 ج: نعم، يمكنك استخدام تنسيقات صور مختلفة تدعمها مكتبة Aspose.PDF، مثل PNG وBMP وGIF والمزيد. عند إنشاء`Image` كائن، حدد مسار الملف لتنسيق الصورة المطلوب.

#### س: هل يلزم وجود ترخيص Aspose صالح لهذا البرنامج التعليمي؟

ج: نعم، يلزم وجود ترخيص Aspose صالح حتى يعمل هذا البرنامج التعليمي بشكل صحيح. يمكنك شراء ترخيص كامل أو الحصول على ترخيص مؤقت لمدة 30 يومًا من موقع Aspose.