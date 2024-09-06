---
title: محاذاة النص لمحتوى صف الجدول
linktitle: محاذاة النص لمحتوى صف الجدول
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية محاذاة محتوى الصف في جدول PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 210
url: /ar/net/programming-with-tables/text-alignment-for-table-row-content/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة لمحاذاة محتويات صف في جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح كود المصدر C# المقدم ونوضح لك كيفية تنفيذه.

## الخطوة 1: إنشاء مستند PDF
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

## الخطوة 3: ضبط لون حدود الجدول
سنقوم بتكوين لون حدود الجدول:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## الخطوة 4: تكوين حدود خلية الجدول
سنقوم بتكوين حدود خلية الجدول:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## الخطوة 5: تكرار لإضافة 10 صفوف إلى الجدول
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

## الخطوة 7: إضافة المحتوى إلى خلايا الصف
سنقوم بإضافة المحتوى إلى خلايا الصف:

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
وأخيرًا، سنقوم بحفظ مستند PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### مثال على كود المصدر لمحاذاة النص لمحتوى صف الجدول باستخدام Aspose.PDF لـ .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// يقوم بتهيئة مثيل جديد للجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تعيين لون حدود الجدول إلى LightGray
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
// إضافة كائن الجدول إلى الصفحة الأولى من مستند الإدخال
tocPage.Paragraphs.Add(table);
// حفظ المستند المحدث الذي يحتوي على كائن الجدول
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## خاتمة
تهانينا! لقد تعلمت الآن كيفية محاذاة محتويات صف في جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح لك هذا الدليل خطوة بخطوة كيفية إنشاء مستند، وتهيئة جدول، وتكوين الحدود والمحاذاة، وإضافة المحتوى، وحفظ مستند PDF. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة.

### الأسئلة الشائعة

#### س: كيف يمكنني محاذاة محتويات خلايا الجدول أفقيا؟

 أ: يمكنك محاذاة محتويات خلايا الجدول أفقيًا عن طريق ضبط`HorizontalAlign` خاصية الخلية`TextState` الكائن. على سبيل المثال، لمحاذاة النص في المنتصف، استخدم`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` يمكنك أيضًا ضبطه على`HorizontalAlignment.Left` أو`HorizontalAlignment.Right` للمحاذاة إلى اليسار واليمين على التوالي.

#### س: هل يمكنني تطبيق أنماط وألوان حدود مختلفة على خلايا فردية داخل الجدول؟

 ج: نعم، يمكنك تطبيق أنماط وألوان حدود مختلفة على خلايا فردية داخل الجدول. لتخصيص الحدود لخلية معينة، اضبط`cell.Border` الملكية إلى جديدة`BorderInfo`الكائن بالإعدادات المطلوبة، مثل جوانب الحدود والعرض واللون.

#### س: كيف يمكنني ضبط المحاذاة الرأسية لمحتوى الجدول داخل الخلايا؟

 أ: يمكنك ضبط المحاذاة الرأسية لمحتوى الجدول داخل الخلايا عن طريق ضبط`VerticalAlignment` خاصية الصف إلى`VerticalAlignment.Center`, `VerticalAlignment.Top` ، أو`VerticalAlignment.Bottom`تتحكم هذه الخاصية في المحاذاة الرأسية لجميع الخلايا في هذا الصف.

#### س: هل من الممكن إضافة المزيد من الأعمدة أو الصفوف إلى الجدول بشكل ديناميكي؟

 ج: نعم، يمكنك إضافة المزيد من الأعمدة والصفوف إلى الجدول ديناميكيًا باستخدام`table.Rows.Add()` طريقة إضافة صفوف جديدة و`row.Cells.Add()` طريقة لإضافة خلايا جديدة إلى الصفوف. يمكنك القيام بذلك داخل الحلقات أو بناءً على متطلباتك المحددة.

#### س: كيف يمكنني تعيين لون الخلفية لخلايا محددة أو الجدول بأكمله؟

 أ: لتعيين لون الخلفية لخلايا معينة أو الجدول بأكمله، استخدم`BackgroundColor` ممتلكات`Cell` أو`Table` الكائن. على سبيل المثال، لتعيين لون الخلفية لخلية، استخدم`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.