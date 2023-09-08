---
title: إضافة جدول في ملف PDF
linktitle: إضافة جدول في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بإضافة الجداول بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 40
url: /ar/net/programming-with-tables/add-table/
---
Aspose.PDF for .NET هي مكتبة قوية تتيح للمطورين إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة جدول في ملف PDF باستخدام Aspose.PDF لـ .NET. سنشرح كل خطوة من مقتطف الكود المقدم ونقدم دليلاً شاملاً لمساعدتك على فهم الوظيفة وتنفيذها في مشاريعك الخاصة.

## مقدمة

تُستخدم مستندات PDF على نطاق واسع لمشاركة المعلومات وحفظها بتنسيق محمول. يمكن أن تؤدي إضافة الجداول إلى مستندات PDF إلى تحسين مظهرها المرئي وجعل عرض البيانات أكثر تنظيمًا وتنظيمًا. يوفر Aspose.PDF for .NET طريقة ملائمة لإضافة جداول إلى مستندات PDF الموجودة أو إنشاء جداول جديدة من البداية.

## ما هو Aspose.PDF لـ .NET؟

Aspose.PDF for .NET هي مكتبة قوية وغنية بالميزات تمكن مطوري .NET من إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. فهو يوفر مجموعة واسعة من الوظائف، بما في ذلك إنشاء ملفات PDF من البداية، وتعديل مستندات PDF الموجودة، ودمج ملفات PDF أو تقسيمها، وإضافة النصوص والصور والجداول، واستخراج البيانات من ملفات PDF، وغير ذلك الكثير. باستخدام Aspose.PDF for .NET، يمكن للمطورين أتمتة المهام المعقدة المتعلقة بملفات PDF وتقديم حلول PDF عالية الجودة.

## إضافة جدول إلى وثيقة PDF

لإضافة جدول إلى مستند PDF باستخدام Aspose.PDF لـ .NET، اتبع الدليل التفصيلي أدناه:

## الخطوة 1: تحميل مستند PDF المصدر

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

يقوم مقتطف الكود أعلاه بتحميل مستند PDF المصدر الذي تريد إضافة الجدول إليه. تأكد من توفير المسار الصحيح لملف PDF الخاص بك.

## الخطوة 2: تهيئة مثيل جديد للجدول

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

في هذه الخطوة، نقوم بإنشاء مثيل جديد لفئة Table، والذي يمثل جدولًا في مستند PDF.

## الخطوة 3: تحديد لون حدود الجدول

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

هنا، قمنا بتعيين لون الحدود للجدول باستخدام فئة BorderInfo. يمكنك تخصيص نمط الحدود وعرضها ولونها وفقًا لمتطلباتك.

## الخطوة 4: تعيين الحدود لخلايا الجدول

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

قمنا أيضًا بتعيين حدود خلايا الجدول باستخدام خاصية DefaultCellBorder لكائن الجدول. وهذا يضمن أن كل خلية في الجدول لها نمط الحدود والعرض واللون المحدد.

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

في هذه الخطوة، نقوم بإنشاء حلقة لإضافة 10 صفوف إلى الجدول. داخل كل صف، نضيف ثلاث خلايا تحتوي على بيانات نموذجية. يمكنك تعديل التعليمات البرمجية لإضافة صفوف وخلايا وفقًا لمتطلباتك المحددة.

## الخطوة 6: إضافة كائن الجدول إلى المستند

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// حفظ المستند المحدث الذي يحتوي على كائن الجدول
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

أخيرًا، نضيف كائن الجدول إلى الصفحة الأولى من مستند PDF باستخدام مجموعة الفقرات في الصفحة المقابلة.

### مثال على التعليمات البرمجية المصدر لإضافة جدول باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//قم بتحميل مستند PDF المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// تهيئة مثيل جديد للجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// قم بتعيين لون حدود الجدول باللون LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// تعيين الحدود لخلايا الجدول
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// قم بإنشاء حلقة لإضافة 10 صفوف
for (int row_count = 1; row_count < 10; row_count++)
{
	// إضافة صف إلى الجدول
	Aspose.Pdf.Row row = table.Rows.Add();
	// إضافة خلايا الجدول
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// إضافة كائن جدول إلى الصفحة الأولى من مستند الإدخال
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// حفظ المستند المحدث الذي يحتوي على كائن الجدول
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## خاتمة

في هذا البرنامج التعليمي، شرحنا عملية إضافة جدول إلى مستند PDF خطوة بخطوة باستخدام Aspose.PDF لـ .NET. لقد قمنا بتغطية تحميل مستند PDF المصدر، وتهيئة مثيل جديد لفئة الجدول، وتعيين لون حدود الجدول وحدود الخلايا، وإضافة صفوف وخلايا إلى الجدول، وإضافة كائن الجدول إلى المستند. باتباع هذا الدليل، يمكنك بسهولة دمج الجداول في مستندات PDF الخاصة بك برمجيًا وتخصيصها وفقًا لاحتياجاتك الخاصة.

### الأسئلة الشائعة لإضافة جدول في ملف PDF

#### س: هل يمكنني إضافة المزيد من الأعمدة إلى الجدول؟

ج: نعم، يمكنك إضافة المزيد من الأعمدة إلى الجدول عن طريق زيادة عدد الخلايا المضافة إلى كل صف. في المثال المقدم، يحتوي كل صف على ثلاث خلايا تمثل ثلاثة أعمدة. يمكنك إضافة المزيد من الخلايا إلى كل صف لإضافة أعمدة إضافية.

#### س: كيف يمكنني تغيير مظهر الجدول، مثل حجم الخط ونمطه؟

 ج: يمكنك تخصيص مظهر الجدول، بما في ذلك حجم الخط ونمطه، عن طريق تعيين الخصائص على`Aspose.Pdf.Table` و`Aspose.Pdf.TextFragment` أشياء. على سبيل المثال، يمكنك ضبط`DefaultCellTextState` خاصية لتغيير خصائص خط النص في خلايا الجدول.

#### س: هل يمكن دمج الخلايا في الجدول؟

 ج: نعم، يمكنك دمج الخلايا في الجدول باستخدام`MergeCells` طريقة`Aspose.Pdf.Row` فصل. يتيح لك ذلك إنشاء خلايا تمتد عبر عدة صفوف وأعمدة.

#### س: هل يمكنني إضافة صور أو محتوى آخر إلى خلايا الجدول؟

ج: نعم، يمكنك إضافة أنواع مختلفة من المحتوى إلى خلايا الجدول، بما في ذلك الصور والنصوص والارتباطات التشعبية والمزيد. يمكنك استخدام الفئات المناسبة من Aspose.PDF لـ .NET لإضافة أنواع مختلفة من المحتوى إلى الخلايا.

#### س: هل يتوافق Aspose.PDF for .NET مع .NET 5.0 أو الإصدارات الأحدث؟

ج: نعم، Aspose.PDF for .NET متوافق مع .NET 5.0 والإصدارات الأحدث. وهو يدعم العديد من منصات .NET، بما في ذلك .NET Framework و.NET Core و.NET 5.0+.