---
title: عنصر جدول الأنماط
linktitle: عنصر جدول الأنماط
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تنسيق عناصر الجدول باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتخصيص الأنماط والخصائص.
type: docs
weight: 170
url: /ar/net/programming-with-tagged-pdf/style-table-element/
---
في هذا البرنامج التعليمي المفصل، سنشرح لك خطوة بخطوة التعليمات البرمجية المصدرية المقدمة بلغة C# لتنسيق عنصر المصفوفة باستخدام Aspose.PDF لـ .NET. اتبع الإرشادات أدناه لفهم كيفية تخصيص أنماط وخصائص عنصر المصفوفة.

## الخطوة 1: إعداد البيئة

قبل أن تبدأ، تأكد من تكوين بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن هذا تثبيت مكتبة Aspose.PDF وتكوين مشروعك للإشارة إليها.

## الخطوة 2: إنشاء مستند

في هذه الخطوة، سنقوم بإنشاء كائن مستند جديد Aspose.PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء المستندات
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

لقد قمنا بإنشاء مستند جديد وقمنا بتعيين عنوان المستند واللغة.

## الخطوة 3: الحصول على عنصر البنية الجذرية

في هذه الخطوة سوف نحصل على عنصر البنية الجذرية لمستندنا.

```csharp
// الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
```

لقد حصلنا على عنصر البنية الجذرية الذي سيعمل كحاوية لعناصر المصفوفة.

## الخطوة 4: إنشاء عنصر هيكل المصفوفة

الآن دعونا نقوم بإنشاء عنصر هيكل جدول جديد للمستند الخاص بنا.

```csharp
// إنشاء عنصر هيكل المصفوفة
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

لقد قمنا بإنشاء عنصر هيكل مصفوفة جديد وأضفناه إلى عنصر الهيكل الجذر.

## الخطوة 5: تخصيص أنماط وخصائص عناصر المصفوفة

في هذه الخطوة، سنقوم بتخصيص أنماط وخصائص عناصر المصفوفة.

```csharp
// تخصيص أنماط وخصائص عناصر المصفوفة
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// تخصيص نمط الخطوط المتكررة
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

لقد استخدمنا خصائص مختلفة لتخصيص عناصر الجدول، مثل لون الخلفية، والحدود، والمحاذاة، ونمط الخلية الافتراضي، والهوامش، وعرض العمود، وما إلى ذلك.

## الخطوة 6: إضافة رؤوس الجدول والنص والتذييل

الآن دعونا نضيف رؤوس الجدول والجسم والتذييل إلى عنصر الجدول.
```csharp
// إضافة رؤوس الجدول
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// عدد الصفوف والأعمدة في الجدول
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// إنشاء صف رأس الجدول
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//أضف صفوف نص الجدول
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// أضف خط الأساس للجدول
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

لقد أضفنا رؤوس الصفحات، وصفوف النص، وصفوف التذييل إلى الجدول باستخدام العناصر المقابلة.

## الخطوة 7: حفظ مستند PDF المُوسوم

الآن بعد أن قمنا بإنشاء مستندنا باستخدام عنصر الجدول المصمم، سنقوم بحفظه كمستند PDF مميز.

```csharp
// احفظ مستند PDF المُوسوم
document.Save(dataDir + "StyleTableElement.pdf");
```

لقد قمنا بحفظ مستند PDF المُوسوم في الدليل المحدد.

## الخطوة 8: التحقق من توافق PDF/UA

بعد ذلك، سوف نقوم بالتحقق من تطابق PDF/UA الخاص بمستندنا.

```csharp
// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

لقد قمنا بتحميل مستند PDF الذي تم وضع العلامة عليه وقمنا بالتحقق من توافقه مع PDF/UA من خلال إنشاء تقرير XML.

### عينة من كود المصدر لعنصر جدول الأنماط باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;

// إنشاء عنصر هيكل الجدول
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// حفظ مستند PDF المُوسوم
document.Save(dataDir + "StyleTableElement.pdf");

// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تنسيق عنصر المصفوفة باستخدام Aspose.PDF لـ .NET. قمنا بتخصيص أنماط وخصائص عنصر الجدول، وإضافة رؤوس وصفوف نص وتذييل، وحفظ مستند PDF المُوسوم، والتحقق من توافقه مع PDF/UA.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي حول تنسيق عنصر المصفوفة باستخدام Aspose.PDF لـ .NET؟

