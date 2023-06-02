---
title: محاذاة النص لمحتوى صف الجدول
linktitle: محاذاة النص لمحتوى صف الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية محاذاة محتوى الصف في جدول PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 210
url: /ar/net/programming-with-tables/text-alignment-for-table-row-content/
---

في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة لمحاذاة محتويات صف في جدول مستند PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه.

## الخطوة الأولى: إنشاء مستند PDF
أولاً ، سننشئ مستند PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## الخطوة 2: تهيئة الجدول
بعد ذلك ، سنقوم بتهيئة الجدول:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## الخطوة 3: ضبط لون حدود الجدول
سنقوم بتكوين لون حدود الجدول:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## الخطوة 4: تكوين حد خلية الجدول
سنقوم بتكوين حد خلية الجدول:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## الخطوة 5: التكرار لإضافة 10 صفوف إلى الجدول
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

## الخطوة 8: إضافة الجدول إلى صفحة الوثيقة
لنقم الآن بإضافة الجدول إلى صفحة المستند:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## الخطوة 9: حفظ مستند PDF
أخيرًا ، سنحفظ مستند PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### مثال على شفرة المصدر لمحاذاة النص لمحتوى صف الجدول باستخدام Aspose.Words for .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء وثيقة PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// يقوم بتهيئة مثيل جديد للجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// اضبط لون حدود الجدول على LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// تعيين الحدود لخلايا الجدول
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// قم بإنشاء حلقة لإضافة 10 صفوف
for (int row_count = 0; row_count < 10; row_count++)
{
	// أضف صفًا إلى الجدول
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// أضف كائن جدول إلى الصفحة الأولى من مستند الإدخال
tocPage.Paragraphs.Add(table);
// احفظ المستند المحدث الذي يحتوي على كائن جدول
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية محاذاة محتويات صف في جدول في مستند PDF باستخدام Aspose.PDF for .NET. يوضح لك هذا الدليل التفصيلي كيفية إنشاء مستند وتهيئة جدول وتكوين الحدود والمحاذاة وإضافة محتوى وحفظ مستند PDF. الآن يمكنك تطبيق هذه المعرفة على مشاريعك الخاصة.