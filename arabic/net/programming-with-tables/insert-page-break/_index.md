---
title: إدراج فاصل صفحة
linktitle: إدراج فاصل صفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إدراج فاصل صفحات في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 110
url: /ar/net/programming-with-tables/insert-page-break/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية إدراج فاصل صفحات في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري في C # خطوة بخطوة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية إضافة فاصل صفحة بعد عدد معين من الأسطر في جدول مستند PDF. لنبدأ!

## الخطوة الأولى: تهيئة البيئة
تأكد من تكوين بيئة التطوير C # الخاصة بك باستخدام Aspose.PDF for .NET. أضف المرجع إلى المكتبة واستورد مساحات الأسماء الضرورية.

## الخطوة 2: إنشاء المستند والجدول
نقوم بإنشاء مثيل مستند جديد وإضافة صفحة إلى هذا المستند. بعد ذلك ، نقوم بإنشاء مثيل Table لتمثيل جدولنا في مستند PDF. نحدد أيضًا أنماط الحدود للجدول.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## الخطوة 3: أضف صفوفًا إلى الجدول
نستخدم حلقة لإضافة 200 صف إلى المصفوفة. لكل صف ، نقوم بإنشاء مثيل للصف وإضافة خليتين بمحتوى نصي.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // عند إضافة 10 أسطر ، نقوم بإدراج فاصل صفحة جديد
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## الخطوة 4: إضافة الجدول إلى المستند
نضيف الجدول إلى مجموعة الفقرات في صفحة الوثيقة.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## الخطوة 5: احفظ المستند
نقوم بحفظ مستند PDF مع إدراج فاصل الصفحة.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### مثال على التعليمات البرمجية المصدر لإدراج فاصل صفحة باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// مثيل المستند
Document doc = new Document();
// أضف صفحة إلى مجموعة صفحات من ملف PDF
doc.Pages.Add();
// إنشاء مثيل الجدول
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// تعيين نمط الحدود للجدول
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// عيّن نمط الحدود الافتراضي للجدول بلون الحد باللون الأحمر
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// حدد جدول عمود Widht
tab.ColumnWidths = "100 100";
// قم بإنشاء حلقة لإضافة 200 صف للجدول
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// عند إضافة 10 صفوف ، قم بعرض صف جديد في صفحة جديدة
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// أضف جدولاً إلى مجموعة فقرات ملف PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// احفظ مستند PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إدراج فاصل صفحات في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل المفصل خطوة بخطوة لإضافة فاصل صفحة بعد عدد معين من الأسطر في جدول في مستند PDF باستخدام C #.