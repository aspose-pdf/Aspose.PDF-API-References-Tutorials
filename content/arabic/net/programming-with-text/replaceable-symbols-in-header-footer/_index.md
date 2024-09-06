---
title: الرموز القابلة للاستبدال في رأس الصفحة وتذييلها
linktitle: الرموز القابلة للاستبدال في رأس الصفحة وتذييلها
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 320
url: /ar/net/programming-with-text/replaceable-symbols-in-header-footer/
---
في هذا البرنامج التعليمي، سنشرح كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتناول العملية خطوة بخطوة لإنشاء ملف PDF، وتعيين الهوامش، وإضافة رأس وتذييل برموز قابلة للاستبدال، وحفظ ملف PDF باستخدام كود المصدر C# المقدم.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت مكتبة Aspose.PDF لـ .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وصفحة PDF

 بعد ذلك، نقوم بإنشاء مستند PDF جديد وإضافة صفحة إليه باستخدام`Document` الصف و`Page` الفئة من مكتبة Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 3: تعيين الهوامش

لقد قمنا بتعيين هوامش الصفحة باستخدام`MarginInfo` الصف. قم بتعديل قيم الهوامش وفقًا لمتطلباتك.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## الخطوة 4: إضافة رأس الصفحة بالرموز القابلة للاستبدال

 نحن ننشئ`HeaderFooter` كائن للصفحة وأضف`TextFragment` مع رموز قابلة للاستبدال.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// تعيين خصائص النص إذا رغبت في ذلك
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// أضف المزيد من TextFragments أو قم بتخصيصها حسب الحاجة
```

## الخطوة 5: إضافة تذييل يحتوي على رموز قابلة للاستبدال

 وبالمثل، نقوم بإنشاء`HeaderFooter` كائن لتذييل الصفحة وإضافته`TextFragment` الأشياء التي تحتوي على رموز قابلة للاستبدال.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// أضف المزيد من TextFragments أو قم بتخصيصها حسب الحاجة

hfFoot.Paragraphs.Add(tab2);
```

## الخطوة 6: احفظ مستند PDF

