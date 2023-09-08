---
title: تصدير بيانات ورقة عمل Excel إلى الجدول
linktitle: تصدير بيانات ورقة عمل Excel إلى الجدول
second_title: Aspose.PDF لمرجع .NET API
description: قم بتصدير البيانات من ورقة Excel إلى جدول PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
في هذا البرنامج التعليمي، سوف نتعلم كيفية تصدير البيانات من ورقة عمل Excel وإنشاء جدول في مستند PDF باستخدام مكتبة Aspose.PDF for .NET. سنتعرف على الكود المصدري خطوة بخطوة وسنشرح كل قسم بالتفصيل. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على إنشاء ملفات PDF تحتوي على جداول تحتوي على بيانات من أوراق عمل Excel. هيا بنا نبدأ!

## متطلبات
قبل أن نبدأ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#
- تم تثبيت Visual Studio على جهازك
- تمت إضافة Aspose.PDF لمكتبة .NET إلى مشروعك

## الخطوة 1: إعداد البيئة
للبدء، قم بإنشاء مشروع C# جديد في Visual Studio. أضف المرجع إلى مكتبة Aspose.PDF لـ .NET عن طريق النقر بزر الماوس الأيمن على مشروعك في Solution Explorer، وتحديد "Manage NuGet Packages"، والبحث عن "Aspose.PDF". قم بتثبيت الحزمة وستكون جاهزًا للانطلاق.

## الخطوة 2: تحميل ورقة عمل Excel
في الخطوة الأولى من التعليمات البرمجية الخاصة بنا، نحدد المسار إلى الدليل الذي يحتوي على مستند Excel. استبدل "دليل المستندات الخاص بك" بمسار الدليل الفعلي الذي يوجد به ملف Excel الخاص بك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

هنا، نستخدم مكتبة Aspose.Cells لتحميل مصنف Excel. تأكد من استبدال "newBook1.xlsx" باسم ملف Excel الخاص بك.

## الخطوة 3: الوصول إلى ورقة العمل
 بعد ذلك، نحتاج إلى الوصول إلى ورقة العمل الأولى في ملف Excel. نحن نفعل هذا باستخدام`Worksheets` جمع من`Workbook` هدف.

```csharp
// الوصول إلى ورقة العمل الأولى في ملف Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 إذا كان ملف Excel الخاص بك يحتوي على أوراق عمل متعددة، فيمكنك تغيير قيمة الفهرس`[0]` للوصول إلى ورقة عمل مختلفة.

## الخطوة 4: تصدير البيانات إلى DataTable
 الآن، سوف نقوم بتصدير محتويات ورقة عمل Excel إلى ملف`DataTable` هدف. نحدد نطاق الخلايا المراد تصديرها باستخدام`ExportDataTable` طريقة.

```csharp
// تصدير محتويات 7 صفوف وعمودين بدءًا من الخلية الأولى إلى DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

في هذا المثال، نقوم بتصدير كافة الصفوف والأعمدة بدءًا من الخلية الأولى (0، 0) إلى الخلية الأخيرة في ورقة العمل. قم بتعيين النطاق المناسب بناءً على متطلباتك.

## الخطوة 5: إنشاء مستند PDF
الآن، سنقوم بإنشاء مستند PDF جديد باستخدام مكتبة Aspose.PDF.

```csharp
// إنشاء مثيل مستند
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

يؤدي هذا إلى إنشاء مستند PDF فارغ حيث يمكننا إضافة محتوى.

## الخطوة 6: إضافة صفحة وجدول
لعرض البيانات بتنسيق جدول، نحتاج إلى إضافة صفحة وجدول إلى مستند PDF.

```csharp
// قم بإنشاء صفحة في مثيل المستند
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// قم بإضافة كائن الجدول في مجموعة الفقرات الخاصة بالقسم
sec1.Paragraphs.Add(tab1);
```

هنا، نقوم بإنشاء صفحة جديدة وكائن جدول. ثم نقوم بإضافة الجدول إلى مجموعة الفقرات بالصفحة.

## الخطوة 7: تحديد خصائص الجدول
قبل استيراد البيانات، نحتاج إلى تعيين بعض خصائص الجدول، مثل عرض الأعمدة وحدود الخلايا الافتراضية.

```csharp
// ضبط عرض أعمدة الجدول
tab1.ColumnWidths = "40 100 100";

