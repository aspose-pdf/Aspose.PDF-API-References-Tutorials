---
title: أضف الجدول
linktitle: أضف الجدول
second_title: Aspose.PDF لمرجع .NET API
description: أضف الجداول بسهولة إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-tables/add-table/
---

Aspose.PDF for .NET مكتبة قوية تسمح للمطورين بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي ، سنوجهك خلال عملية إضافة جدول إلى مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح كل خطوة في مقتطف الشفرة المقدم ونقدم دليلاً شاملاً لمساعدتك على فهم وتنفيذ الوظائف في مشاريعك الخاصة.

## مقدمة

تُستخدم مستندات PDF على نطاق واسع لمشاركة المعلومات وحفظها بتنسيق محمول. يمكن أن تؤدي إضافة الجداول إلى مستندات PDF إلى تحسين مظهرها المرئي وجعل عرض البيانات أكثر تنظيماً وتنظيماً. يوفر Aspose.PDF for .NET طريقة ملائمة لإضافة جداول إلى مستندات PDF الموجودة أو إنشاء جداول جديدة من البداية.

## ما هو Aspose.PDF for .NET؟

Aspose.PDF for .NET مكتبة قوية وغنية بالمميزات تمكن مطوري .NET من إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. يوفر مجموعة واسعة من الوظائف ، بما في ذلك إنشاء ملفات PDF من البداية ، وتعديل مستندات PDF الموجودة ، ودمج ملفات PDF أو تقسيمها ، وإضافة نصوص ، وصور ، وجداول ، واستخراج البيانات من ملفات PDF ، وغير ذلك الكثير. باستخدام Aspose.PDF for .NET ، يمكن للمطورين أتمتة المهام المعقدة المتعلقة بـ PDF وتقديم حلول PDF عالية الجودة.

## إضافة جدول إلى وثيقة PDF

لإضافة جدول إلى مستند PDF باستخدام Aspose.PDF for .NET ، اتبع الدليل المفصل أدناه:

## الخطوة 1: تحميل مستند PDF المصدر

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

يقوم مقتطف الشفرة أعلاه بتحميل مستند PDF المصدر الذي تريد إضافة الجدول إليه. تأكد من توفير المسار الصحيح لملف PDF الخاص بك.

## الخطوة 2: تهيئة مثيل جديد للجدول

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

في هذه الخطوة ، نقوم بإنشاء مثيل جديد لفئة Table ، والتي تمثل جدولًا في مستند PDF.

## الخطوة 3: ضبط لون حدود الجدول

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

هنا ، قمنا بتعيين لون الحدود للجدول باستخدام فئة BorderInfo. يمكنك تخصيص نمط الحدود وعرضها ولونها وفقًا لمتطلباتك.

## الخطوة 4: تعيين الحدود لخلايا الجدول

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

قمنا أيضًا بتعيين الحدود لخلايا الجدول باستخدام خاصية DefaultCellBorder لكائن الجدول. هذا يضمن أن كل خلية في الجدول لها نمط الحدود والعرض واللون المحدد.

## الخطوة 5: إضافة صفوف وخلايا إلى الجدول

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

في هذه الخطوة ، نقوم بإنشاء حلقة لإضافة 10 صفوف إلى الجدول. داخل كل صف ، نضيف ثلاث خلايا مع بيانات العينة. يمكنك تعديل الكود لإضافة صفوف وخلايا وفقًا لمتطلباتك الخاصة.

## الخطوة 6: إضافة كائن الجدول إلى المستند

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// احفظ المستند المحدث الذي يحتوي على كائن جدول
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

أخيرًا ، نضيف كائن الجدول إلى الصفحة الأولى من مستند PDF باستخدام مجموعة الفقرات في الصفحة المقابلة.

### مثال على شفرة المصدر لإضافة جدول باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//تحميل مستند PDF المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// يقوم بتهيئة مثيل جديد للجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// اضبط لون حدود الجدول على LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// عيّن الحدود لخلايا الجدول
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// قم بإنشاء حلقة لإضافة 10 صفوف
for (int row_count = 1; row_count < 10; row_count++)
{
	// أضف صفًا إلى الجدول
	Aspose.Pdf.Row row = table.Rows.Add();
	// أضف خلايا الجدول
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// أضف كائن جدول إلى الصفحة الأولى من مستند الإدخال
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// احفظ المستند المحدث الذي يحتوي على كائن جدول
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا العملية خطوة بخطوة لإضافة جدول إلى مستند PDF باستخدام Aspose.PDF لـ .NET. قمنا بتغطية تحميل مستند PDF المصدر ، وتهيئة نسخة جديدة من فئة الجدول ، وتعيين لون حدود الجدول وحدود الخلية ، وإضافة صفوف وخلايا إلى الجدول ، وإضافة كائن الجدول إلى المستند. باتباع هذا الدليل ، يمكنك بسهولة دمج الجداول في مستندات PDF الخاصة بك برمجيًا وتخصيصها وفقًا لاحتياجاتك الخاصة.