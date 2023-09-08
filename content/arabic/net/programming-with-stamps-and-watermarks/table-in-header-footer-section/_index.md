---
title: الجدول في قسم تذييل الرأس
linktitle: الجدول في قسم تذييل الرأس
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة جدول في قسم الرأس/التذييل لمستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 170
url: /ar/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية إضافة جدول في قسم الرأس أو التذييل لمستند PDF باستخدام Aspose.PDF لـ .NET. يوضح لك كود مصدر C# المقدم كيفية إنشاء مستند PDF فارغ، وإضافة صفحة، وتكوين قسم الرأس، وإنشاء جدول، وإضافة صفوف وخلايا إلى الجدول، وأخيرًا حفظ مستند PDF.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF الخاصة بـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: إنشاء مستند وصفحة PDF

 الخطوة الأولى هي إنشاء مثيل لـ`Document` فئة وإضافة صفحة إلى المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء مثيل لكائن المستند
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// قم بإنشاء صفحة في مستند PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي تريد حفظ مستند PDF فيه.

## الخطوة 3: تكوين قسم الرأس

 سنقوم الآن بتكوين قسم الرأس في مستند PDF عن طريق إنشاء مثيل لـ`HeaderFooter` فصل. إليك الطريقة:

```csharp
// قم بإنشاء قسم رأس لملف PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// تحديد قسم الرأس للصفحة
page. Header = header;

// قم بتعيين الهامش العلوي لقسم الرأس
header. Margin. Top = 20;
```

## الخطوة 4: إنشاء الجدول

 الآن سنقوم بإنشاء جدول باستخدام`Table` class وإضافته إلى مجموعة فقرات قسم العنوان. إليك الطريقة:

```csharp
// إنشاء مثيل لكائن الجدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// أضف الجدول إلى مجموعة الفقرات في قسم الرأس
header.Paragraphs.Add(tab1);

// تحديد عرض أعمدة الجدول
tab1.ColumnWidths = "60,300";
```

يقوم الكود أعلاه بإنشاء جدول بعمودين بعرض محدد.

## الخطوة 5: إضافة صفوف وخلايا إلى الجدول

 الآن سنقوم بإضافة صفوف وخلايا إلى الجدول باستخدام الأمر`Row` الطبقة و`Cell` فصل. إليك الطريقة:

