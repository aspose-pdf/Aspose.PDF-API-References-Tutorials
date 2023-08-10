---
title: تصدير بيانات ورقة عمل Excel إلى جدول
linktitle: تصدير بيانات ورقة عمل Excel إلى جدول
second_title: Aspose.PDF لمرجع .NET API
description: قم بتصدير البيانات من ورقة Excel إلى جدول PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 70
url: /ar/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
في هذا البرنامج التعليمي ، سوف نتعلم كيفية تصدير البيانات من ورقة عمل Excel وإنشاء جدول في مستند PDF باستخدام Aspose.PDF لمكتبة .NET. سنستعرض التعليمات البرمجية المصدر خطوة بخطوة وسنشرح كل قسم بالتفصيل. بنهاية هذا البرنامج التعليمي ، ستتمكن من إنشاء ملفات PDF بجداول تحتوي على بيانات من أوراق عمل Excel. هيا بنا نبدأ!

## متطلبات
قبل أن نبدأ ، تأكد من توفر لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C #
- تم تثبيت Visual Studio على جهازك
- تمت إضافة Aspose.PDF لمكتبة .NET إلى مشروعك

## الخطوة الأولى: تهيئة البيئة
للبدء ، قم بإنشاء مشروع C # جديد في Visual Studio. أضف المرجع إلى Aspose.PDF لمكتبة .NET عن طريق النقر بزر الماوس الأيمن على مشروعك في Solution Explorer ، واختيار "Manage NuGet Packages" ، والبحث عن Aspose.PDF. قم بتثبيت الحزمة وأنت على استعداد للذهاب.

## الخطوة 2: تحميل ورقة عمل Excel
في الخطوة الأولى من الكود الخاص بنا ، نحدد المسار إلى الدليل الذي يحتوي على مستند Excel. استبدل "دليل المستند" بمسار الدليل الفعلي حيث يوجد ملف Excel.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

هنا ، نستخدم مكتبة Aspose.Cells لتحميل مصنف Excel. تأكد من استبدال "newBook1.xlsx" باسم ملف Excel الخاص بك.

## الخطوة 3: الوصول إلى ورقة العمل
 بعد ذلك ، نحتاج إلى الوصول إلى ورقة العمل الأولى في ملف Excel. نفعل هذا باستخدام`Worksheets` جمع`Workbook` هدف.

```csharp
// الوصول إلى ورقة العمل الأولى في ملف Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 إذا كان ملف Excel يحتوي على أوراق عمل متعددة ، فيمكنك تغيير قيمة الفهرس`[0]` للوصول إلى ورقة عمل مختلفة.

## الخطوة 4: تصدير البيانات إلى DataTable
 الآن ، سنقوم بتصدير محتويات ورقة عمل Excel إلى ملف`DataTable` هدف. نحدد نطاق الخلايا المراد تصديرها باستخدام ملف`ExportDataTable` طريقة.

```csharp
// تصدير محتويات 7 صفوف وعمودين بدءًا من الخلية الأولى إلى DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

في هذا المثال ، نقوم بتصدير جميع الصفوف والأعمدة بدءًا من الخلية الأولى (0 ، 0) إلى الخلية الأخيرة في ورقة العمل. حدد النطاق المناسب بناءً على متطلباتك.

## الخطوة 5: إنشاء مستند PDF
الآن ، سنقوم بإنشاء مستند PDF جديد باستخدام مكتبة Aspose.PDF.

```csharp
// إنشاء مثيل المستند
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

يؤدي هذا إلى إنشاء مستند PDF فارغ حيث يمكننا إضافة المحتوى.

## الخطوة 6: إضافة صفحة وجدول
لعرض البيانات بتنسيق جدول ، نحتاج إلى إضافة صفحة وجدول إلى مستند PDF.

```csharp
// قم بإنشاء صفحة في نسخة المستند
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// قم بإنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// أضف كائن الجدول في مجموعة فقرات القسم
sec1.Paragraphs.Add(tab1);
```

هنا ، نقوم بإنشاء صفحة جديدة وكائن جدول. ثم نضيف الجدول إلى مجموعة فقرات الصفحة.

## الخطوة 7: ضبط خصائص الجدول
قبل استيراد البيانات ، نحتاج إلى تعيين بعض خصائص الجدول ، مثل عرض الأعمدة وحدود الخلية الافتراضية.

```csharp
// تعيين عرض أعمدة الجدول
tab1.ColumnWidths = "40 100 100";