ج: الهدف من هذا البرنامج التعليمي هو إرشادك خلال عملية تنسيق عنصر المصفوفة في مستند PDF باستخدام Aspose.PDF لـ .NET. وهو يوفر تعليمات خطوة بخطوة وأمثلة لأكواد المصدر C# لمساعدتك في تخصيص أنماط وخصائص عنصر المصفوفة.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء، تأكد من إعداد بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن هذا تثبيت مكتبة Aspose.PDF وتكوين مشروعك للإشارة إليها.

#### س: كيف يمكنني إنشاء مستند PDF جديد وتعيين عنوانه ولغته باستخدام Aspose.PDF لـ .NET؟

 أ: لإنشاء مستند PDF جديد، تحتاج إلى إنشاء`Document` كائن من مكتبة Aspose.PDF. يوضح كود المصدر C# المقدم في البرنامج التعليمي كيفية إنشاء مستند وتعيين عنوانه وخصائص اللغة الخاصة به.

#### س: ما أهمية عنصر البنية الجذرية في مستند PDF؟

ج: يعمل عنصر البنية الجذرية كحاوية لعناصر البنية الأخرى، مما يساعد في تنظيم وتصنيف محتوى مستند PDF. ويلعب دورًا حاسمًا في تحديد البنية المنطقية للمستند.

#### س: كيف يمكنني إنشاء عنصر بنية المصفوفة وتخصيصه باستخدام Aspose.PDF لـ .NET؟

 أ: يمكنك إنشاء عنصر هيكل المصفوفة باستخدام`CreateTableElement()` يوفر كود المصدر للبرنامج التعليمي أمثلة لتخصيص خصائص مختلفة لعناصر الجدول، مثل لون الخلفية والحدود والمحاذاة وعرض العمود والمزيد.

#### س: هل يمكنني تخصيص أنماط وخصائص خلايا الجدول داخل عنصر المصفوفة؟

ج: نعم، يغطي البرنامج التعليمي كيفية تخصيص أنماط وخصائص عناصر الجدول بالكامل، بما في ذلك الرؤوس وصفوف النص والتذييل. ومع ذلك، فهو لا يتناول على وجه التحديد تخصيص خلايا الجدول الفردية.

#### س: كيف يمكنني إضافة رؤوس وصفوف النص وتذييل إلى عنصر الجدول؟

أ: يشرح البرنامج التعليمي كيفية إنشاء وإضافة رؤوس الصفحات وصفوف النص وتذييل الصفحة إلى عناصر الجدول باستخدام الطرق المناسبة التي يوفرها Aspose.PDF لـ .NET.

#### س: ما هو التوافق مع PDF/UA، وكيف يمكنني التحقق من صحته لمستند PDF الذي قمت بوضع علامة عليه؟

 أ: يضمن توافق PDF/UA أن مستند PDF يتوافق مع معايير إمكانية الوصول، مما يجعله أكثر سهولة في الوصول للمستخدمين ذوي الإعاقة. يوضح البرنامج التعليمي كيفية التحقق من صحة توافق PDF/UA باستخدام`Validate()` الطريقة وإنشاء تقرير امتثال XML.

#### س: كيف يمكنني دمج هذه المفاهيم في تطبيقات .NET الخاصة بي؟

ج: يمكنك استخدام أمثلة التعليمات البرمجية المصدرية بلغة C# المقدمة كدليل لتنفيذ تنسيق عناصر المصفوفة في تطبيقات .NET الخاصة بك. قم بتعديل التعليمات البرمجية وتكييفها لتتناسب مع متطلباتك ودمجها في مشاريعك.

#### س: هل هناك أي ممارسات أفضل موصى بها لتنسيق عناصر المصفوفة في مستندات PDF؟

أ: عند تنسيق عناصر المصفوفة (الجداول)، ضع في اعتبارك قابلية قراءة المحتوى وإمكانية الوصول إليه. استخدم خطوطًا واضحة وقابلة للقراءة وألوانًا مناسبة وحافظ على تخطيط متناسق. تحقق من توافق PDF/UA لضمان تلبية معايير إمكانية الوصول.

#### س: ما هي الميزات الأخرى لـ Aspose.PDF لـ .NET التي يمكنني استكشافها لتخصيص مستند PDF؟

ج: يوفر Aspose.PDF for .NET مجموعة من الميزات لتخصيص مستندات PDF، بما في ذلك معالجة النصوص، وإدراج الصور، وإدارة حقول النماذج، والتوقيعات الرقمية، والتعليقات التوضيحية، والمزيد. راجع الوثائق والموارد الرسمية لاستكشاف الوظائف الإضافية.