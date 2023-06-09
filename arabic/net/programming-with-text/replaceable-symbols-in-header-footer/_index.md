---
title: الرموز القابلة للاستبدال في رأس تذييل الصفحة
linktitle: الرموز القابلة للاستبدال في رأس تذييل الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 320
url: /ar/net/programming-with-text/replaceable-symbols-in-header-footer/
---

في هذا البرنامج التعليمي ، سنشرح كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنمر في العملية خطوة بخطوة لإنشاء ملف PDF ، وتعيين الهوامش ، وإضافة رأس وتذييل برموز قابلة للاستبدال ، وحفظ ملف PDF باستخدام كود المصدر C # المقدم.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى الدليل حيث تريد حفظ ملف PDF الذي تم إنشاؤه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بإنشاء مستند وصفحة PDF

بعد ذلك ، نقوم بإنشاء مستند PDF جديد وإضافة صفحة إليه باستخدام ملف`Document` فئة و`Page` فئة من مكتبة Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 3: تعيين الهوامش

 نقوم بتعيين هوامش الصفحة باستخدام الامتداد`MarginInfo` فصل. اضبط قيم الهامش وفقًا لمتطلباتك.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## الخطوة 4: أضف رأسًا برموز قابلة للاستبدال

 نقوم بإنشاء ملف`HeaderFooter` كائن للصفحة وإضافة`TextFragment` مع رموز قابلة للاستبدال لها.

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

// أضف المزيد من TextFragments أو قم بتخصيصها حسب الحاجة
```

## الخطوة 5: إضافة تذييل برموز قابلة للاستبدال

 وبالمثل ، نقوم بإنشاء ملف`HeaderFooter` كائن لتذييل الصفحة وإضافته`TextFragment` كائنات ذات رموز قابلة للاستبدال.

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

أخيرًا ، نحفظ مستند PDF في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر للرموز القابلة للاستبدال في رأس تذييل الصفحة باستخدام Aspose.PDF لـ .NET 
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
//قم بتعيين مثيل marginInfo لخاصية الهامش sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// إنشاء فقرة نصية ستخزن المحتوى لإظهارها كرأس
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
// اضبط كائن HeaderFooter على تذييل فردي وزوجي
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// أضف فقرة نصية تحتوي على رقم الصفحة الحالي لإجمالي عدد الصفحات
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// إنشاء كائن جدول
Table tab2 = new Table();
// أضف الجدول في مجموعة فقرات القسم المطلوب
hfFoot.Paragraphs.Add(tab2);
// اضبط مع عرض أعمدة الجدول
tab2.ColumnWidths = "165 172 165";
// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// قم بتعيين المحاذاة الرأسية للنص كمحاذاة للوسط
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add (نص جديد ("Aspose.Total for Java هو تجميع لكل مكون Java تقدمه Aspose. يتم تجميعه على أساس # $ NL" + "يوميًا للتأكد من احتوائه على أحدث الإصدارات من كل منها من مكونات Java الخاصة بنا. # $ NL "+" باستخدام Aspose.Total لمطوري Java يمكنهم إنشاء مجموعة واسعة من التطبيقات. # $ NL # $ NL # $ NP "+" Aspose.Total for Java هو تجميع لكل مكون Java مقدم من Aspose. يتم تجميعه على أساس يومي # $ NL "+" لضمان احتوائه على أحدث الإصدارات من كل مكون من مكونات Java الخاصة بنا. # $ NL "+" باستخدام Aspose.Total لمطوري Java يمكنهم إنشاء مجموعة واسعة مجموعة من التطبيقات. # $ NL # $ NL # $ NP "+" Aspose.Total for Java هو تجميع لكل مكون Java تقدمه Aspose. يتم تجميعه على أساس يومي # $ NL "+" لضمان احتوائه على أكثر إصدارات محدثة من كل مكون من مكونات Java الخاصة بنا. # $ NL "+" باستخدام Aspose.Total لمطوري Java يمكن أن ينشئوا مجموعة واسعة من التطبيقات. # $ NL # $ NL "))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// أضف الجدول في مجموعة فقرات القسم المطلوب
page.Paragraphs.Add(table);
// تعيين حد الخلية الافتراضي باستخدام كائن BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// قم بتعيين حدود الجدول باستخدام كائن BorderInfo مخصص آخر
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
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

في هذا البرنامج التعليمي ، تعلمت كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل المفصل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك إنشاء ملف PDF وتعيين الهوامش وإضافة رأس وتذييل برموز قابلة للاستبدال وحفظ ملف PDF.