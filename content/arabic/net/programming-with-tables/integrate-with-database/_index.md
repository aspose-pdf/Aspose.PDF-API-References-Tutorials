---
title: التكامل مع قاعدة البيانات في ملف PDF
linktitle: التكامل مع قاعدة البيانات في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تضمين البيانات من قاعدة البيانات في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-tables/integrate-with-database/
---
في هذا البرنامج التعليمي، سنتعلم كيفية تضمين البيانات من قاعدة بيانات في ملف PDF باستخدام Aspose.PDF لـ .NET. وسنشرح التعليمات البرمجية المصدرية بلغة C# خطوة بخطوة. وفي نهاية هذا البرنامج التعليمي، ستعرف كيفية استيراد بيانات الجدول من قاعدة بيانات إلى مستند PDF. لنبدأ!

## الخطوة 1: إعداد البيئة
تأكد من تكوين بيئة تطوير C# الخاصة بك باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد المساحات الأساسية اللازمة.

## الخطوة 2: إنشاء جدول البيانات
نقوم بإنشاء مثيل لجدول البيانات لتمثيل البيانات التي نريد تضمينها في مستند PDF. في هذا المثال، نقوم بإنشاء جدول بيانات يحتوي على ثلاثة أعمدة: معرف الموظف، واسم الموظف، والجنس. كما نضيف صفين إلى جدول البيانات يحتويان على بيانات وهمية.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## الخطوة 3: إنشاء مستند PDF والجدول
نقوم بإنشاء مثيل من Document ونضيف صفحة إلى هذا المستند. بعد ذلك، نقوم بإنشاء مثيل Table لتمثيل الجدول في مستند PDF. نقوم بتحديد عرض أعمدة الجدول وأنماط الحدود.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## الخطوة 4: استيراد البيانات من جدول البيانات إلى الجدول
نحن نستخدم طريقة ImportDataTable لاستيراد البيانات من DataTable إلى الجدول في مستند PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## الخطوة 5: إضافة الجدول إلى المستند
نضيف الجدول إلى مجموعة الفقرات الخاصة بصفحة المستند.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## الخطوة 6: احفظ المستند
نقوم بحفظ مستند PDF بالبيانات من قاعدة البيانات المضمنة.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

مبروك! أنت الآن تعرف كيفية تضمين بيانات قاعدة البيانات في مستند PDF باستخدام Aspose.PDF لـ .NET.

### مثال على كود المصدر للتكامل مع قاعدة البيانات باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// إضافة صفين إلى كائن DataTable برمجيًا
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// إنشاء مثيل المستند
Document doc = new Document();
doc.Pages.Add();
// يقوم بتهيئة مثيل جديد للجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تعيين عرض الأعمدة في الجدول
table.ColumnWidths = "40 100 100 100";
// تعيين لون حدود الجدول إلى LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// تعيين الحدود لخلايا الجدول
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// إضافة كائن الجدول إلى الصفحة الأولى من مستند الإدخال
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// حفظ المستند المحدث الذي يحتوي على كائن الجدول
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تضمين البيانات من قاعدة بيانات في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الدليل التفصيلي لاستيراد البيانات من قاعدة البيانات الخاصة بك وعرضها في مستندات PDF. استكشف وثائق Aspose.PDF بشكل أكبر لاكتشاف الميزات والإمكانيات الأخرى التي توفرها هذه المكتبة القوية.

### الأسئلة الشائعة حول التكامل مع قاعدة البيانات في ملف PDF

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET مع أنواع قواعد بيانات مختلفة مثل MySQL أو SQL Server أو Oracle؟

ج: نعم، يمكنك استخدام Aspose.PDF for .NET مع أنواع مختلفة من قواعد البيانات مثل MySQL وSQL Server وOracle وغيرها. يوفر Aspose.PDF for .NET وظائف لقراءة البيانات من مصادر بيانات مختلفة، بما في ذلك قواعد البيانات وملفات XML والمزيد. يمكنك استرداد البيانات من نوع قاعدة البيانات المطلوبة وتعبئتها في جدول بيانات أو أي بنية بيانات أخرى متوافقة مع Aspose.PDF for .NET.

#### س: كيف يمكنني تخصيص مظهر الجدول في مستند PDF؟

ج: يمكنك تخصيص مظهر الجدول في مستند PDF باستخدام خصائص مختلفة توفرها مكتبة Aspose.PDF for .NET. على سبيل المثال، يمكنك تعيين أنماط حدود مختلفة وألوان خلفية وأنماط خطوط ومحاذاة للجدول وخلاياه. راجع وثائق Aspose.PDF for .NET لمزيد من التفاصيل حول تخصيص مظهر الجدول.

#### س: هل من الممكن إضافة ارتباطات تشعبية أو عناصر تفاعلية للبيانات المستوردة من قاعدة البيانات؟

ج: نعم، يمكنك إضافة ارتباطات تشعبية أو عناصر تفاعلية أخرى إلى البيانات المستوردة من قاعدة البيانات. يدعم برنامج Aspose.PDF for .NET إضافة ارتباطات تشعبية وإشارات مرجعية وعناصر تفاعلية أخرى إلى مستند PDF. يمكنك معالجة المحتوى في جدول البيانات قبل استيراده إلى الجدول وتضمين ارتباطات تشعبية أو ميزات تفاعلية أخرى.

#### س: هل يمكنني تقسيم الجدول إلى صفحات إذا تجاوز عدد معين من الصفوف؟

 ج: نعم، يمكنك ترقيم صفحات الجدول إذا تجاوز عدد الصفوف المسموح به. لتحقيق ذلك، يمكنك استخدام`IsInNewPage`خاصية كائن الصف للإشارة إلى أنه يجب بدء صفحة جديدة بعد صف معين. يمكنك حساب عدد الصفوف المراد عرضها في كل صفحة وتعيين`IsInNewPage` الممتلكات وفقا لذلك.

#### س: كيف يمكنني تصدير مستند PDF مع بيانات قاعدة البيانات المضمنة إلى تنسيقات ملفات مختلفة مثل DOCX أو XLSX؟

ج: يتيح لك Aspose.PDF for .NET تحويل مستندات PDF إلى تنسيقات ملفات أخرى متنوعة، بما في ذلك DOCX (Microsoft Word) وXLSX (Microsoft Excel). يمكنك استخدام مكتبة Aspose.PDF for .NET بالاشتراك مع مكتبات Aspose الأخرى مثل Aspose.Words وAspose.Cells لتحقيق ذلك. أولاً، احفظ مستند PDF مع بيانات قاعدة البيانات المضمنة، ثم استخدم مكتبة Aspose ذات الصلة لتحويله إلى تنسيق الملف المطلوب.