```csharp
// أنشئ صفًا في الجدول وأضف الخلايا
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// دمج الخلية الأولى من الصف الأول
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// أنشئ صفًا آخر في الجدول وأضف خلية تحتوي على صورة
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
// احفظ ملف PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي تريد حفظ مستند PDF فيه.

### نموذج التعليمات البرمجية المصدر للجدول في قسم تذييل الرأس باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مثيل للمستند عن طريق استدعاء مُنشئ فارغ
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// إنشاء صفحة في مستند pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// قم بإنشاء قسم رأس لملف PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//قم بتعيين الرأس الفردي لملف PDF
page.Header = header;

// قم بتعيين الهامش العلوي لقسم الرأس
header.Margin.Top = 20;

// إنشاء مثيل لكائن الجدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// إضافة الجدول في مجموعة فقرات القسم المطلوب
header.Paragraphs.Add(tab1);

// قم بتعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// تعيين مع عرض أعمدة الجدول
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// قم بإنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// قم بتعيين قيمة امتداد الصف للصف الأول على 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// قم بإنشاء صفوف في الجدول ثم خلايا في الصفوف
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// قم بتعيين لون الخلفية للصف 2
row2.BackgroundColor = Color.White;

// أضف الخلية التي تحتوي على الصورة
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// اضبط عرض الصورة على 60
img.FixWidth = 60;

// أضف الصورة إلى خلية الجدول
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// قم بتعيين المحاذاة العمودية للنص كمحاذاة للوسط
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// احفظ ملف PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة جدول في قسم الرأس أو التذييل لمستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تخصيص الرؤوس والتذييلات الخاصة بك عن طريق إضافة جداول لعرض معلومات إضافية في مستندات PDF الخاصة بك.

### الأسئلة الشائعة للجدول في قسم تذييل الرأس

#### س: ما هو الغرض من إضافة جدول في قسم الرأس أو التذييل لمستند PDF؟

ج: تتيح لك إضافة جدول في قسم الرأس أو التذييل لمستند PDF عرض معلومات منظمة ومنظمة مثل العناوين أو الترجمة أو الشعارات أو أي محتوى آخر تريده أن يظهر بشكل متسق في كل صفحة من المستند.

#### س: كيف يحقق كود مصدر C# المقدم إضافة جدول في قسم الرأس أو التذييل لمستند PDF؟

ج: يوضح الكود عملية إنشاء مستند PDF فارغ، وإضافة صفحة، وتكوين قسم الرأس، وإنشاء جدول يحتوي على صفوف وخلايا، وأخيرًا حفظ مستند PDF. والنتيجة هي جدول معروض في قسم الرأس في مستند PDF.

#### س: هل يمكنني تخصيص مظهر خلايا الجدول، مثل الحدود ولون الخلفية ونمط النص؟

ج: نعم، يمكنك تخصيص مظهر خلايا الجدول عن طريق تعيين خصائص مثل حدود الخلايا ولون الخلفية ونمط النص والخط وحجم الخط والمزيد.

#### س: كيف تتم إضافة الجدول إلى قسم الرأس في مستند PDF؟

ج: يضيف الكود الجدول إلى مجموعة الفقرات في قسم الرأس، مما يضمن عرض الجدول في رأس كل صفحة.

#### س: هل يمكنني إضافة المزيد من الصفوف والخلايا إلى الجدول حسب الحاجة؟

 ج: بالتأكيد، يمكنك إضافة المزيد من الصفوف والخلايا إلى الجدول باستخدام الأمر`Rows.Add()` و`Cells.Add()` طُرق. يتيح لك ذلك تنظيم محتوى الجدول حسب الرغبة.

#### س: هل يمكن تعديل عرض أعمدة الجدول؟
 ج: نعم، يمكنك ضبط عرض أعمدة الجدول باستخدام`ColumnWidths` ملكية. يتيح لك هذا التحكم في تخطيط الجدول.

#### س: كيف يمكنني تمديد الخلايا عبر أعمدة أو صفوف متعددة داخل الجدول؟
 ج: لتوزيع الخلايا عبر أعمدة متعددة، يمكنك استخدام الخيار`ColSpan` خاصية الخلية المقابلة. وبالمثل، يمكنك استخدام`RowSpan` خاصية تمديد الخلايا عبر صفوف متعددة.

#### س: ماذا يحدث إذا أردت إضافة جدول إلى كل من قسمي الرأس والتذييل في مستند PDF؟

ج: يمكنك اتباع أسلوب مماثل لكل من قسمي الرأس والتذييل. ببساطة قم بإنشاء`HeaderFooter` مثيل للتذييل، وتكوينه، وإضافة الجدول إلى مجموعة الفقرات الخاصة به.

#### س: هل يمكنني استخدام الصور داخل خلايا الجدول، وكيف يتم تحقيق ذلك؟

 ج: نعم، يمكنك إضافة صور داخل خلايا الجدول. يوضح مثال التعليمات البرمجية إضافة صورة إلى خلية عن طريق إنشاء ملف`Image` الكائن، وتعيين مسار الملف وأبعاده، ثم إضافته إلى فقرات الخلية.

#### س: كيف أتأكد من ظهور الجدول بشكل متسق عبر جميع الصفحات في مستند PDF؟

 ج: عند إضافة الجدول إلى قسم الرأس أو التذييل باستخدام`HeaderFooter` على سبيل المثال، يضمن Aspose.PDF ظهور الجدول بشكل متسق في كل صفحة، مما يوفر تخطيطًا موحدًا.