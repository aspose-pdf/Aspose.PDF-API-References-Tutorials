---
title: الهوامش أو الحشو
linktitle: الهوامش أو الحشو
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تعيين الهوامش أو الحشو في جدول باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 140
url: /ar/net/programming-with-tables/margins-or-padding/
---
في هذا البرنامج التعليمي، سنرشدك خلال عملية خطوة بخطوة لاستخدام Aspose.PDF لـ .NET لتعيين الهوامش أو الحشو في جدول. وسنقدم تفسيرات ومقاطع تعليمات برمجية لمساعدتك على فهم هذه الوظيفة وتنفيذها في كود المصدر C# الخاص بك.

## الخطوة 1: إعداد المستند والصفحة
للبدء، يجب عليك إعداد المستند والصفحة باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن المستند عن طريق استدعاء المنشئ الفارغ الخاص به
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 2: إنشاء جدول
بعد ذلك، سنقوم بإنشاء كائن جدول باستخدام فئة Aspose.Pdf.Table:

```csharp
// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// أضف الجدول إلى مجموعة الفقرات الخاصة بالقسم المطلوب
page.Paragraphs.Add(tab1);
```

## الخطوة 3: تعيين عرض الأعمدة وحدود الخلية الافتراضية
لتعيين عرض الأعمدة وحدود الخلايا الافتراضية للجدول، استخدم الكود التالي:

```csharp
// تعيين عرض الأعمدة في الجدول
tab1. ColumnWidths = "50 50 50";
// تعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## الخطوة 4: إعداد حدود الجدول وحشو الخلايا
لتعيين حدود الجدول وحشو الخلايا، قم بإنشاء كائن MarginInfo وتعيين خصائصه:

```csharp
// إنشاء كائن MarginInfo وتعيين هوامشه اليسرى والسفلى واليمنى والعلوية
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// تعيين الحشو الافتراضي للخلية إلى كائن MarginInfo
tab1. DefaultCellPadding = margin;

// تعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## الخطوة 5: إضافة الصفوف والخلايا
الآن، لنقم بإضافة صفوف وخلايا إلى الجدول. سنقوم بإنشاء صف جديد وإضافة خلايا إليه:

```csharp
// إنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## الخطوة 6: إضافة نص إلى الخلايا
لإضافة نص إلى خلية، قم بإنشاء كائن TextFragment وأضفه إلى الخلية المطلوبة:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## الخطوة 7: حفظ ملف PDF
لحفظ مستند PDF، استخدم الكود التالي:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### مثال على كود المصدر للهوامش أو الحشو باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن المستند عن طريق استدعاء المنشئ الفارغ الخاص به
Document doc = new Document();
Page page = doc.Pages.Add();
// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// أضف الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(tab1);
// مجموعة مع عرض أعمدة الجدول
tab1.ColumnWidths = "50 50 50";
// تعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// تعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// إنشاء كائن MarginInfo وتعيين هوامشه اليسرى والسفلى واليمنى والعلوية
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// تعيين الحشو الافتراضي للخلية إلى كائن MarginInfo
tab1.DefaultCellPadding = margin;
// إنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 مع سلسلة نصية كبيرة ليتم وضعها داخل الخلية");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// الصف 1. الخلايا [2]. الفقرات [0]. العرض الثابت = 80؛
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## خاتمة
مبروك! لقد نجحت في تعلم كيفية تعيين الهوامش أو الحشو في جدول باستخدام Aspose.PDF لـ .NET. ستساعدك هذه المعرفة في تحسين قدرات تنسيق المستندات لديك وجعل جداولك جذابة بصريًا.

### الأسئلة الشائعة

#### س: هل يمكنني تعيين هوامش أو حشو مختلفة للخلايا الفردية في جدول؟

ج: نعم، يمكنك تعيين هوامش أو حشو مختلفين لخلايا فردية في جدول باستخدام Aspose.PDF لـ .NET. في المثال المقدم، قمنا بتعيين حشو الخلايا الافتراضي للجدول بأكمله باستخدام`DefaultCellPadding` الخاصية. لتعيين حشو مختلف لخلايا معينة، يمكنك الوصول إلى`MarginInfo` لكل خلية على حدة وتعديل هوامشها.

#### س: كيف يمكنني تغيير لون حدود الجدول أو نمطه؟

 أ: لتغيير لون حدود الجدول أو نمطه، يمكنك تعديل`Color` و`Width` خصائص`BorderInfo` الكائن. في المثال الموضح، قمنا بتعيين لون الحدود إلى الأسود وعرض 1F (نقطة واحدة) باستخدام`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`يمكنك تعديل اللون والعرض حسب متطلباتك.

#### س: هل من الممكن إضافة رؤوس أو تذييلات للجدول؟

ج: نعم، يمكنك إضافة رؤوس أو تذييلات إلى الجدول باستخدام Aspose.PDF لـ .NET. عادةً ما تكون الرؤوس والتذييلات عبارة عن صفوف منفصلة تحتوي على معلومات إضافية مثل تسميات الأعمدة أو عناوين الجداول أو بيانات الملخص. يمكنك إنشاء صفوف إضافية وتصميمها بشكل مختلف وإضافتها أعلى أو أسفل محتوى الجدول.

#### س: كيف أقوم بتعديل محاذاة النص داخل خلية الجدول؟

 أ: لضبط محاذاة النص داخل خلية الجدول، يمكنك استخدام`HorizontalAlignment` و`VerticalAlignment` خصائص`TextFragment` الكائن. على سبيل المثال، لمحاذاة النص أفقيًا في المنتصف، يمكنك ضبط`mytext.HorizontalAlignment = HorizontalAlignment.Center;` وبالمثل، يمكنك ضبط`mytext.VerticalAlignment` للتحكم في المحاذاة العمودية.

#### س: هل يمكنني إضافة الصور إلى خلايا الجدول بدلاً من النص؟

 ج: نعم، يمكنك إضافة صور إلى خلايا الجدول باستخدام Aspose.PDF لـ .NET. بدلاً من إنشاء`TextFragment` الكائن، يمكنك إنشاء`Image` الكائن، قم بتحميل ملف الصورة، وأضفه إلى الخلية المطلوبة باستخدام`cell.Paragraphs.Add(image);` هذه الطريقة تسمح لك بإدراج الصور في الجدول إلى جانب محتوى النص.