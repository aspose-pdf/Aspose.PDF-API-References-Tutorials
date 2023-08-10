---
title: إضافة عمود مكرر في مستند PDF
linktitle: إضافة عمود مكرر في مستند PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة عمود مكرر في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 20
url: /ar/net/programming-with-tables/add-repeating-column/
---
في هذا البرنامج التعليمي ، سوف نتعلم كيفية إضافة عمود مكرر في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري في C # خطوة بخطوة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية إنشاء جدول بعمود متكرر في مستند PDF. لنبدأ!

## الخطوة الأولى: تهيئة البيئة
أولاً ، تأكد من إعداد بيئة التطوير C # الخاصة بك باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد مساحات الأسماء الضرورية.

## الخطوة الثانية: إنشاء وثيقة PDF
في هذه الخطوة ، نقوم بإنشاء مستند PDF جديد.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

لقد قمنا بإنشاء مستند PDF فارغ حيث يمكننا إضافة المحتوى.

## الخطوة الثالثة: إنشاء الجداول
في هذه الخطوة نقوم بإنشاء جدول رئيسي (`outerTable`) وجدول متداخل (`mytable`) والتي سوف تتكرر في العمود.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

حددنا خصائص الجدول مثل عرض العمود ووضع فاصل الجدول المتداخل.

## الخطوة 4: إضافة الجداول إلى المستند
الآن نضيف الجداول التي تم إنشاؤها إلى مستند PDF.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

نضيف أولاً الجدول الرئيسي (`outerTable`) إلى مستند PDF. بعد ذلك ، نضيف الجدول المتداخل (`mytable` ) كفقرة في خلية في الجدول الرئيسي. نحدد أيضًا عدد الأعمدة المكررة لـ`mytable` (في هذا المثال ، 5 أعمدة).

## الخطوة 5: إضافة رؤوس وخطوط
الآن نضيف الرؤوس والصفوف إلى الجدول.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// أضف رؤوسًا أخرى هنا

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // أضف الأعمدة الأخرى هنا
}
```

نضيف أولاً الرؤوس إلى الصف الأول من الجدول (`headerRow`). ثم نضيف صفوف البيانات من حلقة. في هذا المثال ، نضيف 6 صفوف من البيانات.

## الخطوة 6: حفظ مستند PDF
أخيرًا ، نحفظ مستند PDF في الملف المحدد.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

تأكد من تحديد الدليل الصحيح واسم الملف لحفظ ملف PDF الناتج.

### مثال على كود المصدر لإضافة عمود مكرر باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// قم بإنشاء مستند جديد
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// إنشاء جدول خارجي يشغل الصفحة بأكملها
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//إنشاء كائن جدول سيتم تداخله داخل OuterTable والذي سينقسم داخل نفس الصفحة
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// قم بإضافة الجزء الخارجي إلى فقرات الصفحة
// أضف mytable إلى OuterTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// إضافة صف الرأس
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إضافة عمود مكرر في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل المفصل خطوة بخطوة لإنشاء جداول بأعمدة متكررة في مشاريع C # الخاصة بك.

### الأسئلة الشائعة حول إضافة عمود مكرر في مستند PDF

#### س: هل يمكنني تخصيص عدد الأعمدة المكررة في الجدول المتداخل؟

 ج: نعم ، يمكنك تخصيص عدد الأعمدة المكررة في الجدول المتداخل. في المثال المقدم ، قمنا بتعيين`mytable.RepeatingColumnsCount = 5;`، مما يعني أنه سيكون هناك 5 أعمدة متكررة. يمكنك تغيير هذه القيمة إلى أي رقم تريده.

#### س: هل من الممكن إضافة المزيد من الصفوف إلى الجدول المتداخل ديناميكيًا؟

ج: نعم ، يمكنك إضافة المزيد من الصفوف ديناميكيًا إلى الجدول المتداخل بنفس الطريقة الموضحة في البرنامج التعليمي. يمكنك استخدام الحلقات أو أي منطق آخر لإضافة صفوف بناءً على بياناتك.

#### س: هل يمكنني تطبيق الأنماط والتنسيق على الجدول وخلاياه؟

ج: نعم ، يمكنك تطبيق الأنماط والتنسيق على الجدول وخلاياه باستخدام Aspose.PDF for .NET. توفر المكتبة خصائص وطرق مختلفة لتخصيص مظهر الجدول ومحتوياته.

#### س: هل Aspose.PDF for .NET متوافق مع .NET Core؟

ج: نعم ، Aspose.PDF for .NET متوافق مع .NET Core. يمكنك استخدامه في تطبيقات .NET Framework و .NET Core.

#### س: هل يمكنني استخدام هذا الأسلوب لإضافة أعمدة متكررة في مستند PDF موجود؟

ج: نعم ، يمكنك استخدام هذا الأسلوب لإضافة أعمدة متكررة في مستند PDF موجود. ما عليك سوى تحميل المستند الحالي باستخدام Aspose.PDF for .NET واتبع نفس الخطوات لإنشاء وإضافة عمود التكرار.