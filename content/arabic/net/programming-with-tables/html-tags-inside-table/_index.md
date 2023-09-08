---
title: علامات HTML داخل الجدول في ملف PDF
linktitle: علامات HTML داخل الجدول في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام علامات HTML داخل جدول في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 100
url: /ar/net/programming-with-tables/html-tags-inside-table/
---
في هذا البرنامج التعليمي، سنتعلم كيفية استخدام علامات HTML داخل جدول في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري في لغة C# خطوة بخطوة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية إدراج محتوى HTML في جدول في مستند PDF. لنبدأ!

## الخطوة 1: تهيئة البيئة
تأكد من أنك قمت بتكوين بيئة تطوير C# الخاصة بك باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد مساحات الأسماء الضرورية.

## الخطوة الثانية: إنشاء بيانات الجدول
نقوم بإنشاء DataTable يحتوي على عمود "بيانات" من النوع String. نقوم بعد ذلك بإضافة صفوف إلى DataTable باستخدام محتوى HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## الخطوة 3: إنشاء المستند والجدول
نقوم بإنشاء مستند PDF جديد ونضيف صفحة في هذا المستند. بعد ذلك، نقوم بتهيئة مثيل لفئة الجدول وتعيين خصائص الجدول.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## الخطوة 4: استيراد البيانات إلى الجدول
نقوم باستيراد البيانات من DataTable إلى الجدول باستخدام طريقة "ImportDataTable". نحدد معلمات الطريقة للإشارة إلى نطاق الصفوف والأعمدة التي يجب استيرادها في DataTable.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## الخطوة 5: إضافة الجدول إلى المستند
نضيف الجدول إلى صفحة الوثيقة.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## المرحلة 6: حفظ الوثيقة
نقوم بحفظ مستند PDF بالجدول الذي يحتوي على محتوى HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### مثال على التعليمات البرمجية المصدر لعلامات HTML داخل الجدول باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// تهيئة مثيل جديد للجدول
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//ضبط عرض أعمدة الجدول
tableProvider.ColumnWidths = "400 50 ";
// قم بتعيين لون حدود الجدول باللون LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// تعيين الحدود لخلايا الجدول
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام علامات HTML داخل جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل التفصيلي لإدراج محتوى HTML في خلايا الجدول في مستند PDF باستخدام لغة C#.

### الأسئلة الشائعة حول علامات HTML داخل الجدول في ملف PDF

#### س: هل يمكنني استخدام علامات وسمات HTML الأخرى داخل خلايا الجدول؟

 ج: نعم، يمكنك استخدام علامات وسمات HTML المختلفة داخل خلايا الجدول، مثل`<b>`, `<i>`, `<a>`، و أكثر من ذلك بكثير. يدعم Aspose.PDF for .NET نطاقًا واسعًا من عناصر وأنماط HTML التي يمكنك استخدامها لتنسيق المحتوى داخل خلايا الجدول.

#### س: هل يمكنني تطبيق أنماط CSS على محتوى HTML داخل خلايا الجدول؟

ج: نعم، يمكنك تطبيق أنماط CSS على محتوى HTML داخل خلايا الجدول. يوفر Aspose.PDF for .NET دعمًا لأنماط CSS الأساسية التي يمكن تطبيقها على عناصر HTML.

#### س: هل من الممكن إضافة صور مع محتوى HTML داخل خلايا الجدول؟

 ج: نعم، يمكنك إضافة صور مع محتوى HTML داخل خلايا الجدول. يمكنك استخدام HTML`<img>` علامات لتضمين صور من مصادر مختلفة، مثل الملفات المحلية أو عناوين URL.

#### س: كيف يمكنني تحديد عروض أعمدة مختلفة للجدول؟

 ج: يمكنك تحديد عروض أعمدة مختلفة للجدول باستخدام الأمر`ColumnWidths` خاصية الجدول. تأخذ الخاصية سلسلة تحتوي على قيم مفصولة بمسافات، حيث تمثل كل قيمة عرض العمود بالنقاط.

#### س: هل يمكنني استخدام الجداول المتداخلة داخل خلية تحتوي على محتوى HTML؟

ج: نعم، يمكنك استخدام الجداول المتداخلة داخل خلية تحتوي على محتوى HTML. يمكنك إنشاء مثيلات جدول منفصلة وإضافتها كجزء من محتوى HTML داخل الخلية لتحقيق تأثير التداخل.