// قم بتعيين حدود الخلية الافتراضية للجدول باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

في هذا المثال، قمنا بتعيين عرض الأعمدة على 40 و100 و100 وحدة. اضبط القيم بناءً على بياناتك. قمنا أيضًا بتعيين حدود الخلية الافتراضية لعرض الحدود على جميع جوانب كل خلية.

## الخطوة 8: استيراد البيانات إلى الجدول
 الآن سوف نقوم باستيراد البيانات من`DataTable` كائن في الجدول باستخدام`ImportDataTable` طريقة.

```csharp
// قم باستيراد البيانات إلى كائن الجدول من DataTable الذي تم إنشاؤه أعلاه
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 هنا، نحدد نطاق الصفوف والأعمدة المراد استيرادها. في هذا المثال، نقوم باستيراد جميع الصفوف والأعمدة من ملف`dataTable` هدف.

## الخطوة 9: تنسيق الجدول
لتحسين مظهر الجدول، يمكننا تطبيق التنسيق على خلايا أو صفوف معينة. في هذه الخطوة، سنقوم بتنسيق الصف الأول والصفوف البديلة من الجدول.

```csharp
// احصل على الصف الأول من الجدول
Aspose.Pdf.Row row1 = tab1.Rows[0];

// تنسيق الصف الأول
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // قم بتعيين لون خلفية الخلايا في الصف الأول
     curCell.BackgroundColor = Color.Blue;// تعيين الوجه للخلايا في الصف الأول
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // قم بتعيين لون الخط للخلايا في الصف الأول
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // قم بتعيين محاذاة النص للخلايا الموجودة في الصف الأول
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// تنسيق الصف البديل
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // قم بتعيين لون خلفية الخلايا في الصفوف البديلة
         curCell.BackgroundColor = Color.Gray;
        
         // قم بتعيين لون نص الخلايا في الصفوف البديلة
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

هنا، نقوم بالتكرار عبر الخلايا الموجودة في الصف الأول ونقوم بتعيين لون الخلفية ووجه الخط ولون الخط ومحاذاة النص. بعد ذلك، نقوم بالتكرار عبر كافة الخلايا الموجودة في الصفوف البديلة ونقوم بتعيين لون الخلفية والنص الخاص بها.

## الخطوة 10: حفظ مستند PDF
وأخيرًا، نقوم بحفظ مستند PDF في الموقع المحدد.

