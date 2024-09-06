---
title: تصدير بيانات ورقة عمل Excel إلى جدول
linktitle: تصدير بيانات ورقة عمل Excel إلى جدول
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تصدير البيانات من ورقة Excel إلى جدول PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
في هذا البرنامج التعليمي، سنتعلم كيفية تصدير البيانات من ورقة عمل Excel وإنشاء جدول في مستند PDF باستخدام مكتبة Aspose.PDF for .NET. سنتناول التعليمات البرمجية المصدرية خطوة بخطوة ونشرح كل قسم بالتفصيل. بحلول نهاية هذا البرنامج التعليمي، ستتمكن من إنشاء ملفات PDF تحتوي على جداول تحتوي على بيانات من أوراق عمل Excel. لنبدأ!

## متطلبات
قبل أن نبدأ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#
- تم تثبيت Visual Studio على جهازك
- تمت إضافة مكتبة Aspose.PDF لـ .NET إلى مشروعك

## الخطوة 1: إعداد البيئة
للبدء، قم بإنشاء مشروع C# جديد في Visual Studio. أضف المرجع إلى مكتبة Aspose.PDF for .NET بالنقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول، وتحديد "إدارة حزم NuGet"، والبحث عن "Aspose.PDF". قم بتثبيت الحزمة وستكون جاهزًا للبدء.

## الخطوة 2: تحميل ورقة عمل Excel
في الخطوة الأولى من الكود الخاص بنا، نقوم بتحديد المسار إلى الدليل الذي يحتوي على مستند Excel. استبدل "YOUR DOCUMENT DIRECTORY" بمسار الدليل الفعلي الذي يوجد به ملف Excel الخاص بك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

هنا، نستخدم مكتبة Aspose.Cells لتحميل مصنف Excel. تأكد من استبدال "newBook1.xlsx" باسم ملف Excel الخاص بك.

## الخطوة 3: الوصول إلى ورقة العمل
 بعد ذلك، نحتاج إلى الوصول إلى ورقة العمل الأولى في ملف Excel. نقوم بذلك باستخدام`Worksheets` مجموعة من`Workbook` هدف.

```csharp
// الوصول إلى ورقة العمل الأولى في ملف Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 إذا كان ملف Excel الخاص بك يحتوي على أوراق عمل متعددة، فيمكنك تغيير قيمة الفهرس`[0]` للوصول إلى ورقة عمل مختلفة.

## الخطوة 4: تصدير البيانات إلى جدول البيانات
 الآن، سنقوم بتصدير محتويات ورقة عمل Excel إلى`DataTable` الكائن. نحدد نطاق الخلايا المراد تصديرها باستخدام`ExportDataTable` طريقة.

```csharp
// تصدير محتويات 7 صفوف و 2 عمودين بدءًا من الخلية الأولى إلى جدول البيانات
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

في هذا المثال، نقوم بتصدير جميع الصفوف والأعمدة بدءًا من الخلية الأولى (0, 0) وحتى الخلية الأخيرة في ورقة العمل. قم بتعيين النطاق المناسب بناءً على متطلباتك.

## الخطوة 5: إنشاء مستند PDF
الآن، سوف نقوم بإنشاء مستند PDF جديد باستخدام مكتبة Aspose.PDF.

```csharp
// إنشاء مثيل مستند
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

يؤدي هذا إلى إنشاء مستند PDF فارغ حيث يمكننا إضافة المحتوى.

## الخطوة 6: إضافة صفحة وجدول
لعرض البيانات بتنسيق جدول، نحتاج إلى إضافة صفحة وجدول إلى مستند PDF.

```csharp
// إنشاء صفحة في مثيل المستند
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// أضف كائن الجدول إلى مجموعة الفقرات في القسم
sec1.Paragraphs.Add(tab1);
```

هنا نقوم بإنشاء صفحة جديدة وكائن جدول. ثم نضيف الجدول إلى مجموعة الفقرات الخاصة بالصفحة.

## الخطوة 7: إعداد خصائص الجدول
قبل استيراد البيانات، نحتاج إلى تعيين بعض خصائص الجدول، مثل عرض الأعمدة وحدود الخلايا الافتراضية.

```csharp
// تعيين عرض الأعمدة في الجدول
tab1.ColumnWidths = "40 100 100";