// قم بتعيين حد الخلية الافتراضي للجدول باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

في هذا المثال ، قمنا بتعيين عرض العمود على 40 و 100 و 100 وحدة. اضبط القيم بناءً على بياناتك. قمنا أيضًا بتعيين حدود الخلية الافتراضية لعرض الحدود على جميع جوانب كل خلية.

## الخطوة 8: استيراد البيانات إلى الجدول
 الآن ، سنقوم باستيراد البيانات من ملف`DataTable` كائن في الجدول باستخدام`ImportDataTable` طريقة.

```csharp
// استيراد البيانات إلى كائن الجدول من DataTable الذي تم إنشاؤه أعلاه
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 هنا ، نحدد نطاق الصفوف والأعمدة المراد استيرادها. في هذا المثال ، نقوم باستيراد جميع الصفوف والأعمدة من ملف`dataTable` هدف.

## الخطوة 9: تنسيق الجدول
لتحسين مظهر الجدول ، يمكننا تطبيق التنسيق على خلايا أو صفوف معينة. في هذه الخطوة ، سنقوم بتنسيق الصف الأول والصفوف البديلة من الجدول.

```csharp
// احصل على الصف الأول من الجدول
Aspose.Pdf.Row row1 = tab1.Rows[0];

// تنسيق الصف الأول
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // عيّن لون خلفية الخلايا في الصف الأول
     curCell.BackgroundColor = Color.Blue;// اضبط الوجه للخلايا في الصف الأول
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // عيّن لون خط الخلايا في الصف الأول
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // قم بتعيين محاذاة النص للخلايا في الصف الأول
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// تنسيق الصف البديل
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // عيّن لون خلفية الخلايا في صفوف بديلة
         curCell.BackgroundColor = Color.Gray;
        
         // عيّن لون نص الخلايا في صفوف بديلة
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

هنا ، نقوم بالتكرار خلال الخلايا في الصف الأول وتعيين لون الخلفية ووجه الخط ولون الخط ومحاذاة النص. بعد ذلك ، نقوم بالتكرار خلال جميع الخلايا في الصفوف البديلة وتعيين الخلفية ولون النص.

## الخطوة 10: حفظ مستند PDF
أخيرًا ، نحفظ مستند PDF في الموقع المحدد.

