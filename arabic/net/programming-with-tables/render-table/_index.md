---
title: عرض الجدول في مستند PDF
linktitle: عرض الجدول في مستند PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية عرض جدول في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 170
url: /ar/net/programming-with-tables/render-table/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة لعرض جدول في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه.

## الخطوة الأولى: إنشاء المستند
أولاً ، سننشئ مستند PDF جديدًا:

```csharp
// المسار إلى دليل المستندات
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء مستند جديد
Document doc = new Document();
```

## الخطوة 2: تكوين هوامش الصفحة والاتجاه
بعد ذلك ، سنقوم بتهيئة هوامش الصفحة وضبط الاتجاه على الوضع الأفقي:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## الخطوة 3: إنشاء الجدول والأعمدة
لنقم الآن بإنشاء جدول وتعيين عرض العمود:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## الخطوة 4: أضف صفوفًا وخلايا إلى الجدول
بعد ذلك ، سنضيف صفوفًا وخلايا إلى الجدول باستخدام حلقة:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## الخطوة 5: إضافة الجدول إلى الصفحة
لنقم الآن بإضافة الجدول إلى صفحة المستند:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## الخطوة 6: عرض الجدول على صفحة جديدة
بعد ذلك ، سننشئ جدولًا جديدًا ونضبط خاصية "IsInNewPage" على "true" لعرض الجدول في صفحة جديدة:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## الخطوة 7: احفظ ملف PDF
أخيرًا ، نحفظ مستند PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### مثال على التعليمات البرمجية المصدر لجدول العرض باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// الصفحة المضافة.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// أريد الاحتفاظ بالجدول 1 في الصفحة التالية من فضلك ...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية عرض جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح لك هذا الدليل التفصيلي كيفية إنشاء مستند وتكوين هوامش الصفحة والاتجاه وإضافة جدول وعرض جدول على صفحة جديدة. الآن يمكنك تطبيق هذه المعرفة على مشاريعك الخاصة.

### الأسئلة الشائعة حول جدول العرض في مستند PDF

#### س: كيف يمكنني تعديل مظهر الجدول ، مثل تغيير ألوان الخلية أو إضافة حدود؟

ج: لتعديل مظهر الجدول ، يمكنك تعيين خصائص متنوعة لـ`Aspose.Pdf.Table` وخلاياه. على سبيل المثال ، يمكنك ضبط ملف`BackgroundColor` خاصية الخلايا لتغيير لون خلفيتها. يمكنك أيضًا ضبط ملف`Border` خاصية الجدول أو الخلايا الفردية لإضافة حدود. بالإضافة إلى ذلك ، يمكنك تخصيص الخط ولون النص ومحاذاة محتوى الجدول عن طريق تعديل`TextState` التابع`TextFragment` كائنات مضافة إلى الخلايا.

#### س: هل يمكنني إضافة رؤوس أو تذييلات إلى الجدول؟

ج: نعم ، يمكنك إضافة رؤوس أو تذييلات إلى الجدول عن طريق إنشاء صفوف إضافية في بداية أو نهاية الجدول وتعيين المحتوى المناسب في الخلايا. يمكنك تخصيص الرؤوس أو التذييلات بشكل مستقل عن باقي محتويات الجدول عن طريق إضافة أنماط أو محتوى مختلف إلى هذه الصفوف المحددة.

#### س: كيف يمكنني التحكم في موضع الجدول على الصفحة؟

 ج: للتحكم في موضع الجدول على الصفحة ، يمكنك ضبط ملف`MarginInfo` التابع`PageInfo` هدف. ال`MarginInfo`يسمح لك بتعيين الهوامش اليسرى واليمنى والعلوية والسفلية للصفحة ، مما يؤثر على المساحة المتاحة للجدول. يمكنك أيضًا استخدام ملف`PositioningType` ممتلكات`Aspose.Pdf.Table` للتحكم في المحاذاة الأفقية والعمودية داخل منطقة محتوى الصفحة.

#### س: هل يمكنني تصدير الجدول إلى تنسيقات ملفات مختلفة ، مثل Excel أو CSV؟

ج: تم تصميم Aspose.PDF for .NET بشكل أساسي للعمل مع مستندات PDF. بينما يمكنه تصدير مستند PDF كصورة أو XPS ، فإنه لا يدعم جداول التصدير مباشرة إلى تنسيقات مثل Excel أو CSV. لتصدير بيانات الجدول إلى تنسيقات ملفات مختلفة ، قد تحتاج إلى استخدام مكتبات أو طرق إضافية لتحويل محتوى PDF إلى التنسيق المطلوب.

#### س: كيف يمكنني إضافة ارتباطات تشعبية إلى خلايا الجدول؟

 ج: لإضافة ارتباطات تشعبية إلى خلايا الجدول ، يمكنك استخدام الامتداد`Aspose.Pdf.WebHyperlink` class لإنشاء ارتباط تشعبي ثم إضافته كمرساة إلى ملف`TextFragment`داخل الخلية. يسمح لك هذا بربط عنوان URL أو هدف الارتباط بنص أو محتوى معين داخل الخلية ، وإنشاء ارتباطات تشعبية قابلة للنقر.