---
title: تحديد فاصل الجدول في ملف PDF
linktitle: تحديد فاصل الجدول في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تحديد فواصل الجدول في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 60
url: /ar/net/programming-with-tables/determine-table-break/
---
في هذا البرنامج التعليمي، سنتعلم كيفية تحديد فواصل الجداول في ملف PDF باستخدام Aspose.PDF لـ .NET. وسنشرح التعليمات البرمجية المصدرية بلغة C# خطوة بخطوة. وفي نهاية هذا البرنامج التعليمي، ستعرف كيفية تحديد ما إذا كان الجدول يتجاوز هوامش الصفحة. فلنبدأ!

## الخطوة 1: إعداد البيئة
أولاً، تأكد من إعداد بيئة تطوير C# الخاصة بك باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد المساحات الأساسية اللازمة.

## الخطوة 2: إنشاء مستند PDF
 في هذه الخطوة نقوم بإنشاء ملف جديد`Document` كائن لتمثيل مستند PDF.

```csharp
pdf-Document = new Document();
```

سيتم استخدام هذه الوثيقة لإضافة الأقسام والجداول.

## الخطوة 3: إضافة قسم وجدول
سنقوم الآن بإضافة قسم إلى مستند PDF الخاص بنا وإنشاء جدول داخل هذا القسم.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

كما حددنا هامشًا أعلى للجدول يبلغ 300 نقطة. ويمكنك تعديل هذه القيمة وفقًا لاحتياجاتك.

## الخطوة 4: إعداد الجدول
في هذه الخطوة، نقوم بتكوين خصائص الجدول، مثل عرض الأعمدة والحدود.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

هنا نقوم بتحديد عرض أعمدة الجدول وحدود الخلايا. يمكنك تعديل هذه القيم وفقًا لتفضيلاتك.

## الخطوة 5: إضافة صفوف وخلايا إلى الجدول
الآن سوف نقوم بإنشاء صفوف وخلايا في الجدول باستخدام حلقة.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

هنا نقوم بإنشاء 17 صفًا في الجدول ونضيف ثلاث خلايا لكل صف. يمكنك ضبط الإبزيم وفقًا لاحتياجاتك.

## الخطوة 6: تحديد فواصل الجدول
الآن سوف نحدد ما إذا كان الجدول يتجاوز هوامش الصفحة عن طريق مقارنة ارتفاع الصفحة مع الارتفاع الإجمالي للأشياء الموجودة في الجدول.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

نقوم بحساب ارتفاع الصفحة والارتفاع الإجمالي للأشياء مع مراعاة الهوامش. إذا كان الفرق 10 أو أقل، فإن الجدول يتجاوز هوامش الصفحة.

## الخطوة 7: حفظ مستند PDF
وأخيرًا، نحفظ مستند PDF مع النتائج.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

تأكد من تحديد دليل المستند الصحيح. سيتم حفظ ملف PDF الناتج مع فواصل الجدول المحددة.

### مثال على كود المصدر لتحديد فاصل الجدول باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن من فئة PDF
Document pdf = new Document();
// أضف القسم إلى مجموعة أقسام مستند PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// إنشاء كائن جدول
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// أضف الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(table1);
// مجموعة مع عرض أعمدة الجدول
table1.ColumnWidths = "100 100 100";
// تعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// تعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// إنشاء كائن MarginInfo وتعيين هوامشه اليسرى والسفلى واليمنى والعلوية
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// تعيين الحشو الافتراضي للخلية إلى كائن MarginInfo
table1.DefaultCellPadding = margin;
// إذا قمت بزيادة العداد إلى 17، فسوف تنكسر الطاولة
// لأنه لا يمكن استيعاب المزيد من خلال هذه الصفحة
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//إنشاء صفوف في الجدول ثم خلايا في الصفوف
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// احصل على معلومات ارتفاع الصفحة
float PageHeight = (float)pdf.PageInfo.Height;
// احصل على معلومات الارتفاع الإجمالي للهوامش العلوية والسفلية للصفحة،
// هامش أعلى الجدول وارتفاع الجدول.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// عرض ارتفاع الصفحة وارتفاع الجدول وحاشية أعلى الجدول وأعلى الصفحة
// ومعلومات الهامش السفلي
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// تحقق مما إذا كنا نطرح مجموع هامش أعلى الصفحة + هامش أسفل الصفحة
// + هامش أعلى الجدول وارتفاع الجدول من ارتفاع الصفحة وأقل
// أقل من 10 (يمكن أن يكون الصف المتوسط أكبر من 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// إذا كانت القيمة أقل من 10، قم بعرض الرسالة.
	//مما يدل على أنه لا يمكن وضع صف آخر وإذا أضفنا صفًا جديدًا
	// سيتم كسر الصف والجدول. يعتمد ذلك على قيمة ارتفاع الصف.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// حفظ مستند pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تحديد فواصل الجداول في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل خطوة بخطوة للتحقق مما إذا كان الجدول يتجاوز هوامش الصفحة في مشاريع C# الخاصة بك.

### الأسئلة الشائعة حول تحديد فاصل الجدول في ملف PDF

#### س: ما هو الغرض من تحديد فواصل الجدول في مستند PDF؟

ج: الغرض من تحديد فواصل الجدول في مستند PDF هو التحقق مما إذا كان الجدول يتجاوز هوامش الصفحة. وهذا يضمن عرض محتوى الجدول بشكل صحيح ضمن مساحة الصفحة المتاحة. من خلال اكتشاف فواصل الجدول، يمكنك التعامل مع تجاوز المحتوى وضبط تخطيط الجدول وفقًا لذلك.

#### س: كيف يمكنني تعديل الهامش العلوي للجدول؟

 أ: في كود المصدر C# المقدم، يمكنك تعديل الهامش العلوي للجدول عن طريق تعديل قيمة`table1.Margin.Top`الخاصية. قم بزيادة أو تقليل القيمة حسب الحاجة لتعيين الهامش العلوي المطلوب للجدول.

#### س: هل يمكنني تخصيص مظهر الجدول، مثل ألوان الخلايا وحجم الخط؟

ج: نعم، يمكنك تخصيص مظهر الجدول وخلاياه باستخدام خصائص وطرق مختلفة يوفرها Aspose.PDF لـ .NET. على سبيل المثال، يمكنك تغيير ألوان خلفية الخلية وحجم الخط وعائلة الخط ومحاذاة النص والمزيد. راجع الوثائق الرسمية للحصول على مزيد من المعلومات حول كيفية تخصيص مظهر الجدول.

#### س: ماذا يحدث إذا تجاوز الجدول هوامش الصفحة؟

ج: إذا تجاوز الجدول هوامش الصفحة، فقد يؤدي ذلك إلى اقتطاع المحتوى أو تداخله، مما يجعل مستند PDF أقل قابلية للقراءة والتنظيم. من خلال اكتشاف فواصل الجدول والتعامل مع الفائض، يمكنك التأكد من أن المحتوى يظل معروضًا بشكل صحيح ضمن منطقة الصفحة المتاحة.

#### س: هل يمكنني تحديد فواصل الجداول لعدة جداول في نفس مستند PDF؟

ج: نعم، يمكنك تحديد فواصل الجداول لعدة جداول في نفس مستند PDF. ما عليك سوى تكرار الخطوات لكل جدول تريد تحليله وتعديل تخطيط الجدول حسب الضرورة لمنع تجاوز المحتوى.