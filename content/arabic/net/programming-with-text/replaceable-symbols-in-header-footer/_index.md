---
title: الرموز القابلة للاستبدال في تذييل الرأس
linktitle: الرموز القابلة للاستبدال في تذييل الرأس
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 320
url: /ar/net/programming-with-text/replaceable-symbols-in-header-footer/
---
سنشرح في هذا البرنامج التعليمي كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتابع عملية إنشاء ملف PDF خطوة بخطوة، وتعيين الهوامش، وإضافة رأس وتذييل برموز قابلة للاستبدال، وحفظ ملف PDF باستخدام كود مصدر C# المقدم.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir`متغير مع المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وصفحة PDF

 بعد ذلك، نقوم بإنشاء مستند PDF جديد ونضيف إليه صفحة باستخدام الملف`Document` الطبقة و`Page` فئة من مكتبة Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 3: تعيين الهوامش

 قمنا بتعيين هوامش الصفحة باستخدام`MarginInfo`فصل. اضبط قيم الهامش وفقًا لمتطلباتك.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## الخطوة 4: إضافة رأس برموز قابلة للاستبدال

 نقوم بإنشاء أ`HeaderFooter` كائن للصفحة وإضافة أ`TextFragment` مع رموز قابلة للاستبدال لها.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// قم بتعيين خصائص النص إذا رغبت في ذلك
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// أضف المزيد من أجزاء النص أو قم بتخصيصها حسب الحاجة
```

## الخطوة 5: إضافة تذييل برموز قابلة للاستبدال

 وبالمثل، نقوم بإنشاء`HeaderFooter` كائن لتذييل الصفحة وإضافة`TextFragment` كائنات ذات رموز قابلة للاستبدال لها.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// أضف المزيد من أجزاء النص أو قم بتخصيصها حسب الحاجة

hfFoot.Paragraphs.Add(tab2);
```

## الخطوة 6: احفظ مستند PDF

وأخيرًا، نقوم بحفظ مستند PDF في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر للرموز القابلة للاستبدال في تذييل الرأس باستخدام Aspose.PDF لـ .NET 
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
// قم بتعيين مثيلMarginInfo لخاصية Margin لـ sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// قم بإنشاء مثيل لفقرة نصية تقوم بتخزين المحتوى لإظهاره كرأس
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
// قم بإنشاء كائن HeaderFooter للمقطع
HeaderFooter hfFoot = new HeaderFooter();
// قم بتعيين كائن HeaderFooter على التذييل الفردي والزوجي
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// إضافة فقرة نصية تحتوي على رقم الصفحة الحالية من إجمالي عدد الصفحات
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// إنشاء مثيل لكائن الجدول
Table tab2 = new Table();
// إضافة الجدول في مجموعة فقرات القسم المطلوب
hfFoot.Paragraphs.Add(tab2);
// تعيين مع عرض أعمدة الجدول
tab2.ColumnWidths = "165 172 165";
// قم بإنشاء صفوف في الجدول ثم خلايا في الصفوف
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// قم بتعيين المحاذاة العمودية للنص كمحاذاة للوسط
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java عبارة عن تجميع لكل مكونات Java التي تقدمها Aspose. ويتم تجميعها على أساس #$NL" + "يوميًا للتأكد من أنها تحتوي على أحدث الإصدارات من كل منها من مكونات Java الخاصة بنا. #$NL " + "استخدام Aspose.Total لمطوري Java يمكن أن ينشئ نطاقًا واسعًا من التطبيقات. #$NL #$NL #$NP" + "Aspose.Total لـ Java عبارة عن تجميع لكل مكون Java مقدمة من Aspose. ويتم تجميعها على أساس #$NL" + "يوميًا للتأكد من أنها تحتوي على أحدث الإصدارات لكل مكون من مكونات Java لدينا. #$NL " + "باستخدام Aspose.Total لمطوري Java يمكن إنشاء مجموعة واسعة من مجموعة من التطبيقات. #$NL #$NL #$NP" + "Aspose.Total for Java عبارة عن تجميع لكل مكونات Java التي تقدمها Aspose. ويتم تجميعها على أساس #$NL" + "يوميًا للتأكد من أنها تحتوي على أكبر قدر من التطبيقات إصدارات محدثة لكل مكون من مكونات Java. #$NL " + "باستخدام Aspose.Total لمطوري Java يمكن إنشاء مجموعة واسعة من التطبيقات. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// إضافة الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(table);
// قم بتعيين حدود الخلية الافتراضية باستخدام كائن BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// قم بتعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// قم بإنشاء صفوف في الجدول ثم خلايا في الصفوف
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

