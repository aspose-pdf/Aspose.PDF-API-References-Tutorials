---
title: تحديد فاصل الجدول في ملف PDF
linktitle: تحديد فاصل الجدول في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد فواصل الجدول في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 60
url: /ar/net/programming-with-tables/determine-table-break/
---
في هذا البرنامج التعليمي، سنتعلم كيفية تحديد فواصل الجدول في ملف PDF باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري في لغة C# خطوة بخطوة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية تحديد ما إذا كان الجدول يتجاوز هوامش الصفحة. لنبدأ!

## الخطوة 1: تهيئة البيئة
أولاً، تأكد من قيامك بإعداد بيئة تطوير C# باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد مساحات الأسماء الضرورية.

## الخطوة 2: إنشاء وثيقة PDF
 في هذه الخطوة نقوم بإنشاء جديد`Document` كائن لتمثيل وثيقة PDF.

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

نحدد أيضًا هامشًا أعلى قدره 300 نقطة للجدول. يمكنك ضبط هذه القيمة وفقًا لاحتياجاتك.

## الخطوة 4: إعداد الجدول
في هذه الخطوة، نقوم بتكوين خصائص الجدول، مثل عرض الأعمدة والحدود.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

نحدد هنا عرض أعمدة الجدول وحدود الخلايا. يمكنك ضبط هذه القيم وفقًا لتفضيلاتك.

## الخطوة 5: إضافة صفوف وخلايا إلى الجدول
سنقوم الآن بإنشاء صفوف وخلايا في الجدول باستخدام حلقة.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

نقوم هنا بإنشاء 17 صفًا في الجدول وإضافة ثلاث خلايا إلى كل صف. يمكنك ضبط الإبزيم وفقًا لاحتياجاتك.

## الخطوة 6: تحديد فواصل الجدول
سنحدد الآن ما إذا كان الجدول يتجاوز هوامش الصفحة من خلال مقارنة ارتفاع الصفحة مع الارتفاع الإجمالي للكائنات الموجودة في الجدول.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

نقوم بحساب ارتفاع الصفحة والارتفاع الإجمالي للكائنات مع مراعاة الهوامش. إذا كان الفرق 10 أو أقل، فإن الجدول يتجاوز هوامش الصفحة.

## الخطوة 7: حفظ مستند PDF
وأخيرا، نقوم بحفظ وثيقة PDF مع النتائج.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

تأكد من تحديد دليل المستند الصحيح. سيتم حفظ ملف PDF الناتج مع فواصل الجدول المحددة.

### مثال للتعليمة البرمجية المصدر لتحديد فاصل الجدول باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مثيل لفئة PDF كائن
Document pdf = new Document();
// أضف القسم إلى مجموعة أقسام مستند PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// إنشاء مثيل لكائن الجدول
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// إضافة الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(table1);
// تعيين مع عرض أعمدة الجدول
table1.ColumnWidths = "100 100 100";
// قم بتعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// قم بتعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// قم بإنشاء كائن MarginInfo وقم بتعيين الهوامش اليسرى والسفلى واليمنى والعليا
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// قم بتعيين حشوة الخلية الافتراضية لكائن MarginInfo
table1.DefaultCellPadding = margin;
// إذا قمت بزيادة العداد إلى 17، فسوف تنكسر الطاولة
// لأنه لا يمكن استيعابها أكثر من هذه الصفحة
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// قم بإنشاء صفوف في الجدول ثم خلايا في الصفوف
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// احصل على معلومات ارتفاع الصفحة
float PageHeight = (float)pdf.PageInfo.Height;
// احصل على معلومات الارتفاع الإجمالي للهامش العلوي والسفلي للصفحة،
// هامش أعلى الجدول وارتفاع الجدول.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// عرض ارتفاع الصفحة وارتفاع الجدول والهامش العلوي للجدول وأعلى الصفحة
// ومعلومات الهامش السفلي
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// تحقق مما إذا كنا نخصم مجموع الهامش العلوي للصفحة + الهامش السفلي للصفحة
// + هامش أعلى الجدول وارتفاع الجدول من ارتفاع الصفحة وأقل منه
// أكثر من 10 (يمكن أن يكون متوسط الصف أكبر من 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// إذا كانت القيمة أقل من 10، قم بعرض الرسالة.
	//مما يدل على أنه لا يمكن وضع صف آخر وإذا أضفنا جديدا
	// الصف، سوف ينكسر الجدول. ذلك يعتمد على قيمة ارتفاع الصف.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// احفظ مستند pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تحديد فواصل الجدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل خطوة بخطوة للتحقق مما إذا كان الجدول يتجاوز هوامش الصفحة في مشاريع C# الخاصة بك.

### الأسئلة الشائعة لتحديد فاصل الجدول في ملف PDF

#### س: ما هو الغرض من تحديد فواصل الجدول في وثيقة PDF؟

ج: إن الغرض من تحديد فواصل الجدول في مستند PDF هو التحقق مما إذا كان الجدول يتجاوز هوامش الصفحة. وهذا يضمن عرض محتوى الجدول بشكل صحيح ضمن مساحة الصفحة المتوفرة. من خلال الكشف عن فواصل الجدول، يمكنك التعامل مع تجاوز المحتوى وضبط تخطيط الجدول وفقًا لذلك.

#### س: كيف يمكنني ضبط الهامش العلوي للجدول؟

 ج: في كود مصدر C# المقدم، يمكنك ضبط الهامش العلوي للجدول عن طريق تعديل قيمة`table1.Margin.Top`ملكية. قم بزيادة القيمة أو تقليلها حسب الحاجة لتعيين الهامش العلوي المطلوب للجدول.

#### س: هل يمكنني تخصيص مظهر الجدول، مثل ألوان الخلايا وحجم الخط؟

ج: نعم، يمكنك تخصيص مظهر الجدول وخلاياه باستخدام الخصائص والأساليب المتنوعة التي يوفرها Aspose.PDF لـ .NET. على سبيل المثال، يمكنك تغيير ألوان خلفية الخلية وحجم الخط وعائلة الخطوط ومحاذاة النص والمزيد. راجع الوثائق الرسمية لمزيد من المعلومات حول كيفية تخصيص مظهر الجدول.

#### س: ماذا يحدث إذا تجاوز الجدول هوامش الصفحة؟

ج: إذا تجاوز الجدول هوامش الصفحة، فقد يؤدي ذلك إلى اقتطاع المحتوى أو تداخله، مما يجعل مستند PDF أقل قابلية للقراءة وتنظيمًا. من خلال الكشف عن فواصل الجدول ومعالجة التجاوز، يمكنك التأكد من أن المحتوى يظل معروضًا بشكل صحيح داخل منطقة الصفحة المتاحة.

#### س: هل يمكنني تحديد فواصل الجدول لجداول متعددة في نفس مستند PDF؟

ج: نعم، يمكنك تحديد فواصل الجدول لجداول متعددة في نفس مستند PDF. ما عليك سوى تكرار الخطوات لكل جدول تريد تحليله وضبط تخطيط الجدول حسب الضرورة لمنع تجاوز المحتوى.