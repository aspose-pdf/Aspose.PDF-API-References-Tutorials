---
title: تحديد فاصل الجدول
linktitle: تحديد فاصل الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد فواصل الجدول في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 60
url: /ar/net/programming-with-tables/determine-table-break/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية تحديد فواصل الجدول في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري في C # خطوة بخطوة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تحديد ما إذا كان الجدول يتجاوز هوامش الصفحة. لنبدأ!

## الخطوة الأولى: تهيئة البيئة
أولاً ، تأكد من إعداد بيئة التطوير C # الخاصة بك باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد مساحات الأسماء الضرورية.

## الخطوة الثانية: إنشاء وثيقة PDF
 في هذه الخطوة ، نقوم بإنشاء ملف`Document` كائن لتمثيل وثيقة PDF.

```csharp
pdf-Document = new Document();
```

سيتم استخدام هذا المستند لإضافة أقسام وجداول.

## الخطوة 3: إضافة قسم وجدول
سنقوم الآن بإضافة قسم إلى مستند PDF الخاص بنا وإنشاء جدول داخل هذا القسم.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

نحدد أيضًا هامشًا أعلى للجدول بمقدار 300 نقطة. يمكنك ضبط هذه القيمة وفقًا لاحتياجاتك.

## الخطوة 4: إعداد الجدول
في هذه الخطوة ، نقوم بتكوين خصائص الجدول ، مثل عرض الأعمدة وحدودها.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

نحدد هنا عرض أعمدة الجدول وحدود الخلية. يمكنك ضبط هذه القيم وفقًا لتفضيلاتك.

## الخطوة 5: أضف صفوفًا وخلايا إلى الجدول
سنقوم الآن بإنشاء صفوف وخلايا في الجدول باستخدام حلقة.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

هنا نقوم بإنشاء 17 صفًا في الجدول وإضافة ثلاث خلايا لكل صف. يمكنك ضبط الإبزيم وفقًا لاحتياجاتك.

## الخطوة 6: تحديد فواصل الجدول
سنحدد الآن ما إذا كان الجدول يتجاوز هوامش الصفحة من خلال مقارنة ارتفاع الصفحة مع الارتفاع الإجمالي للكائنات في الجدول.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

نحسب ارتفاع الصفحة والارتفاع الإجمالي للكائنات مع مراعاة الهوامش. إذا كان الاختلاف 10 أو أقل ، فإن الجدول يتجاوز هوامش الصفحة.

## الخطوة 7: حفظ مستند PDF
أخيرًا ، نحفظ مستند PDF بالنتائج.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

تأكد من تحديد دليل المستند الصحيح. سيتم حفظ ملف PDF الناتج مع فواصل الجدول المحددة.

### مثال على شفرة المصدر لتحديد فاصل الجدول باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء فئة كائن PDF
Document pdf = new Document();
// أضف القسم إلى مجموعة أقسام مستند PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// إنشاء كائن جدول
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// أضف الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(table1);
// اضبط مع عرض أعمدة الجدول
table1.ColumnWidths = "100 100 100";
// تعيين حد الخلية الافتراضي باستخدام كائن BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// قم بتعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// قم بإنشاء كائن MarginInfo وقم بتعيين هوامشه اليسرى والسفلية واليمنى والعليا
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// قم بتعيين مساحة الخلية الافتراضية إلى كائن MarginInfo
table1.DefaultCellPadding = margin;
// إذا قمت بزيادة العداد إلى 17 ، فسوف ينكسر الجدول
// لأنه لا يمكن استيعابها أكثر من هذه الصفحة
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// احصل على معلومات ارتفاع الصفحة
float PageHeight = (float)pdf.PageInfo.Height;
// احصل على معلومات الارتفاع الإجمالية للهامش العلوي والسفلي للصفحة ،
// هامش أعلى الجدول وارتفاع الجدول.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// عرض ارتفاع الصفحة وارتفاع الجدول والهامش العلوي للجدول وأعلى الصفحة
// ومعلومات الهامش السفلي
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//تحقق مما إذا كنا قد اقتطعنا حجم الهامش العلوي للصفحة + الهامش السفلي للصفحة
// + هامش أعلى الجدول وارتفاع الجدول من ارتفاع الصفحة وأقلها
// من 10 (يمكن أن يكون الصف المتوسط أكبر من 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// إذا كانت القيمة أقل من 10 ، فقم بعرض الرسالة.
	// مما يدل على أنه لا يمكن وضع صف آخر وإذا أضفنا جديدًا
	// صف ، الجدول سوف ينكسر. يعتمد ذلك على قيمة ارتفاع الصف.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// احفظ مستند pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحديد فواصل الجدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل المفصل خطوة بخطوة للتحقق مما إذا كان الجدول يتجاوز هوامش الصفحة في مشاريع C # الخاصة بك.