// تعيين حدود الخلية الافتراضية للجدول باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

في هذا المثال، قمنا بتعيين عرض الأعمدة إلى 40 و100 و100 وحدة. وقم بتعديل القيم بناءً على بياناتك. وقمنا أيضًا بتعيين حدود الخلية الافتراضية لعرض الحدود على جميع جوانب كل خلية.

## الخطوة 8: استيراد البيانات إلى الجدول
 الآن سوف نقوم باستيراد البيانات من`DataTable` إدخال الكائن إلى الجدول باستخدام`ImportDataTable` طريقة.

```csharp
// استيراد البيانات إلى كائن الجدول من جدول البيانات الذي تم إنشاؤه أعلاه
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 هنا، نحدد نطاق الصفوف والأعمدة المراد استيرادها. في هذا المثال، نستورد جميع الصفوف والأعمدة من`dataTable` هدف.

## الخطوة 9: تنسيق الجدول
لتحسين مظهر الجدول، يمكننا تطبيق التنسيق على خلايا أو صفوف معينة. في هذه الخطوة، سنقوم بتنسيق الصف الأول والصفوف البديلة للجدول.

```csharp
// احصل على الصف الأول من الجدول
Aspose.Pdf.Row row1 = tab1.Rows[0];

// تنسيق الصف الأول
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // تعيين لون الخلفية للخلايا في الصف الأول
     curCell.BackgroundColor = Color.Blue;// تعيين الوجه للخلايا في الصف الأول
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // تعيين لون الخط للخلايا في الصف الأول
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // ضبط محاذاة النص للخلايا في الصف الأول
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// تنسيق الصف البديل
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // تعيين لون الخلفية للخلايا في الصفوف المتبادلة
         curCell.BackgroundColor = Color.Gray;
        
         // تعيين لون نص الخلايا في الصفوف المتبادلة
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

هنا، نكرر الخلايا في الصف الأول ونحدد لون الخلفية ووجه الخط ولون الخط ومحاذاة النص. بعد ذلك، نكرر جميع الخلايا في الصفوف البديلة ونحدد لون الخلفية والنص.

## الخطوة 10: حفظ مستند PDF
وأخيرًا، نقوم بحفظ مستند PDF في الموقع المحدد.

