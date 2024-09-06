---
title: الجدول في قسم التذييل والرأس
linktitle: الجدول في قسم التذييل والرأس
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة جدول في قسم الرأس/التذييل في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 170
url: /ar/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية إضافة جدول في قسم الرأس أو التذييل في مستند PDF باستخدام Aspose.PDF for .NET. يوضح لك كود المصدر C# المقدم كيفية إنشاء مستند PDF فارغ، وإضافة صفحة، وتكوين قسم الرأس، وإنشاء جدول، وإضافة صفوف وخلايا إلى الجدول، وأخيرًا حفظ مستند PDF.

## الخطوة 1: إعداد البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: إنشاء مستند PDF والصفحة

 الخطوة الأولى هي إنشاء مثيل لـ`Document` قم بإنشاء فصل دراسي وأضف صفحة إلى المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن مستند
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// إنشاء صفحة في مستند PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي تريد حفظ مستند PDF فيه.

## الخطوة 3: تكوين قسم الرأس

 سنقوم الآن بتكوين قسم الرأس لمستند PDF عن طريق إنشاء مثيل لـ`HeaderFooter` الصف. إليك الطريقة:

```csharp
// إنشاء قسم رأسي لملف PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// تحديد قسم الرأس للصفحة
page. Header = header;

// تعيين الهامش العلوي لقسم الرأس
header. Margin. Top = 20;
```

## الخطوة 4: إنشاء الجدول

 الآن سنقوم بإنشاء جدول باستخدام`Table` قم بإضافتها إلى مجموعة فقرات قسم العنوان. إليك الطريقة:

```csharp
// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// أضف الجدول إلى مجموعة الفقرات في قسم الرأس
header.Paragraphs.Add(tab1);

// تحديد عرض أعمدة الجدول
tab1.ColumnWidths = "60,300";
```

يقوم الكود أعلاه بإنشاء جدول يحتوي على عمودين بعرض محدد.

## الخطوة 5: إضافة صفوف وخلايا إلى الجدول

 الآن سوف نضيف صفوفًا وخلايا إلى الجدول باستخدام`Row` الصف و`Cell` الصف. إليك الطريقة:

```csharp
// إنشاء صف في الجدول وإضافة خلايا
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// دمج الخلية الأولى من الصف الأول
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// إنشاء صف آخر في الجدول وإضافة خلية تحتوي على صورة
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

بمجرد إضافة الجدول إلى قسم الرأس، يمكننا حفظ مستند PDF. إليك الطريقة:

```csharp
// حفظ ملف PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي تريد حفظ مستند PDF فيه.

### عينة من كود المصدر للجدول في قسم الرأس والتذييل باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مثيل مستند عن طريق استدعاء المنشئ الفارغ
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// إنشاء صفحة في مستند pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//إنشاء قسم رأسي لملف PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// تعيين رأس الصفحة الفردية لملف PDF
page.Header = header;

// تعيين الهامش العلوي لقسم الرأس
header.Margin.Top = 20;

// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// أضف الجدول في مجموعة فقرات القسم المطلوب
header.Paragraphs.Add(tab1);

// تعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// مجموعة مع عرض أعمدة الجدول
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// إنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// تعيين قيمة امتداد الصف للصف الأول على 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// إنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// تعيين لون الخلفية للصف الثاني
row2.BackgroundColor = Color.White;

// أضف الخلية التي تحتوي على الصورة
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// ضبط عرض الصورة إلى 60
img.FixWidth = 60;

// أضف الصورة إلى خلية الجدول
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// تعيين محاذاة النص العمودية إلى المنتصف
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// حفظ ملف PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## خاتمة

تهانينا! لقد تعلمت كيفية إضافة جدول في قسم الرأس أو التذييل في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تخصيص الرؤوس والتذييلات الخاصة بك عن طريق إضافة جداول لعرض معلومات إضافية في مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول الجدول الموجود في قسم التذييل والرأس

#### س: ما هو الغرض من إضافة جدول في قسم الرأس أو التذييل في مستند PDF؟

أ: إضافة جدول في قسم الرأس أو التذييل في مستند PDF يسمح لك بعرض معلومات منظمة ومهيكلة مثل العناوين أو العناوين الفرعية أو الشعارات أو أي محتوى آخر تريد ظهوره بشكل متسق في كل صفحة من المستند.

#### س: كيف يقوم كود المصدر C# المقدم بتحقيق إضافة جدول في قسم الرأس أو التذييل في مستند PDF؟

ج: يوضح الكود عملية إنشاء مستند PDF فارغ، وإضافة صفحة، وتكوين قسم الرأس، وإنشاء جدول يحتوي على صفوف وخلايا، وأخيرًا حفظ مستند PDF. والنتيجة هي جدول معروض في قسم الرأس بمستند PDF.

#### س: هل يمكنني تخصيص مظهر خلايا الجدول، مثل الحدود ولون الخلفية ونمط النص؟

ج: نعم، يمكنك تخصيص مظهر خلايا الجدول عن طريق تعيين خصائص مثل حدود الخلايا ولون الخلفية ونمط النص والخط وحجم الخط والمزيد.

#### س: كيف تتم إضافة الجدول إلى قسم الرأس في مستند PDF؟

ج: يقوم الكود بإضافة الجدول إلى مجموعة الفقرات في قسم الرأس، مما يضمن عرض الجدول في رأس كل صفحة.

#### س: هل يمكنني إضافة المزيد من الصفوف والخلايا إلى الجدول حسب الحاجة؟

 ج: بالتأكيد، يمكنك إضافة المزيد من الصفوف والخلايا إلى الجدول باستخدام`Rows.Add()` و`Cells.Add()` الأساليب. وهذا يسمح لك بتنظيم محتوى الجدول حسب رغبتك.

#### س: هل من الممكن تعديل عرض أعمدة الجدول؟
 ج: نعم، يمكنك تعديل عرض أعمدة الجدول باستخدام`ColumnWidths` يتيح لك هذا التحكم في تخطيط الجدول.

#### س: كيف يمكنني توزيع الخلايا عبر عدة أعمدة أو صفوف داخل الجدول؟
 أ: لتمديد الخلايا عبر أعمدة متعددة، يمكنك استخدام`ColSpan`خاصية الخلية المقابلة. وبالمثل، يمكنك استخدام`RowSpan` الخاصية لتمتد الخلايا عبر عدة صفوف.

#### س: ماذا يحدث إذا أردت إضافة جدول إلى كل من أقسام الرأس والتذييل في مستند PDF؟

 ج: يمكنك اتباع نهج مماثل لكل من أقسام الرأس والتذييل. ما عليك سوى إنشاء`HeaderFooter` مثال للتذييل، قم بتكوينه، ثم أضف الجدول إلى مجموعة الفقرات الخاصة به.

#### س: هل يمكنني استخدام الصور داخل خلايا الجدول، وكيف يتم ذلك؟

 ج: نعم، يمكنك إضافة صور داخل خلايا الجدول. يوضح مثال التعليمات البرمجية إضافة صورة إلى خلية من خلال إنشاء`Image` الكائن، وتعيين مسار ملفه وأبعاده، ثم إضافته إلى فقرات الخلية.

#### س: كيف يمكنني التأكد من ظهور الجدول بشكل متسق في جميع الصفحات في مستند PDF؟

 أ: عند إضافة الجدول إلى قسم الرأس أو التذييل باستخدام`HeaderFooter` على سبيل المثال، يضمن Aspose.PDF ظهور الجدول بشكل متسق في كل صفحة، مما يوفر تخطيطًا موحدًا.