```csharp
// احفظ ملف PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

تأكد من استبدال "دليل المستند" بمسار الدليل المطلوب واسم الملف لملف PDF الناتج.

### مثال على التعليمات البرمجية المصدر لتصدير بيانات ورقة عمل Excel إلى جدول باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// الوصول إلى ورقة العمل الأولى في ملف Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// تصدير محتويات 7 صفوف وعمودين بدءًا من الخلية الأولى إلى DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// إنشاء مستند instanc
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// قم بإنشاء صفحة في نسخة المستند
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// قم بإنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// أضف كائن الجدول في مجموعة فقرات القسم
sec1.Paragraphs.Add(tab1);

// تعيين عرض أعمدة الجدول. نحتاج إلى تحديد ColumnCount يدويًا.
// نظرًا لأن ورقة عمل Excel الحالية تحتوي على ثلاثة أعمدة ، فإننا نحدد نفس العدد
tab1.ColumnWidths = "40 100 100";

// قم بتعيين حد الخلية الافتراضي للجدول باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// استيراد البيانات إلى كائن الجدول من DataTable الذي تم إنشاؤه أعلاه
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// احصل على الصف الأول من الجدول
Aspose.Pdf.Row row1 = tab1.Rows[0];

// كرر عبر جميع الخلايا في الصف الأول واضبط لون الخلفية على اللون الأزرق
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// عيّن خلفية جميع الخلايا في الصف الأول من الجدول.
	curCell.BackgroundColor = Color.Blue;
	// عيّن وجه الخط لخلايا الصف الأول في الجدول.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// عيّن لون الخط لجميع الخلايا في الصف الأول من الجدول.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// قم بتعيين محاذاة النص لخلايا الصف الأول كمركز.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// كرر عبر جميع الخلايا في الصف الأول واضبط لون الخلفية على اللون الأزرق
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// عيّن لون الخلفية لجميع الخلايا باستثناء الصف الأول.
		curCell.BackgroundColor = Color.Gray;
		// عيّن لون النص لجميع الخلايا باستثناء الصف الأول.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// احفظ ملف PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تصدير البيانات من ورقة عمل Excel إلى جدول PDF باستخدام Aspose.PDF لمكتبة .NET. لقد غطينا العملية خطوة بخطوة لتحميل ورقة عمل Excel ، وإنشاء مستند PDF ، وإضافة جدول ، واستيراد البيانات ، وتنسيق الجدول. يمكنك الآن إنشاء ملفات PDF بجداول تحتوي على بيانات Excel برمجيًا.

### التعليمات

#### س: ما هو الغرض من تصدير بيانات ورقة عمل Excel إلى جدول PDF؟

ج: يتيح لك تصدير بيانات ورقة عمل Excel إلى جدول PDF تقديم البيانات بتنسيق منظم ومنظم. يمكّنك من إنشاء ملفات PDF بجداول تحتوي على بيانات من أوراق عمل Excel ، مما يسهل مشاركة المعلومات والاحتفاظ بها في تنسيق مستند محمول.

#### س: هل يمكنني تخصيص مظهر جدول PDF؟

ج: نعم ، يمكنك تخصيص مظهر جدول PDF باستخدام الخصائص المتنوعة التي يوفرها Aspose.PDF لـ .NET. في التعليمات البرمجية المصدر C # المقدمة ، يمكنك تعديل عرض الأعمدة وحدود الخلية ومحاذاة النص ونمط الخط والمزيد لتناسب متطلباتك المحددة.

#### س: كيف يمكنني التعامل مع ملفات Excel ذات أوراق العمل المتعددة؟

 ج: في كود C # المقدم ، وصلنا إلى ورقة العمل الأولى في ملف Excel باستخدام الفهرس`[0]` . إذا كان ملف Excel يحتوي على أوراق عمل متعددة ، فيمكنك الوصول إليها عن طريق تغيير قيمة الفهرس وفقًا لذلك ، مثل`[1]` لورقة العمل الثانية أو`[2]` لورقة العمل الثالثة.

#### س: هل يمكنني تطبيق تنسيقات مختلفة على صفوف أو خلايا معينة في جدول PDF؟

ج: نعم ، يمكنك تطبيق تنسيقات مختلفة على صفوف أو خلايا معينة في جدول PDF. في الكود المصدري C # المقدم ، أوضحنا كيفية تنسيق الصف الأول والصفوف البديلة بشكل مختلف عن طريق تغيير لون الخلفية ونمط الخط ولون الخط. يمكنك تطبيق تقنيات تنسيق مماثلة على أي صفوف أو خلايا محددة حسب الحاجة.

#### س: هل Aspose.PDF for .NET هي المكتبة الوحيدة التي تسمح بتصدير بيانات Excel إلى جدول PDF؟

ج: Aspose.PDF for .NET مكتبة قوية للعمل مع مستندات PDF في تطبيقات .NET. بينما قد تكون هناك مكتبات أخرى متاحة ، يقدم Aspose.PDF for .NET مجموعة واسعة من الميزات والإمكانيات لإنشاء ملفات PDF ومعالجتها وتصديرها بجداول من بيانات Excel ، مما يجعلها خيارًا شائعًا لمثل هذه المهام.