في هذا البرنامج التعليمي، تعلمت كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك إنشاء ملف PDF وتعيين الهوامش وإضافة رأس وتذييل برموز قابلة للاستبدال وحفظ ملف PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "الرموز القابلة للاستبدال في تذييل الصفحة"؟

ج: يهدف البرنامج التعليمي "الرموز القابلة للاستبدال في تذييل الرأس" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لإضافة رموز قابلة للاستبدال إلى رأس وتذييل مستند PDF. تتيح لك الرموز القابلة للاستبدال استبدال عناصر نائبة معينة ديناميكيًا بقيم فعلية عند إنشاء ملف PDF.

#### س: ما هي الرموز القابلة للاستبدال في سياق رأس وتذييل ملف PDF؟

ج: الرموز القابلة للاستبدال هي عناصر نائبة يمكنك إدراجها في رأس وتذييل مستند PDF. تعمل هذه الرموز كعناصر نائبة ديناميكية للقيم التي يمكن ملؤها في وقت التشغيل، مثل أرقام الصفحات والتواريخ والمعلومات المخصصة.

#### س: لماذا أرغب في استخدام رموز قابلة للاستبدال في رأس وتذييل ملف PDF؟

ج: تكون الرموز القابلة للاستبدال في الرأس والتذييل مفيدة عندما تريد تضمين معلومات ديناميكية في مستندات PDF الخاصة بك، مثل أرقام الصفحات أو التواريخ أو البيانات المتغيرة الأخرى التي قد تتغير عند إنشاء المستند.

#### س: كيف يمكنني ضبط هوامش صفحة PDF؟

 ج: يمكنك ضبط هوامش صفحة PDF باستخدام`MarginInfo` الصف وإسناده إلى`Margin` ملكية`PageInfo` من الصفحة. اضبط قيم الهامش حسب الحاجة.

#### س: كيف يمكنني إضافة رموز قابلة للاستبدال إلى الرأس والتذييل؟

 ج: يمكنك إضافة رموز قابلة للاستبدال عن طريق إنشاء ملف`HeaderFooter` كائن لرأس وتذييل الصفحة. وبعد ذلك، يمكنك إضافة`TextFragment`الكائنات التي تحتوي على النص المطلوب، بما في ذلك الرموز القابلة للاستبدال، إلى`Paragraphs` جمع من`HeaderFooter` هدف.

#### س: هل يمكنني تخصيص مظهر الرموز القابلة للاستبدال؟

 ج: نعم، يمكنك تخصيص مظهر الرموز القابلة للاستبدال عن طريق تعديل خصائص`TextFragment` الكائنات التي تحتوي على الرموز. يمكنك تعيين خصائص مثل الخط وحجم الخط واللون والمحاذاة وتباعد الأسطر.

#### س: ما نوع الرموز القابلة للاستبدال التي يمكنني استخدامها؟

ج: يمكنك استخدام مجموعة متنوعة من الرموز القابلة للاستبدال، مثل:

- `$p`: رقم الصفحة الحالية.
- `$P`: إجمالي عدد الصفحات.
- `$d`: التاريخ الحالي.
- `$t`: الوقت الحالي.
- العناصر النائبة المخصصة التي تحددها.

#### س: هل يمكنني تضمين نص وتنسيق آخر حول الرموز القابلة للاستبدال؟

 ج: نعم، يمكنك تضمين نص وتنسيقات أخرى حول الرموز القابلة للاستبدال داخل ملف`TextFragment` أشياء. يتيح لك ذلك إنشاء رؤوس وتذييلات أكثر تعقيدًا تتضمن محتوى ديناميكيًا وثابتًا.

#### س: كيف يمكنني حفظ مستند PDF الذي تم إنشاؤه؟

 ج: لحفظ مستند PDF الذي تم إنشاؤه، يمكنك استخدام الملف`Save` طريقة`Document`فصل. قم بتوفير مسار ملف الإخراج المطلوب واسمه كوسيطة.

#### س: هل يلزم وجود ترخيص Aspose صالح لهذا البرنامج التعليمي؟

ج: نعم، مطلوب ترخيص Aspose صالح لتنفيذ التعليمات البرمجية بنجاح في هذا البرنامج التعليمي. يمكنك الحصول على ترخيص كامل أو ترخيص مؤقت لمدة 30 يومًا من موقع Aspose.