```csharp
// احفظ ملف PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بمسار الدليل واسم الملف المطلوب لملف PDF الناتج.

### مثال على كود المصدر لتصدير بيانات ورقة عمل Excel إلى جدول باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// الوصول إلى ورقة العمل الأولى في ملف Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// تصدير محتويات 7 صفوف و 2 عمودين بدءًا من الخلية الأولى إلى جدول البيانات
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// إنشاء مثيل مستند
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// إنشاء صفحة في مثيل المستند
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// أضف كائن الجدول إلى مجموعة الفقرات في القسم
sec1.Paragraphs.Add(tab1);

// تعيين عرض الأعمدة في الجدول. نحتاج إلى تحديد ColumnCount يدويًا.
// نظرًا لأن ورقة عمل Excel الحالية تحتوي على ثلاثة أعمدة، فإننا نحدد نفس العدد
tab1.ColumnWidths = "40 100 100";

// تعيين حدود الخلية الافتراضية للجدول باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// استيراد البيانات إلى كائن الجدول من جدول البيانات الذي تم إنشاؤه أعلاه
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// احصل على الصف الأول من الجدول
Aspose.Pdf.Row row1 = tab1.Rows[0];

// قم بالتكرار خلال جميع الخلايا في الصف الأول وقم بتعيين لون الخلفية إلى اللون الأزرق
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// تعيين خلفية جميع الخلايا في الصف الأول من الجدول.
	curCell.BackgroundColor = Color.Blue;
	// تعيين وجه الخط لخلايا الصف الأول في الجدول.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// تعيين لون الخط لجميع الخلايا في الصف الأول من الجدول.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// قم بتعيين محاذاة النص لخلايا الصف الأول في المنتصف.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// قم بالتكرار خلال جميع الخلايا في الصف الأول وقم بتعيين لون الخلفية إلى اللون الأزرق
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// تعيين لون الخلفية لجميع الخلايا باستثناء الصف الأول.
		curCell.BackgroundColor = Color.Gray;
		// تعيين لون النص لجميع الخلايا باستثناء الصف الأول.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// احفظ ملف PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تصدير البيانات من ورقة عمل Excel إلى جدول PDF باستخدام مكتبة Aspose.PDF for .NET. قمنا بتغطية عملية تحميل ورقة عمل Excel خطوة بخطوة، وإنشاء مستند PDF، وإضافة جدول، واستيراد البيانات، وتنسيق الجدول. يمكنك الآن إنشاء ملفات PDF تحتوي على جداول تحتوي على بيانات Excel برمجيًا.

### الأسئلة الشائعة

#### س: ما هو الغرض من تصدير بيانات ورقة عمل Excel إلى جدول PDF؟

أ: يتيح لك تصدير بيانات ورقة عمل Excel إلى جدول PDF تقديم البيانات بتنسيق منظم ومنظم. كما يتيح لك إنشاء ملفات PDF تحتوي على جداول تحتوي على بيانات من أوراق عمل Excel، مما يسهل مشاركة المعلومات وحفظها بتنسيق مستند محمول.

#### س: هل يمكنني تخصيص مظهر جدول PDF؟

ج: نعم، يمكنك تخصيص مظهر جدول PDF باستخدام خصائص مختلفة يوفرها Aspose.PDF لـ .NET. في الكود المصدر C# المقدم، يمكنك تعديل عرض الأعمدة وحدود الخلايا ومحاذاة النص ونمط الخط والمزيد لتناسب متطلباتك المحددة.

#### س: كيف أتعامل مع ملفات Excel ذات أوراق العمل المتعددة؟

 أ: في الكود C# المقدم، قمنا بالوصول إلى ورقة العمل الأولى في ملف Excel باستخدام الفهرس`[0]` إذا كان ملف Excel الخاص بك يحتوي على أوراق عمل متعددة، فيمكنك الوصول إليها عن طريق تغيير قيمة الفهرس وفقًا لذلك، مثل`[1]` للورقة الثانية أو`[2]` للورقة العمل الثالثة.

#### س: هل يمكنني تطبيق تنسيق مختلف على صفوف أو خلايا محددة في جدول PDF؟

ج: نعم، يمكنك تطبيق تنسيق مختلف على صفوف أو خلايا معينة في جدول PDF. في الكود المصدري C# المقدم، أوضحنا كيفية تنسيق الصف الأول والصفوف البديلة بشكل مختلف عن طريق تغيير لون الخلفية ونمط الخط ولون الخط. يمكنك تطبيق تقنيات تنسيق مماثلة على أي صفوف أو خلايا معينة حسب الحاجة.

#### س: هل Aspose.PDF for .NET هي المكتبة الوحيدة التي تسمح بتصدير بيانات Excel إلى جدول PDF؟

ج: Aspose.PDF for .NET هي مكتبة قوية للعمل مع مستندات PDF في تطبيقات .NET. ورغم أنه قد تتوفر مكتبات أخرى، فإن Aspose.PDF for .NET تقدم مجموعة واسعة من الميزات والقدرات لإنشاء ملفات PDF ومعالجتها وتصديرها مع جداول من بيانات Excel، مما يجعلها خيارًا شائعًا لمثل هذه المهام.