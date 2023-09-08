---
title: محاذاة النص لمحتوى صف الجدول
linktitle: محاذاة النص لمحتوى صف الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية محاذاة محتوى الصف في جدول PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 210
url: /ar/net/programming-with-tables/text-alignment-for-table-row-content/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة لمحاذاة محتويات صف في جدول مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه.

## الخطوة 1: إنشاء وثيقة PDF
أولاً، سنقوم بإنشاء مستند PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## الخطوة 2: تهيئة الجدول
بعد ذلك، سنقوم بتهيئة الجدول:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## الخطوة 3: تحديد لون حدود الجدول
سنقوم بتكوين لون حدود الجدول:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## الخطوة 4: تكوين حدود خلية الجدول
سنقوم بتكوين حدود خلية الجدول:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## الخطوة 5: حلقة لإضافة 10 صفوف إلى الجدول
سنستخدم الآن حلقة لإضافة 10 صفوف إلى الجدول:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## الخطوة 6: تكوين محاذاة الخط العمودي
سنقوم بتكوين المحاذاة الرأسية لصفوف الجدول:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## الخطوة 7: إضافة محتوى إلى خلايا الصف
سنقوم بإضافة محتوى إلى خلايا الصف:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## الخطوة 8: إضافة الجدول إلى صفحة المستند
الآن دعونا نضيف الجدول إلى صفحة المستند:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## الخطوة 9: حفظ مستند PDF
أخيرًا، سنقوم بحفظ مستند PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### مثال على التعليمات البرمجية المصدر لمحاذاة النص لمحتوى صف الجدول باستخدام Aspose.PDF لـ .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء وثيقة PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// تهيئة مثيل جديد للجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// قم بتعيين لون حدود الجدول باللون LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// تعيين الحدود لخلايا الجدول
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// إنشاء حلقة لإضافة 10 صفوف
for (int row_count = 0; row_count < 10; row_count++)
{
	// إضافة صف إلى الجدول
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// إضافة كائن جدول إلى الصفحة الأولى من مستند الإدخال
tocPage.Paragraphs.Add(table);
// حفظ المستند المحدث الذي يحتوي على كائن الجدول
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية محاذاة محتويات صف في جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح لك هذا الدليل خطوة بخطوة كيفية إنشاء مستند، وتهيئة جدول، وتكوين الحدود والمحاذاة، وإضافة محتوى، وحفظ مستند PDF. الآن يمكنك تطبيق هذه المعرفة على مشاريعك الخاصة.

### الأسئلة الشائعة

#### س: كيف يمكنني محاذاة محتويات خلايا الجدول أفقيًا؟

 ج: يمكنك محاذاة محتويات خلايا الجدول أفقيًا عن طريق ضبط الإعداد`HorizontalAlign` خاصية الخلية`TextState` هدف. على سبيل المثال، لمحاذاة النص إلى المنتصف، استخدم`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . يمكنك أيضًا ضبطه على`HorizontalAlignment.Left` أو`HorizontalAlignment.Right` للمحاذاة اليسرى واليمنى، على التوالي.

#### س: هل يمكنني تطبيق أنماط وألوان حدود مختلفة على الخلايا الفردية داخل الجدول؟

 ج: نعم، يمكنك تطبيق أنماط وألوان حدود مختلفة على الخلايا الفردية داخل الجدول. لتخصيص الحدود لخلية معينة، قم بتعيين`cell.Border` الملكية إلى جديد`BorderInfo`الكائن بالإعدادات المطلوبة، مثل جوانب الحدود والعرض واللون.

#### س: كيف يمكنني ضبط المحاذاة الرأسية لمحتوى الجدول داخل الخلايا؟

 ج: يمكنك ضبط المحاذاة الرأسية لمحتوى الجدول داخل الخلايا عن طريق ضبط الإعداد`VerticalAlignment` خاصية الصف ل`VerticalAlignment.Center`, `VerticalAlignment.Top` ، أو`VerticalAlignment.Bottom`. تتحكم هذه الخاصية في المحاذاة العمودية لجميع الخلايا في هذا الصف.

#### س: هل من الممكن إضافة المزيد من الأعمدة أو الصفوف إلى الجدول ديناميكيًا؟

 ج: نعم، يمكنك إضافة المزيد من الأعمدة والصفوف إلى الجدول ديناميكيًا باستخدام الأمر`table.Rows.Add()` طريقة لإضافة صفوف جديدة و`row.Cells.Add()` طريقة إضافة خلايا جديدة إلى الصفوف. يمكنك القيام بذلك داخل الحلقات أو بناءً على متطلباتك المحددة.

#### س: كيف يمكنني تعيين لون خلفية لخلايا معينة أو للجدول بأكمله؟

 ج: لتعيين لون خلفية لخلايا معينة أو للجدول بأكمله، استخدم الخيار`BackgroundColor` ملكية`Cell` أو`Table` هدف. على سبيل المثال، لتعيين لون خلفية الخلية، استخدم`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.