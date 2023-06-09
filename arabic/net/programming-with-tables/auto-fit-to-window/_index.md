---
title: احتواء تلقائي للنافذة
linktitle: احتواء تلقائي للنافذة
second_title: Aspose.PDF لمرجع .NET API
description: دليل تفصيلي خطوة بخطوة لاستخدام Aspose.PDF لـ .NET وتحقيق التوافق التلقائي مع النافذة في إنشاء PDF.
type: docs
weight: 50
url: /ar/net/programming-with-tables/auto-fit-to-window/
---

المقالة التالية عبارة عن دليل مفصل خطوة بخطوة حول كيفية استخدام كود المصدر C # المتوفر لتحقيق وظيفة Auto Fit To Window باستخدام مكتبة Aspose.PDF لـ .NET. تتيح لك وظيفة Auto Fit To Window إنشاء ملفات PDF بتنسيق يتلاءم مع نافذة العرض. هذه الميزة مفيدة بشكل خاص عندما تريد أن يتكيف مستند PDF تلقائيًا مع حجم نافذة قارئ PDF التي يستخدمها المستخدم.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تحتاج إلى تثبيت مكتبة Aspose.PDF لـ .NET على جهازك. تأكد أيضًا من استيراد مساحات الأسماء الضرورية إلى مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند PDF

 للبدء ، تحتاج إلى إنشاء ملف`Document` الكائن عن طريق استدعاء المُنشئ الافتراضي الخاص به.

```csharp
Document doc = new Document();
```

 بعد ذلك ، قم بإنشاء قسم في ملف`Pdf` هدف.

```csharp
Page sec1 = doc.Pages.Add();
```

## الخطوة 3: إضافة جدول إلى المستند

 في هذه الخطوة ، سنقوم بإضافة جدول إلى مستند PDF الخاص بنا. قم أولاً بإنشاء ملف`Table` هدف.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

بعد ذلك ، أضف الجدول إلى مجموعة فقرات القسم.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  الخطوة 4: تخصيص مظهر الجدول

يمكنك تخصيص مظهر الجدول عن طريق تعيين خصائص مثل حدود الخلية والهامش.

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

لنقم الآن بإضافة صفوف وخلايا إلى طاولتنا. ابدأ بإنشاء صف وإضافة خلايا إلى هذا الصف.

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

أخيرًا ، حدد مسار ملف الإخراج واحفظ المستند.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### مثال على كود المصدر لـ Auto Fit To Window باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتأسيس كائن Pdf عن طريق استدعاء المُنشئ الفارغ الخاص به
Document doc = new Document();
// أنشئ المقطع في كائن Pdf
Page sec1 = doc.Pages.Add();

// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// أضف الجدول في مجموعة فقرات القسم المطلوب
sec1.Paragraphs.Add(tab1);

// اضبط مع عرض أعمدة الجدول
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

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
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// احفظ المستند المحدث الذي يحتوي على كائن جدول
doc.Save(dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية استخدام Aspose.PDF for .NET لإنشاء ملف PDF باستخدام ميزة Auto Fit To Window. هذه الميزة مفيدة للغاية عندما تريد أن يتكيف مستند PDF تلقائيًا مع حجم نافذة العرض. يوفر Aspose.PDF for .NET العديد من الميزات القوية الأخرى لإنشاء ملفات PDF ومعالجتها. أنا أشجعك على استكشاف هذه المكتبة بشكل أكبر لاكتشاف جميع إمكانياتها.