---
title: الهوامش أو الحشو
linktitle: الهوامش أو الحشو
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين الهوامش أو المساحة المتروكة في جدول باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 140
url: /ar/net/programming-with-tables/margins-or-padding/
---
في هذا البرنامج التعليمي، سنرشدك خلال عملية خطوة بخطوة لاستخدام Aspose.PDF لـ .NET لتعيين الهوامش أو المساحة المتروكة في الجدول. سنقدم توضيحات ومقتطفات من التعليمات البرمجية لمساعدتك على فهم هذه الوظيفة وتنفيذها في كود مصدر C# الخاص بك.

## الخطوة 1: إعداد الوثيقة والصفحة
للبدء، تحتاج إلى إعداد المستند والصفحة باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بإنشاء مثيل لكائن المستند عن طريق استدعاء المُنشئ الفارغ الخاص به
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 2: إنشاء جدول
بعد ذلك، سنقوم بإنشاء كائن جدول باستخدام فئة Aspose.Pdf.Table:

```csharp
// إنشاء مثيل لكائن الجدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// إضافة الجدول إلى مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(tab1);
```

## الخطوة 3: تحديد عرض الأعمدة وحدود الخلية الافتراضية
لتعيين عرض الأعمدة وحدود الخلية الافتراضية للجدول، استخدم الكود التالي:

```csharp
// قم بتعيين عرض أعمدة الجدول
tab1. ColumnWidths = "50 50 50";
// قم بتعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## الخطوة 4: تعيين حدود الجدول وحشو الخلية
لتعيين حدود الجدول ومساحة الخلية، قم بإنشاء كائن MarginInfo وقم بتعيين خصائصه:

```csharp
// قم بإنشاء كائن MarginInfo وقم بتعيين هوامشه اليسرى والسفلى واليمنى والعليا
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// قم بتعيين حشوة الخلية الافتراضية لكائن MarginInfo
tab1. DefaultCellPadding = margin;

// قم بتعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## الخطوة 5: إضافة الصفوف والخلايا
الآن، دعونا نضيف صفوفًا وخلايا إلى الجدول. سنقوم بإنشاء صف جديد وإضافة خلايا إليه:

```csharp
// قم بإنشاء صفوف في الجدول ثم خلايا في الصفوف
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
لحفظ مستند PDF استخدم الكود التالي:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### مثال على التعليمات البرمجية المصدر للهوامش أو الحشو باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بإنشاء كائن المستند عن طريق استدعاء المُنشئ الفارغ الخاص به
Document doc = new Document();
Page page = doc.Pages.Add();
// إنشاء مثيل لكائن الجدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// إضافة الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(tab1);
// تعيين مع عرض أعمدة الجدول
tab1.ColumnWidths = "50 50 50";
// قم بتعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// قم بتعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// قم بإنشاء كائن MarginInfo وقم بتعيين الهوامش اليسرى والسفلى واليمنى والعليا
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// قم بتعيين حشوة الخلية الافتراضية لكائن MarginInfo
tab1.DefaultCellPadding = margin;
// قم بإنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 بسلسلة نصية كبيرة ليتم وضعها داخل الخلية");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
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
تهانينا! لقد تعلمت بنجاح كيفية تعيين الهوامش أو المساحة المتروكة في جدول باستخدام Aspose.PDF لـ .NET. ستساعدك هذه المعرفة على تحسين قدرات تنسيق المستندات لديك وجعل جداولك جذابة بصريًا.

### الأسئلة الشائعة

#### س: هل يمكنني تعيين هوامش أو حشوات مختلفة للخلايا الفردية في الجدول؟

ج: نعم، يمكنك تعيين هوامش أو مساحة حشو مختلفة للخلايا الفردية في جدول باستخدام Aspose.PDF لـ .NET. في المثال المقدم، قمنا بتعيين حشوة الخلية الافتراضية للجدول بأكمله باستخدام`DefaultCellPadding` ملكية. لتعيين حشوة مختلفة لخلايا معينة، يمكنك الوصول إلى`MarginInfo` لكل خلية على حدة وتعديل هوامشها.

#### س: كيف يمكنني تغيير لون حدود الجدول أو نمطه؟

 ج: لتغيير لون حدود الجدول أو نمطه، يمكنك تعديل`Color` و`Width` خصائص`BorderInfo` هدف. في المثال الموضح، قمنا بتعيين لون الحدود إلى اللون الأسود وعرض 1F (نقطة واحدة) باستخدام`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. يمكنك ضبط اللون والعرض حسب متطلباتك.

#### س: هل من الممكن إضافة رؤوس أو تذييلات إلى الجدول؟

ج: نعم، يمكنك إضافة رؤوس أو تذييلات إلى الجدول باستخدام Aspose.PDF لـ .NET. عادةً ما تكون الرؤوس والتذييلات عبارة عن صفوف منفصلة تحتوي على معلومات إضافية مثل تسميات الأعمدة أو عناوين الجداول أو بيانات التلخيص. يمكنك إنشاء صفوف إضافية وتصميمها بشكل مختلف وإضافتها أعلى محتوى الجدول أو أسفله.

#### س: كيف يمكنني ضبط محاذاة النص داخل خلية جدول؟

 ج: لضبط محاذاة النص داخل خلية جدول، يمكنك استخدام الخيار`HorizontalAlignment` و`VerticalAlignment` خصائص`TextFragment` هدف. على سبيل المثال، يمكنك ضبط النص لمحاذاة النص أفقيًا إلى المنتصف`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . وبالمثل، يمكنك تعيين`mytext.VerticalAlignment` للتحكم في المحاذاة العمودية.

#### س: هل يمكنني إضافة صور إلى خلايا الجدول بدلاً من النص؟

 ج: نعم، يمكنك إضافة صور إلى خلايا الجدول باستخدام Aspose.PDF لـ .NET. بدلاً من إنشاء`TextFragment` كائن، يمكنك إنشاء`Image` الكائن، وقم بتحميل ملف الصورة، ثم قم بإضافته إلى الخلية المطلوبة باستخدام الملف`cell.Paragraphs.Add(image);` طريقة. يتيح لك ذلك إدراج صور في الجدول إلى جانب محتوى النص.