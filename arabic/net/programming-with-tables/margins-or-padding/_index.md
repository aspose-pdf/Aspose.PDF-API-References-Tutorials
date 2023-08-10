---
title: الهوامش أو الحشو
linktitle: الهوامش أو الحشو
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين الهوامش أو الحشو في جدول باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 140
url: /ar/net/programming-with-tables/margins-or-padding/
---
في هذا البرنامج التعليمي ، سنوجهك خلال العملية خطوة بخطوة لاستخدام Aspose.PDF لـ .NET لتعيين الهوامش أو الحشو في جدول. سنقدم تفسيرات ومقتطفات التعليمات البرمجية لمساعدتك على فهم هذه الوظيفة وتنفيذها في شفرة مصدر C #.

## الخطوة 1: إعداد المستند والصفحة
للبدء ، تحتاج إلى إعداد المستند والصفحة باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن المستند عن طريق استدعاء المُنشئ الفارغ الخاص به
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 2: إنشاء الجدول
بعد ذلك ، سننشئ كائن جدول باستخدام فئة Aspose.Pdf.Table:

```csharp
// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// أضف الجدول إلى مجموعة الفقرات للقسم المطلوب
page.Paragraphs.Add(tab1);
```

## الخطوة 3: تعيين عرض العمود وحدود الخلية الافتراضية
لتعيين عرض العمود وحدود الخلية الافتراضية للجدول ، استخدم التعليمات البرمجية التالية:

```csharp
// اضبط عرض أعمدة الجدول
tab1. ColumnWidths = "50 50 50";
// عيّن حد الخلية الافتراضي باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## الخطوة 4: إعداد حدود الجدول وحشو الخلية
لتعيين حدود الجدول وحشو الخلية ، أنشئ كائن MarginInfo وعيّن خصائصه:

```csharp
// قم بإنشاء كائن MarginInfo وقم بتعيين هوامشه اليسرى ، والسفلية ، واليمنى ، والعليا
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// قم بتعيين مساحة الخلية الافتراضية إلى كائن MarginInfo
tab1. DefaultCellPadding = margin;

// قم بتعيين حد الجدول باستخدام كائن BorderInfo مخصص آخر
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## الخطوة 5: إضافة صفوف وخلايا
الآن ، دعنا نضيف صفوفًا وخلايا إلى الجدول. سننشئ صفًا جديدًا ونضيف خلايا إليه:

```csharp
// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## الخطوة 6: إضافة نص إلى الخلايا
لإضافة نص إلى خلية ، قم بإنشاء كائن TextFragment وأضفه إلى الخلية المطلوبة:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## الخطوة 7: حفظ ملف PDF
لحفظ مستند PDF ، استخدم الكود التالي:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### مثال على شفرة المصدر لـ Margins Or Padding باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتأسيس كائن المستند عن طريق استدعاء المُنشئ الفارغ الخاص به
Document doc = new Document();
Page page = doc.Pages.Add();
// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// أضف الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(tab1);
// اضبط مع عرض أعمدة الجدول
tab1.ColumnWidths = "50 50 50";
// تعيين حد الخلية الافتراضي باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// قم بتعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// قم بإنشاء كائن MarginInfo وقم بتعيين هوامشه اليسرى والسفلية واليمنى والعليا
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// قم بتعيين مساحة الخلية الافتراضية إلى كائن MarginInfo
tab1.DefaultCellPadding = margin;
// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add ("وضع col3 بسلسلة نصية كبيرة داخل الخلية")؛
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells [2] .Paragraphs [0] .FixedWidth = 80 ؛
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
تهانينا! لقد تعلمت بنجاح كيفية تعيين الهوامش أو الحشو في جدول باستخدام Aspose.PDF لـ .NET. ستساعدك هذه المعرفة على تحسين إمكانات تنسيق المستندات وتجعل جداولك جذابة بصريًا.

### التعليمات

#### س: هل يمكنني تعيين هوامش أو حشوة مختلفة لخلايا فردية في جدول؟

ج: نعم ، يمكنك تعيين هوامش أو حشوة مختلفة للخلايا الفردية في جدول باستخدام Aspose.PDF لـ .NET. في المثال المقدم ، قمنا بتعيين مساحة الخلية الافتراضية للجدول بأكمله باستخدام`DefaultCellPadding` ملكية. لتعيين مساحة متروكة مختلفة لخلايا معينة ، يمكنك الوصول إلى ملف`MarginInfo` من كل خلية على حدة وتعديل هوامشها.

#### س: كيف يمكنني تغيير لون حدود الجدول أو نمطه؟

 ج: لتغيير لون حدود الجدول أو نمطه ، يمكنك تعديل ملف`Color` و`Width` خصائص`BorderInfo` هدف. في المثال المعطى ، قمنا بتعيين لون الحدود إلى الأسود وعرض 1F (نقطة واحدة) باستخدام`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. يمكنك ضبط اللون والعرض حسب متطلباتك.

#### س: هل يمكن إضافة رؤوس أو تذييلات إلى الجدول؟

ج: نعم ، يمكنك إضافة رؤوس أو تذييلات إلى الجدول باستخدام Aspose.PDF لـ .NET. عادةً ما تكون الرؤوس والتذييلات عبارة عن صفوف منفصلة تحتوي على معلومات إضافية مثل تسميات الأعمدة أو عناوين الجداول أو بيانات الملخص. يمكنك إنشاء صفوف إضافية وتصميمها بشكل مختلف وإضافتها أعلى أو أسفل محتوى الجدول.

#### س: كيف أقوم بضبط محاذاة النص داخل خلية جدول؟

 ج: لضبط محاذاة النص داخل خلية جدول ، يمكنك استخدام ملف`HorizontalAlignment` و`VerticalAlignment` خصائص`TextFragment` هدف. على سبيل المثال ، لمحاذاة النص أفقيًا للوسط ، يمكنك تعيين`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . وبالمثل ، يمكنك تعيين`mytext.VerticalAlignment` للتحكم في المحاذاة الرأسية.

#### س: هل يمكنني إضافة صور إلى خلايا الجدول بدلاً من النص؟

 ج: نعم ، يمكنك إضافة صور إلى خلايا الجدول باستخدام Aspose.PDF for .NET. بدلاً من إنشاء ملف`TextFragment` كائن ، يمكنك إنشاء`Image` الكائن ، قم بتحميل ملف الصورة ، وأضفه إلى الخلية المطلوبة باستخدام الامتداد`cell.Paragraphs.Add(image);` طريقة. يتيح لك ذلك إدراج الصور في الجدول جنبًا إلى جنب مع محتوى النص.