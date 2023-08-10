---
title: جدول في مقطع رأس تذييل
linktitle: جدول في مقطع رأس تذييل
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة جدول في قسم الرأس / التذييل في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 170
url: /ar/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية إضافة جدول في قسم الرأس أو التذييل في مستند PDF باستخدام Aspose.PDF for .NET. يوضح لك كود المصدر C # المقدم كيفية إنشاء مستند PDF فارغ وإضافة صفحة وتكوين قسم الرأس وإنشاء جدول وإضافة صفوف وخلايا إلى الجدول وأخيراً حفظ مستند PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة 2: إنشاء مستند PDF وصفحة

 تتمثل الخطوة الأولى في إنشاء مثيل لملف`Document` فئة وإضافة صفحة إلى المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن مستند
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// قم بإنشاء صفحة في مستند PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث تريد حفظ مستند PDF.

## الخطوة 3: تكوين قسم الرأس

 سنقوم الآن بتكوين قسم الرأس في مستند PDF عن طريق إنشاء مثيل لملف`HeaderFooter` فصل. إليك الطريقة:

```csharp
// قم بإنشاء قسم رأس لملف PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// حدد قسم رأس الصفحة
page. Header = header;

//قم بتعيين الهامش العلوي لقسم الرأس
header. Margin. Top = 20;
```

## الخطوة 4: إنشاء الجدول

 الآن سنقوم بإنشاء جدول باستخدام`Table` class وإضافتها إلى مجموعة فقرات قسم العنوان. إليك الطريقة:

```csharp
// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// أضف الجدول إلى مجموعة فقرات قسم الرأس
header.Paragraphs.Add(tab1);

// تحديد عروض أعمدة الجدول
tab1.ColumnWidths = "60,300";
```

يقوم الكود أعلاه بإنشاء جدول بعمودين بعرض محدد.

## الخطوة 5: أضف صفوفًا وخلايا إلى الجدول

 سنضيف الآن صفوفًا وخلايا إلى الجدول باستخدام امتداد`Row` الطبقة و`Cell` فصل. إليك الطريقة:

```csharp
// أنشئ صفًا في الجدول وأضف الخلايا
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// دمج الخلية الأولى في الصف الأول
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// أنشئ صفًا آخر في الجدول وأضف خلية بها صورة
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## الخطوة 6: حفظ مستند PDF

بمجرد إضافة الجدول إلى قسم الرأس ، يمكننا حفظ مستند PDF. إليك الطريقة:

```csharp
//احفظ ملف PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث تريد حفظ مستند PDF.

### نموذج التعليمات البرمجية المصدر لـ Table In Header Footer Section باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مثيل المستند عن طريق استدعاء مُنشئ فارغ
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//قم بإنشاء صفحة في مستند pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// قم بإنشاء قسم رأس من ملف PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// قم بتعيين الرأس الفردي لملف PDF
page.Header = header;

// قم بتعيين الهامش العلوي لقسم الرأس
header.Margin.Top = 20;

// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// أضف الجدول في مجموعة فقرات القسم المطلوب
header.Paragraphs.Add(tab1);

// تعيين حد الخلية الافتراضي باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// اضبط مع عرض أعمدة الجدول
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// قم بتعيين قيمة امتداد الصف للصف الأول على 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// عيّن لون الخلفية للصف 2
row2.BackgroundColor = Color.White;

// أضف الخلية التي تحتوي على الصورة
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// اضبط عرض الصورة على 60
img.FixWidth = 60;

// أضف الصورة إلى خلية الجدول
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// قم بتعيين المحاذاة الرأسية للنص كمحاذاة للوسط
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// احفظ ملف Pdf
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة جدول في قسم الرأس أو التذييل لمستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تخصيص الرؤوس والتذييلات الخاصة بك عن طريق إضافة جداول لعرض معلومات إضافية في مستندات PDF الخاصة بك.

### الأسئلة الشائعة للجدول في قسم رأس وتذييل الصفحة

#### س: ما هو الغرض من إضافة جدول في قسم الرأس أو التذييل في مستند PDF؟

ج: تسمح لك إضافة جدول في قسم الرأس أو التذييل في مستند PDF بعرض معلومات منظمة ومنظمة مثل العناوين أو العناوين الفرعية أو الشعارات أو أي محتوى آخر تريد أن يظهر بشكل متسق في كل صفحة من المستند.

#### س: كيف تحقق شفرة المصدر C # المقدمة إضافة جدول في قسم الرأس أو التذييل في مستند PDF؟

ج: يوضح الكود عملية إنشاء مستند PDF فارغ ، وإضافة صفحة ، وتكوين قسم الرأس ، وإنشاء جدول به صفوف وخلايا ، وأخيراً حفظ مستند PDF. والنتيجة هي جدول معروض في قسم رأس وثيقة PDF.

#### س: هل يمكنني تخصيص مظهر خلايا الجدول ، مثل الحدود ولون الخلفية ونمط النص؟

ج: نعم ، يمكنك تخصيص مظهر خلايا الجدول عن طريق تعيين خصائص مثل حدود الخلية ولون الخلفية ونمط النص والخط وحجم الخط والمزيد.

#### س: كيف يتم إضافة الجدول إلى قسم الرأس في مستند PDF؟

ج: يضيف الكود الجدول إلى مجموعة فقرات قسم الرأس ، مما يضمن عرض الجدول في رأس كل صفحة.

#### س: هل يمكنني إضافة المزيد من الصفوف والخلايا إلى الجدول حسب الحاجة؟

 ج: بالتأكيد ، يمكنك إضافة المزيد من الصفوف والخلايا إلى الجدول باستخدام ملف`Rows.Add()` و`Cells.Add()` طُرق. يتيح لك هذا هيكلة محتوى الجدول حسب الرغبة.

#### س: هل يمكن تعديل عرض أعمدة الجدول؟
 ج: نعم ، يمكنك ضبط عرض أعمدة الجدول باستخدام امتداد`ColumnWidths` ملكية. يمكّنك هذا من التحكم في تخطيط الجدول.

#### س: كيف يمكنني تمديد الخلايا عبر عدة أعمدة أو صفوف داخل الجدول؟
 ج: لتمديد الخلايا عبر أعمدة متعددة ، يمكنك استخدام`ColSpan`خاصية الخلية المقابلة. وبالمثل ، يمكنك استخدام ملف`RowSpan` خاصية لتمديد الخلايا عبر صفوف متعددة.

#### س: ماذا يحدث إذا كنت أرغب في إضافة جدول إلى مقاطع الرأس والتذييل في مستند PDF؟

 ج: يمكنك اتباع نهج مماثل لكل من مقاطع الرأس والتذييل. ببساطة قم بإنشاء ملف`HeaderFooter` مثال للتذييل ، قم بتكوينه ، وإضافة الجدول إلى مجموعة فقراته.

#### س: هل يمكنني استخدام الصور داخل خلايا الجدول وكيف يتحقق ذلك؟

 ج: نعم ، يمكنك إضافة الصور داخل خلايا الجدول. يوضح مثال الكود إضافة صورة إلى خلية عن طريق إنشاء ملف`Image` الكائن ، وتحديد مسار الملف وأبعاده ، ثم إضافته إلى فقرات الخلية.

#### س: كيف يمكنني التأكد من ظهور الجدول بشكل متسق عبر جميع الصفحات في مستند PDF؟

 ج: عند إضافة الجدول إلى قسم الرأس أو التذييل باستخدام ملف`HeaderFooter` على سبيل المثال ، يضمن Aspose.PDF أن الجدول يظهر باستمرار في كل صفحة ، مما يوفر تخطيطًا موحدًا.