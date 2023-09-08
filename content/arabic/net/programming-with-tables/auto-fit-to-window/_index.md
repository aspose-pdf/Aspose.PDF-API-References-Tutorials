---
title: احتواء تلقائي للنافذة
linktitle: احتواء تلقائي للنافذة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستخدام Aspose.PDF لـ .NET وتحقيق الملاءمة التلقائية للنافذة في إنشاء PDF.
type: docs
weight: 50
url: /ar/net/programming-with-tables/auto-fit-to-window/
---
المقالة التالية عبارة عن دليل خطوة بخطوة حول كيفية استخدام التعليمات البرمجية المصدر لـ C# المتوفرة لتحقيق وظيفة Auto Fit To Window باستخدام مكتبة Aspose.PDF لـ .NET. تتيح لك وظيفة Auto Fit To Window إنشاء ملفات PDF بتخطيط ملائم لنافذة العرض. تعد هذه الميزة مفيدة بشكل خاص عندما تريد أن يتم ضبط مستند PDF الخاص بك تلقائيًا على حجم نافذة قارئ PDF التي يستخدمها المستخدم.

## الخطوة 1: إعداد البيئة

قبل البدء، تحتاج إلى تثبيت مكتبة Aspose.PDF لـ .NET على جهازك. تأكد أيضًا من استيراد مساحات الأسماء الضرورية إلى مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند PDF

 للبدء، تحتاج إلى إنشاء`Document` كائن عن طريق استدعاء المنشئ الافتراضي الخاص به.

```csharp
Document doc = new Document();
```

 بعد ذلك، قم بإنشاء قسم في`Pdf` هدف.

```csharp
Page sec1 = doc.Pages.Add();
```

## الخطوة 3: إضافة جدول إلى المستند

 في هذه الخطوة، سنقوم بإضافة جدول إلى مستند PDF الخاص بنا. قم أولاً بإنشاء أ`Table` هدف.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

بعد ذلك، أضف الجدول إلى مجموعة فقرات القسم.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  الخطوة 4: تخصيص مظهر الجدول

يمكنك تخصيص مظهر الجدول عن طريق تعيين خصائص مثل حدود الخلايا والهامش.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  الخطوة 4: إضافة صفوف وخلايا إلى الجدول

الآن دعونا نضيف صفوفًا وخلايا إلى طاولتنا. ابدأ بإنشاء صف وإضافة خلايا إلى هذا الصف.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## الخطوة 5: حفظ المستند

وأخيرًا، حدد مسار ملف الإخراج واحفظ المستند.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### مثال على التعليمات البرمجية المصدر للملاءمة التلقائية للنافذة باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بإنشاء كائن Pdf عن طريق استدعاء المُنشئ الفارغ الخاص به
Document doc = new Document();
// قم بإنشاء القسم في كائن Pdf
Page sec1 = doc.Pages.Add();

// إنشاء مثيل لكائن الجدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// إضافة الجدول في مجموعة فقرات القسم المطلوب
sec1.Paragraphs.Add(tab1);

// تعيين مع عرض أعمدة الجدول
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

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
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// حفظ المستند المحدث الذي يحتوي على كائن الجدول
doc.Save(dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.PDF لـ .NET لإنشاء ملف PDF باستخدام ميزة Auto Fit To Window. تعد هذه الميزة مفيدة للغاية عندما تريد أن يتم ضبط مستند PDF الخاص بك تلقائيًا على حجم نافذة العرض. يوفر Aspose.PDF for .NET العديد من الميزات القوية الأخرى لإنشاء ملفات PDF ومعالجتها. أنا أشجعك على استكشاف هذه المكتبة بشكل أكبر لاكتشاف كل إمكانياتها.

### الأسئلة الشائعة

#### س: ما هو الغرض من ميزة Auto Fit To Window في إنشاء PDF؟

ج: تضمن ميزة Auto Fit To Window في إنشاء PDF أن يتم ضبط تخطيط مستند PDF تلقائيًا حسب حجم نافذة قارئ PDF التي يستخدمها المستخدم. وهذا يسمح بمشاهدة أفضل ويضمن أن المحتوى يتناسب تمامًا مع منطقة العرض المتاحة.

#### س: هل يمكنني تخصيص مظهر الجدول، مثل حجم الخط والألوان؟

ج: نعم، يمكنك تخصيص مظهر الجدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح مقتطف التعليمات البرمجية المقدم كيفية تعيين خصائص مثل حدود الخلايا والهوامش وعرض الأعمدة. يمكنك أيضًا تخصيص حجم الخط والألوان وجوانب التصميم الأخرى للجدول ومحتواه.

#### س: كيف يمكنني دمج Aspose.PDF لـ .NET في مشروع C# الخاص بي؟

ج: لاستخدام Aspose.PDF لـ .NET في مشروع C# الخاص بك، تحتاج أولاً إلى تثبيت مكتبة Aspose.PDF لـ .NET على جهازك. وبعد ذلك، يمكنك إضافة مرجع إلى المكتبة في مشروع C# الخاص بك. وأخيرًا، قم باستيراد مساحات الأسماء الضرورية للوصول إلى الفئات والأساليب التي يوفرها Aspose.PDF لـ .NET.

#### س: هل يتوافق Aspose.PDF for .NET مع تطبيقات .NET Core؟

ج: نعم، Aspose.PDF for .NET متوافق مع تطبيقات .NET Core. وهو يدعم العديد من منصات .NET، بما في ذلك .NET Framework و.NET Core و.NET 5.0+.

#### س: هل يمكنني إضافة المزيد من الجداول إلى مستند PDF؟

ج: نعم، يمكنك إضافة جداول متعددة إلى مستند PDF باتباع خطوات مماثلة كما هو موضح في مقتطف التعليمات البرمجية. ما عليك سوى إنشاء مثيلات جديدة لـ`Aspose.Pdf.Table` الفصل وإضافتها إلى أقسام أو صفحات مختلفة من مستند PDF.