```csharp
// احفظ ملف PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

تأكد من استبدال "YOUR DOCUMENT DIRECTORY" بمسار الدليل المطلوب واسم الملف لملف PDF الناتج.

### مثال على التعليمات البرمجية المصدر لتصدير بيانات ورقة عمل Excel إلى الجدول باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// الوصول إلى ورقة العمل الأولى في ملف Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// تصدير محتويات 7 صفوف وعمودين بدءًا من الخلية الأولى إلى DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// إنشاء مثيل لمستند مستند
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// قم بإنشاء صفحة في مثيل المستند
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// قم بإضافة كائن الجدول في مجموعة الفقرات الخاصة بالقسم
sec1.Paragraphs.Add(tab1);

// ضبط عرض أعمدة الجدول. نحتاج إلى تحديد ColumnCount يدويًا.
// وبما أن ورقة عمل Excel الحالية تحتوي على ثلاثة أعمدة، فإننا نحدد نفس العدد
tab1.ColumnWidths = "40 100 100";

// قم بتعيين حدود الخلية الافتراضية للجدول باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// قم باستيراد البيانات إلى كائن الجدول من DataTable الذي تم إنشاؤه أعلاه
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// احصل على الصف الأول من الجدول
Aspose.Pdf.Row row1 = tab1.Rows[0];

// قم بالتكرار خلال جميع الخلايا الموجودة في الصف الأول واضبط لون خلفيتها على اللون الأزرق
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// قم بتعيين خلفية كافة الخلايا في الصف الأول من الجدول.
	curCell.BackgroundColor = Color.Blue;
	// قم بتعيين وجه الخط لخلايا الصف الأول في الجدول.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// قم بتعيين لون الخط لجميع الخلايا في الصف الأول من الجدول.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// قم بتعيين محاذاة النص لخلايا الصف الأول كمركز.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// قم بالتكرار خلال جميع الخلايا الموجودة في الصف الأول واضبط لون خلفيتها على اللون الأزرق
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// قم بتعيين لون الخلفية لجميع الخلايا باستثناء الصف الأول.
		curCell.BackgroundColor = Color.Gray;
		// قم بتعيين لون النص لجميع الخلايا باستثناء الصف الأول.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// احفظ ملف PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تصدير البيانات من ورقة عمل Excel إلى جدول PDF باستخدام مكتبة Aspose.PDF for .NET. لقد قمنا بتغطية العملية خطوة بخطوة لتحميل ورقة عمل Excel، وإنشاء مستند PDF، وإضافة جدول، واستيراد البيانات، وتنسيق الجدول. يمكنك الآن إنشاء ملفات PDF باستخدام جداول تحتوي على بيانات Excel برمجيًا.

### الأسئلة الشائعة

#### س: ما هو الغرض من تصدير بيانات ورقة عمل Excel إلى جدول PDF؟

ج: يتيح لك تصدير بيانات ورقة عمل Excel إلى جدول PDF تقديم البيانات بتنسيق منظم ومنظم. فهو يمكّنك من إنشاء ملفات PDF باستخدام جداول تحتوي على بيانات من أوراق عمل Excel، مما يسهل مشاركة المعلومات والحفاظ عليها في تنسيق مستند محمول.

#### س: هل يمكنني تخصيص مظهر جدول PDF؟

ج: نعم، يمكنك تخصيص مظهر جدول PDF باستخدام الخصائص المتنوعة التي يوفرها Aspose.PDF لـ .NET. في كود مصدر C# المقدم، يمكنك تعديل عرض الأعمدة وحدود الخلايا ومحاذاة النص ونمط الخط والمزيد لتناسب متطلباتك المحددة.

#### س: كيف يمكنني التعامل مع ملفات Excel التي تحتوي على أوراق عمل متعددة؟

 ج: في كود C# المقدم، تمكنا من الوصول إلى ورقة العمل الأولى في ملف Excel باستخدام الفهرس`[0]` . إذا كان ملف Excel الخاص بك يحتوي على أوراق عمل متعددة، فيمكنك الوصول إليها عن طريق تغيير قيمة الفهرس وفقًا لذلك، مثل`[1]` لورقة العمل الثانية أو`[2]` لورقة العمل الثالثة .

#### س: هل يمكنني تطبيق تنسيق مختلف على صفوف أو خلايا معينة في جدول PDF؟

ج: نعم، يمكنك تطبيق تنسيق مختلف على صفوف أو خلايا معينة في جدول PDF. في كود مصدر C# المقدم، أوضحنا كيفية تنسيق الصف الأول والصفوف البديلة بشكل مختلف عن طريق تغيير لون الخلفية ونمط الخط ولون الخط. يمكنك تطبيق تقنيات تنسيق مماثلة على أي صفوف أو خلايا محددة حسب الحاجة.

#### س: هل Aspose.PDF for .NET هي المكتبة الوحيدة التي تسمح بتصدير بيانات Excel إلى جدول PDF؟

ج: Aspose.PDF for .NET هي مكتبة قوية للعمل مع مستندات PDF في تطبيقات .NET. على الرغم من احتمال توفر مكتبات أخرى، يقدم Aspose.PDF for .NET نطاقًا واسعًا من الميزات والإمكانيات لإنشاء ملفات PDF ومعالجتها وتصديرها باستخدام جداول من بيانات Excel، مما يجعله خيارًا شائعًا لمثل هذه المهام.