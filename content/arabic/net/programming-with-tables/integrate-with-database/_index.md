---
title: التكامل مع قاعدة البيانات في ملف PDF
linktitle: التكامل مع قاعدة البيانات في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتضمين البيانات من قاعدة بيانات في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-tables/integrate-with-database/
---
في هذا البرنامج التعليمي، سوف نتعلم كيفية تضمين البيانات من قاعدة بيانات في ملف PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري في لغة C# خطوة بخطوة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية استيراد بيانات الجدول من قاعدة بيانات إلى مستند PDF. لنبدأ!

## الخطوة 1: تهيئة البيئة
تأكد من أنك قمت بتكوين بيئة تطوير C# الخاصة بك باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد مساحات الأسماء الضرورية.

## الخطوة 2: إنشاء جدول البيانات
نقوم بإنشاء مثيل لـ DataTable لتمثيل البيانات التي نريد تضمينها في مستند PDF. في هذا المثال، نقوم بإنشاء DataTable بثلاثة أعمدة: معرف_الموظف، واسم_الموظف، والجنس. نضيف أيضًا صفين إلى DataTable ببيانات وهمية.

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

## الخطوة 3: إنشاء مستند وجدول PDF
نقوم بإنشاء مثيل للمستند وإضافة صفحة إلى هذا المستند. بعد ذلك، نقوم بإنشاء مثيل جدول لتمثيل جدولنا في مستند PDF. نحن نحدد عرض أعمدة الجدول وأنماط الحدود.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## الخطوة 4: استيراد البيانات من DataTable إلى الجدول
نستخدم طريقة ImportDataTable لاستيراد البيانات من DataTable إلى الجدول في مستند PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## الخطوة 5: إضافة الجدول إلى المستند
نضيف الجدول إلى مجموعة الفقرات بصفحة الوثيقة.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## الخطوة 6: احفظ المستند
نقوم بحفظ مستند PDF بالبيانات من قاعدة البيانات المدمجة.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

تهانينا! أنت تعرف الآن كيفية تضمين بيانات قاعدة البيانات في مستند PDF باستخدام Aspose.PDF لـ .NET.

### مثال على التعليمات البرمجية المصدر للتكامل مع قاعدة البيانات باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// إضافة صفين إلى كائن DataTable برمجياً
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
// تهيئة مثيل جديد للجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// ضبط عرض أعمدة الجدول
table.ColumnWidths = "40 100 100 100";
// قم بتعيين لون حدود الجدول باللون LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// تعيين الحدود لخلايا الجدول
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// إضافة كائن جدول إلى الصفحة الأولى من مستند الإدخال
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// حفظ المستند المحدث الذي يحتوي على كائن الجدول
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تضمين البيانات من قاعدة بيانات في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل التفصيلي لاستيراد البيانات من قاعدة البيانات الخاصة بك وعرضها في مستندات PDF. استكشف وثائق Aspose.PDF بشكل أكبر لاكتشاف الميزات والإمكانيات الأخرى التي توفرها هذه المكتبة القوية.

### الأسئلة الشائعة للتكامل مع قاعدة البيانات في ملف PDF

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET مع أنواع مختلفة من قواعد البيانات مثل MySQL أو SQL Server أو Oracle؟

ج: نعم، يمكنك استخدام Aspose.PDF لـ .NET مع أنواع مختلفة من قواعد البيانات مثل MySQL وSQL Server وOracle وغيرها. يوفر Aspose.PDF for .NET وظائف لقراءة البيانات من مصادر البيانات المختلفة، بما في ذلك قواعد البيانات وملفات XML والمزيد. يمكنك استرداد البيانات من نوع قاعدة البيانات التي تريدها ونشرها في DataTable أو أي بنية بيانات أخرى متوافقة مع Aspose.PDF لـ .NET.

#### س: كيف يمكنني تخصيص مظهر الجدول في مستند PDF؟

ج: يمكنك تخصيص مظهر الجدول في مستند PDF باستخدام الخصائص المتنوعة التي توفرها مكتبة Aspose.PDF لـ .NET. على سبيل المثال، يمكنك تعيين أنماط مختلفة للحدود وألوان الخلفية وأنماط الخطوط والمحاذاة للجدول وخلاياه. راجع Aspose.PDF للحصول على وثائق .NET لمزيد من التفاصيل حول تخصيص مظهر الجدول.

#### س: هل من الممكن إضافة ارتباطات تشعبية أو عناصر تفاعلية إلى البيانات المستوردة من قاعدة البيانات؟

ج: نعم، يمكنك إضافة ارتباطات تشعبية أو عناصر تفاعلية أخرى إلى البيانات المستوردة من قاعدة البيانات. يدعم Aspose.PDF for .NET إضافة الارتباطات التشعبية والإشارات المرجعية والعناصر التفاعلية الأخرى إلى مستند PDF. يمكنك معالجة المحتوى الموجود في DataTable قبل استيراده إلى الجدول وتضمين الارتباطات التشعبية أو الميزات التفاعلية الأخرى.

#### س: هل يمكنني ترقيم الجدول إذا تجاوز عدد معين من الصفوف؟

 ج: نعم، يمكنك ترقيم الجدول إذا تجاوز عدداً معيناً من الصفوف. لتحقيق ذلك، يمكنك استخدام`IsInNewPage`خاصية كائن الصف للإشارة إلى أن صفحة جديدة يجب أن تبدأ بعد صف معين. يمكنك حساب عدد الصفوف التي سيتم عرضها في كل صفحة وتعيين`IsInNewPage` الممتلكات وفقا لذلك.

#### س: كيف يمكنني تصدير مستند PDF مع بيانات قاعدة البيانات المضمنة إلى تنسيقات ملفات مختلفة مثل DOCX أو XLSX؟

ج: يسمح لك Aspose.PDF for .NET بتحويل مستندات PDF إلى تنسيقات ملفات أخرى متنوعة، بما في ذلك DOCX (Microsoft Word) وXLSX (Microsoft Excel). يمكنك استخدام Aspose.PDF لمكتبة .NET مع مكتبات Aspose الأخرى مثل Aspose.Words وAspose.Cells لتحقيق ذلك. أولاً، احفظ مستند PDF مع بيانات قاعدة البيانات المضمنة، ثم استخدم مكتبة Aspose المعنية لتحويله إلى تنسيق الملف المطلوب.