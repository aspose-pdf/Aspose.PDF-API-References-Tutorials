---
title: تقديم الجدول في وثيقة PDF
linktitle: تقديم الجدول في وثيقة PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية عرض جدول في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 170
url: /ar/net/programming-with-tables/render-table/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة لعرض جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه.

## الخطوة 1: إنشاء الوثيقة
أولاً، سنقوم بإنشاء مستند PDF جديد:

```csharp
// المسار إلى دليل المستندات
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء مستند جديد
Document doc = new Document();
```

## الخطوة 2: تكوين هوامش الصفحة واتجاهها
بعد ذلك، سنقوم بتكوين هوامش الصفحة وتعيين الاتجاه إلى الوضع الأفقي:

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
لنقم الآن بإنشاء جدول وضبط عرض الأعمدة:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## الخطوة 4: إضافة صفوف وخلايا إلى الجدول
بعد ذلك، سنقوم بإضافة صفوف وخلايا إلى الجدول باستخدام حلقة:

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
الآن دعونا نضيف الجدول إلى صفحة المستند:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## الخطوة 6: عرض الجدول في صفحة جديدة
بعد ذلك، سنقوم بإنشاء جدول جديد وتعيين خاصية "IsInNewPage" على "true" لعرض الجدول في صفحة جديدة:

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

## الخطوة 7: حفظ ملف PDF
وأخيرًا، نقوم بحفظ مستند PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### مثال على التعليمات البرمجية المصدر لـ Render Table باستخدام Aspose.PDF لـ .NET

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
// أريد الاحتفاظ بالجدول 1 في الصفحة التالية من فضلك...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية عرض جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح لك هذا الدليل خطوة بخطوة كيفية إنشاء مستند وتكوين هوامش الصفحة واتجاهها وإضافة جدول وعرض جدول في صفحة جديدة. الآن يمكنك تطبيق هذه المعرفة على مشاريعك الخاصة.

### الأسئلة الشائعة حول جدول العرض في مستند PDF

#### س: كيف يمكنني تعديل مظهر الجدول، مثل تغيير ألوان الخلايا أو إضافة حدود؟

ج: لتعديل مظهر الجدول، يمكنك تعيين خصائص مختلفة للجدول`Aspose.Pdf.Table` وخلاياه. على سبيل المثال، يمكنك ضبط`BackgroundColor` خاصية الخلايا لتغيير لون خلفيتها. يمكنك أيضًا ضبط`Border` خاصية الجدول أو الخلايا الفردية لإضافة الحدود. بالإضافة إلى ذلك، يمكنك تخصيص الخط ولون النص ومحاذاة محتوى الجدول عن طريق تعديل`TextState` التابع`TextFragment` الكائنات المضافة إلى الخلايا.

#### س: هل يمكنني إضافة رؤوس أو تذييلات إلى الجدول؟

ج: نعم، يمكنك إضافة رؤوس أو تذييلات إلى الجدول عن طريق إنشاء صفوف إضافية في بداية الجدول أو نهايته وتعيين المحتوى المناسب في الخلايا. يمكنك تخصيص الرؤوس أو التذييلات بشكل مستقل عن بقية محتوى الجدول عن طريق إضافة أنماط أو محتوى مختلف إلى هذه الصفوف المحددة.

#### س: كيف يمكنني التحكم في موضع الجدول في الصفحة؟

 ج: للتحكم في موضع الجدول في الصفحة، يمكنك ضبط`MarginInfo` التابع`PageInfo` هدف. ال`MarginInfo`يسمح لك بتعيين الهوامش اليسرى واليمنى والعلوية والسفلى للصفحة، مما يؤثر على المساحة المتوفرة للجدول. يمكنك أيضًا استخدام`PositioningType` ملكية`Aspose.Pdf.Table` للتحكم في محاذاتها الأفقية والرأسية داخل منطقة محتوى الصفحة.

#### س: هل يمكنني تصدير الجدول إلى تنسيقات ملفات مختلفة، مثل Excel أو CSV؟

ج: تم تصميم Aspose.PDF for .NET بشكل أساسي للعمل مع مستندات PDF. على الرغم من أنه يمكنه تصدير مستند PDF كصورة أو XPS، إلا أنه لا يدعم بشكل مباشر تصدير الجداول إلى تنسيقات مثل Excel أو CSV. لتصدير بيانات الجدول إلى تنسيقات ملفات مختلفة، قد تحتاج إلى استخدام مكتبات أو طرق إضافية لتحويل محتوى PDF إلى التنسيق المطلوب.

#### س: كيف يمكنني إضافة ارتباطات تشعبية إلى خلايا الجدول؟

 ج: لإضافة ارتباطات تشعبية إلى خلايا الجدول، يمكنك استخدام`Aspose.Pdf.WebHyperlink` فئة لإنشاء ارتباط تشعبي ثم إضافته كمرساة إلى ملف`TextFragment`داخل الخلية. يتيح لك ذلك ربط عنوان URL أو الارتباط المستهدف بنص أو محتوى محدد داخل الخلية، مما يؤدي إلى إنشاء ارتباطات تشعبية قابلة للنقر عليها.