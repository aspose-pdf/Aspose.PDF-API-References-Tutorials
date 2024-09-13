---
title: وضع نص حول الصورة في ملف PDF
linktitle: وضع نص حول الصورة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية وضع النص حول الصورة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 260
url: /ar/net/programming-with-text/placing-text-around-image/
---
في هذا البرنامج التعليمي، سنشرح كيفية وضع نص حول صورة في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتناول العملية خطوة بخطوة لإنشاء جدول وإضافة صورة ووضع نص حول الصورة باستخدام كود المصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت مكتبة Aspose.PDF لـ .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وصفحة

 بعد ذلك، نقوم بإنشاء`Document` الكائن وإضافة صفحة إليه باستخدام`Pages.Add()` طريقة.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء جدول

 نقوم بإنشاء جدول باستخدام`Table` الصف وإضافته إلى مجموعة الفقرات الخاصة بالصفحة.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## الخطوة 4: تعيين عرض أعمدة الجدول وحوافها

 نقوم بتعيين عرض الأعمدة في الجدول وإنشاء`MarginInfo` كائن لتعيين الهوامش.

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

 نحن ننشئ`Image` الكائن، حدد مسار ملف الصورة، وقم بتعيين الارتفاع والعرض الثابتين للصورة. ثم نضيف الصورة إلى مجموعة الفقرات في خلية الجدول.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## الخطوة 6: إضافة نص حول الصورة

 نقوم بإنشاء متغيرات سلسلة تحتوي على نص بتنسيق HTML وننشئ`HtmlFragment`الكائن. ثم نضيف نص HTML إلى خلية الجدول التي تحتوي على الصورة.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## الخطوة 7: إضافة نص إضافي

 نحن نخلق آخر`HtmlFragment` الكائن الذي يحتوي على نص إضافي بتنسيق HTML وإضافته إلى خلية جدول منفصلة.

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

### نموذج لمصدر الكود لوضع النص حول الصورة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// إنشاء صفحة في ملف Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// إنشاء كائن جدول
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// أضف الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(table1);
// مجموعة مع عرض أعمدة الجدول
table1.ColumnWidths = "120 270";
// إنشاء كائن MarginInfo وتعيين هوامشه اليسرى والسفلى واليمنى والعلوية
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// تعيين الحشو الافتراضي للخلية إلى كائن MarginInfo
table1.DefaultCellPadding = margin;
// إنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row row1 = table1.Rows.Add();
// إنشاء كائن صورة
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// حدد مسار ملف الصورة
logo.File = dataDir + "aspose-logo.jpg";
// حدد ارتفاع الصورة الثابت
logo.FixHeight = 120;
// حدد عرض الصورة الثابت
logo.FixWidth = 110;
row1.Cells.Add();
// إضافة الصورة إلى مجموعة فقرات خلية الجدول
row1.Cells[0].Paragraphs.Add(logo);
// إنشاء متغيرات سلسلة تحتوي على نص يحتوي على علامات HTML
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//إنشاء كائن نصي لإضافته إلى يمين الصورة
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// أضف فقرات النص التي تحتوي على نص HTML إلى خلية الجدول
row1.Cells[1].Paragraphs.Add(TitleText);
// تعيين المحاذاة الرأسية لمحتويات الصف على أعلى
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//إنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// تعيين قيمة امتداد الصف للصف الثاني على 2
SecondRow.Cells[0].ColSpan = 2;
// اضبط المحاذاة الرأسية للصف الثاني على أعلى
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// أضف فقرات النص التي تحتوي على نص HTML إلى خلية الجدول
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// حفظ ملف PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية وضع نص حول صورة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك إنشاء جدول وإضافة صورة ووضع نص حول الصورة في مستند PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "وضع النص حول الصورة في ملف PDF"؟

ج: يوضح البرنامج التعليمي "وضع نص حول صورة في ملف PDF" كيفية استخدام مكتبة Aspose.PDF لـ .NET لوضع نص حول صورة في مستند PDF. يوفر البرنامج التعليمي دليلاً خطوة بخطوة وكود مصدر C# لمساعدتك في إنشاء جدول وإضافة صورة ووضع نص حول الصورة.

#### س: لماذا أرغب في وضع نص حول صورة في مستند PDF؟

ج: إن وضع نص حول صورة يعزز العرض المرئي لمستندات PDF الخاصة بك، مما يجعلها أكثر جاذبية وإفادة. تُستخدم هذه التقنية غالبًا في المستندات والكتيبات والتقارير والمواد الأخرى حيث تريد الجمع بين الصور والنص بطريقة جمالية ممتعة.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: كيف أقوم بإنشاء جدول وإضافة صورة إليه؟

 أ: يرشدك البرنامج التعليمي خلال عملية إنشاء جدول باستخدام`Table` الصف وإضافة صورة إلى الجدول باستخدام`Image` ستقوم بتحديد مسار ملف الصورة والارتفاع والعرض قبل إضافتها إلى خلية الجدول.

#### س: كيف أقوم بوضع النص حول الصورة؟

 أ: لوضع النص حول الصورة، ستقوم بإنشاء نص بتنسيق HTML باستخدام`HtmlFragment` سيحتوي هذا النص على عنوان ونص أساسي. ثم ستضيف نص HTML هذا إلى خلية جدول مجاورة لخلية الصورة.

#### س: هل يمكنني تخصيص مظهر النص والصورة؟

ج: نعم، يمكنك تخصيص مظهر النص والصورة باستخدام علامات وخصائص HTML. على سبيل المثال، يمكنك تعيين أحجام الخطوط والألوان والأنماط ومحاذاة النص. بالإضافة إلى ذلك، يمكنك ضبط حجم وأبعاد الصورة.

#### س: كيف أحفظ مستند PDF؟

 ج: بعد إضافة الصورة والنص إلى الجدول، يمكنك حفظ مستند PDF باستخدام`Save` طريقة`Document` الفئة. قم بتوفير مسار ملف الإخراج المطلوب كحجة لـ`Save` طريقة.

#### س: ما هي النتيجة المتوقعة من هذا البرنامج التعليمي؟

ج: باتباع البرنامج التعليمي وتنفيذ الكود C# المقدم، ستتمكن من إنشاء مستند PDF يوضح كيفية وضع نص حول صورة. سيحتوي المستند الناتج على جدول يحتوي على صورة ونص حوله.

#### س: هل يمكنني استخدام تنسيقات صور مختلفة غير JPG؟

 ج: نعم، يمكنك استخدام تنسيقات الصور المختلفة التي تدعمها مكتبة Aspose.PDF، مثل PNG وBMP وGIF والمزيد. عند إنشاء`Image` الكائن، حدد مسار الملف لتنسيق الصورة المطلوب.

#### س: هل يلزم الحصول على ترخيص Aspose صالح لهذا البرنامج التعليمي؟

ج: نعم، يلزم الحصول على ترخيص Aspose صالح حتى يعمل هذا البرنامج التعليمي بشكل صحيح. يمكنك شراء ترخيص كامل أو الحصول على ترخيص مؤقت لمدة 30 يومًا من موقع Aspose على الويب.