وأخيرًا، نقوم بحفظ مستند PDF في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### عينة من كود المصدر للرموز القابلة للاستبدال في الرأس والتذييل باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// تعيين مثيل marginInfo إلى خاصية Margin في sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// إنشاء فقرة نصية لتخزين المحتوى لعرضه كرأس
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// إنشاء كائن HeaderFooter للقسم
HeaderFooter hfFoot = new HeaderFooter();
// تعيين كائن HeaderFooter إلى تذييل فردي وزوجي
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// أضف فقرة نصية تحتوي على رقم الصفحة الحالية أو إجمالي عدد الصفحات
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// إنشاء كائن جدول
Table tab2 = new Table();
// أضف الجدول في مجموعة فقرات القسم المطلوب
hfFoot.Paragraphs.Add(tab2);
// مجموعة مع عرض أعمدة الجدول
tab2.ColumnWidths = "165 172 165";
// إنشاء صفوف في الجدول ثم خلايا في الصفوف
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// تعيين محاذاة النص العمودية إلى المنتصف
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("يعد Aspose.Total for Java عبارة عن تجميع لكل مكون Java تقدمه Aspose. يتم تجميعه على أساس #$NL" + "يوميًا للتأكد من أنه يحتوي على أحدث إصدارات كل مكون من مكونات Java الخاصة بنا. #$NL " + "يمكن لمطوري Aspose.Total for Java إنشاء مجموعة واسعة من التطبيقات. #$NL #$NL #$NP" + "يعد Aspose.Total for Java عبارة عن تجميع لكل مكون Java تقدمه Aspose. يتم تجميعه على أساس #$NL" + "يوميًا للتأكد من أنه يحتوي على أحدث إصدارات كل مكون من مكونات Java الخاصة بنا. #$NL " + "يمكن لمطوري Aspose.Total for Java إنشاء مجموعة واسعة من التطبيقات. #$NL #$NL #$NP" + "يعد Aspose.Total for Java عبارة عن تجميع لكل مكون Java تقدمه Aspose. يتم تجميعه على أساس #$NL" + "يوميًا للتأكد من أنه يحتوي على أحدث إصدارات كل مكون من مكونات Java الخاصة بنا. #$NL " + "يمكن لمطوري Aspose.Total for Java إنشاء مجموعة واسعة من التطبيقات. #$NL #$NL #$NP" + "يعد Aspose.Total for Java عبارة عن تجميع لكل مكون Java تقدمه Aspose. يتم تجميعه على أساس #$NL" + "يوميًا للتأكد من أنه يحتوي على أحدث إصدارات كل مكون من مكونات Java الخاصة بنا. يحتوي على أحدث الإصدارات لكل مكون من مكونات Java الخاصة بنا. #$NL " + "يمكن لمطوري Java باستخدام Aspose.Total إنشاء مجموعة واسعة من التطبيقات. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// أضف الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(table);
// تعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// تعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// إنشاء صفوف في الجدول ثم خلايا في الصفوف
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك إنشاء ملف PDF وتعيين الهوامش وإضافة رأس وتذييل برموز قابلة للاستبدال وحفظ ملف PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "الرموز القابلة للاستبدال في الرأس والتذييل"؟

أ: يهدف البرنامج التعليمي "الرموز القابلة للاستبدال في رأس وتذييل الصفحة" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لإضافة رموز قابلة للاستبدال إلى رأس وتذييل مستند PDF. تتيح لك الرموز القابلة للاستبدال استبدال العناصر النائبة المحددة ديناميكيًا بقيم فعلية عند إنشاء ملف PDF.

#### س: ما هي الرموز القابلة للاستبدال في سياق رأس وتذييل PDF؟

ج: الرموز القابلة للاستبدال هي عناصر نائبة يمكنك إدراجها في رأس وتذييل مستند PDF. تعمل هذه الرموز كعناصر نائبة ديناميكية للقيم التي يمكن ملؤها وقت التشغيل، مثل أرقام الصفحات والتاريخ والمعلومات المخصصة.

#### س: لماذا أرغب في استخدام رموز قابلة للاستبدال في رأس وتذييل ملف PDF؟

أ: تعتبر الرموز القابلة للاستبدال في الرأس والتذييل مفيدة عندما تريد تضمين معلومات ديناميكية في مستندات PDF الخاصة بك، مثل أرقام الصفحات أو التواريخ أو غيرها من البيانات المتغيرة التي قد تتغير عند إنشاء المستند.

#### س: كيف يمكنني ضبط الهوامش لصفحة PDF؟

 أ: يمكنك ضبط الهوامش لصفحة PDF باستخدام`MarginInfo` الصف وتعيينه إلى`Margin` ممتلكات`PageInfo` من الصفحة. قم بتعديل قيم الهوامش حسب الحاجة.

#### س: كيف يمكنني إضافة رموز قابلة للاستبدال إلى الرأس والتذييل؟

 أ: يمكنك إضافة رموز قابلة للاستبدال عن طريق إنشاء`HeaderFooter` كائن لرأس وتذييل الصفحة. بعد ذلك، يمكنك إضافة`TextFragment`الأشياء التي تحتوي على النص المطلوب، بما في ذلك الرموز القابلة للاستبدال،`Paragraphs` مجموعة من`HeaderFooter` هدف.

#### س: هل يمكنني تخصيص مظهر الرموز القابلة للاستبدال؟

 ج: نعم، يمكنك تخصيص مظهر الرموز القابلة للاستبدال عن طريق تعديل خصائص`TextFragment` الكائنات التي تحتوي على الرموز. يمكنك تعيين خصائص مثل الخط وحجم الخط واللون والمحاذاة والتباعد بين السطور.

#### س: ما نوع الرموز القابلة للاستبدال التي يمكنني استخدامها؟

أ: يمكنك استخدام مجموعة متنوعة من الرموز القابلة للاستبدال، مثل:

- `$p`:رقم الصفحة الحالية.
- `$P`:إجمالي عدد الصفحات.
- `$d`:التاريخ الحالي.
- `$t`:الوقت الحالي.
- العناصر النائبة المخصصة التي تقوم بتحديدها.

#### س: هل يمكنني تضمين نص وتنسيق آخر حول الرموز القابلة للاستبدال؟

 ج: نعم، يمكنك تضمين نص آخر وتنسيق حول الرموز القابلة للاستبدال داخل`TextFragment` يتيح لك هذا إنشاء رؤوس وتذييلات أكثر تعقيدًا تتضمن محتوى ديناميكيًا وثابتًا.

#### س: كيف يمكنني حفظ مستند PDF الناتج؟

 أ: لحفظ مستند PDF الناتج، يمكنك استخدام`Save` طريقة`Document`قم بتوفير مسار ملف الإخراج المطلوب والاسم كحجة.

#### س: هل يلزم الحصول على ترخيص Aspose صالح لهذا البرنامج التعليمي؟

ج: نعم، يلزم الحصول على ترخيص Aspose صالح لتنفيذ التعليمات البرمجية بنجاح في هذا البرنامج التعليمي. يمكنك الحصول على ترخيص كامل أو ترخيص مؤقت لمدة 30 يومًا من موقع Aspose على الويب.