---
title: عنصر جدول النمط
linktitle: عنصر جدول النمط
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تنسيق عنصر الجدول باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتخصيص الأنماط والخصائص.
type: docs
weight: 170
url: /ar/net/programming-with-tagged-pdf/style-table-element/
---
في هذا البرنامج التعليمي التفصيلي، سنرشدك عبر كود مصدر C# المقدم خطوة بخطوة لتنسيق عنصر المصفوفة باستخدام Aspose.PDF لـ .NET. اتبع الإرشادات أدناه لفهم كيفية تخصيص أنماط وخصائص عنصر المصفوفة.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من تكوين بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتكوين مشروعك للرجوع إليه.

## الخطوة 2: إنشاء مستند

في هذه الخطوة، سنقوم بإنشاء كائن مستند جديد Aspose.PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

لقد أنشأنا مستندًا جديدًا وقمنا بتعيين عنوان المستند ولغته.

## الخطوة 3: الحصول على عنصر البنية الجذرية

في هذه الخطوة سوف نحصل على عنصر البنية الجذرية لمستندنا.

```csharp
//الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
```

لقد حصلنا على عنصر البنية الجذرية الذي سيكون بمثابة حاوية لعنصر المصفوفة.

## الخطوة 4: إنشاء عنصر هيكل الصفيف

لنقم الآن بإنشاء عنصر هيكل جدول جديد لمستندنا.

```csharp
// إنشاء عنصر هيكل الصفيف
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

لقد أنشأنا عنصر بنية صفيف جديدًا وأضفناه إلى عنصر البنية الجذرية.

## الخطوة 5: تخصيص أنماط وخصائص عناصر المصفوفة

في هذه الخطوة، سنقوم بتخصيص أنماط وخصائص عنصر المصفوفة.

```csharp
// تخصيص أنماط وخصائص عنصر الصفيف
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

استخدمنا خصائص مختلفة لتخصيص عنصر الجدول، مثل لون الخلفية، والحدود، والمحاذاة، ونمط الخلية الافتراضي، والهوامش، وعرض العمود، وما إلى ذلك.

## الخطوة 6: إضافة رؤوس الجدول والنص والتذييل

لنقم الآن بإضافة رؤوس الجدول ونصه وتذييله إلى عنصر الجدول.
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

// قم بإنشاء صف رأس الجدول
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

أضفنا الرؤوس وصفوف النص وصف التذييل إلى الجدول باستخدام العناصر المقابلة.

## الخطوة 7: حفظ وثيقة PDF ذات العلامات

الآن بعد أن أنشأنا مستندنا باستخدام عنصر الجدول المصمم، سنقوم بحفظه كمستند PDF ذو علامات.

```csharp
// احفظ مستند PDF الذي تم وضع علامة عليه
document.Save(dataDir + "StyleTableElement.pdf");
```

لقد حفظنا مستند PDF الذي تم وضع علامة عليه في الدليل المحدد.

## الخطوة 8: التحقق من صحة التوافق مع PDF/UA

بعد ذلك، سوف نقوم بالتحقق من مطابقة PDF/UA لوثيقتنا.

```csharp
// فحص التوافق مع PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

لقد قمنا بتحميل مستند PDF الذي تم وضع علامة عليه وتحققنا من امتثاله لـ PDF/UA من خلال إنشاء تقرير XML.

### نموذج التعليمات البرمجية المصدر لعنصر Style Table باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر هيكل الجذر
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

// حفظ وثيقة PDF ذات العلامات
document.Save(dataDir + "StyleTableElement.pdf");

// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تنسيق عنصر المصفوفة باستخدام Aspose.PDF لـ .NET. لقد قمنا بتخصيص أنماط وخصائص عنصر الجدول، وإضافة الرؤوس، وصفوف النص، والتذييل، وحفظنا مستند PDF الذي تم وضع علامة عليه، والتحقق من توافقه مع PDF/UA.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي حول تنسيق عنصر الصفيف باستخدام Aspose.PDF لـ .NET؟

ج: الهدف من هذا البرنامج التعليمي هو إرشادك خلال عملية تنسيق عنصر المصفوفة في مستند PDF باستخدام Aspose.PDF لـ .NET. فهو يوفر إرشادات خطوة بخطوة وأمثلة التعليمات البرمجية المصدر لـ C# لمساعدتك على تخصيص أنماط وخصائص عنصر الصفيف.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء، تأكد من أنك قمت بإعداد بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتكوين مشروعك للرجوع إليه.

#### س: كيف يمكنني إنشاء مستند PDF جديد وتعيين عنوانه ولغته باستخدام Aspose.PDF لـ .NET؟

 ج: لإنشاء مستند PDF جديد، تحتاج إلى إنشاء ملف`Document` كائن من مكتبة Aspose.PDF. يوضح الكود المصدري لـ C# المقدم في البرنامج التعليمي كيفية إنشاء مستند وتعيين عنوانه وخصائص اللغة الخاصة به.

#### س: ما هي أهمية عنصر البنية الجذرية في مستند PDF؟

ج: يعمل عنصر البنية الجذرية كحاوية لعناصر البنية الأخرى، مما يساعد على تنظيم وتصنيف محتوى مستند PDF. إنه يلعب دورًا حاسمًا في إنشاء البنية المنطقية للوثيقة.

#### س: كيف يمكنني إنشاء عنصر بنية صفيف وتخصيصه باستخدام Aspose.PDF لـ .NET؟

 ج: يمكنك إنشاء عنصر بنية صفيف باستخدام ملف`CreateTableElement()` طريقة. يوفر الكود المصدري للبرنامج التعليمي أمثلة لتخصيص خصائص مختلفة لعنصر الجدول، مثل لون الخلفية والحدود والمحاذاة وعرض العمود والمزيد.

#### س: هل يمكنني تخصيص أنماط وخصائص خلايا الجدول داخل عنصر الصفيف؟

ج: نعم، يغطي البرنامج التعليمي كيفية تخصيص أنماط وخصائص عنصر الجدول بأكمله، بما في ذلك الرؤوس وصفوف النص والتذييل. ومع ذلك، فهو لا يتناول تخصيص خلايا الجدول الفردية على وجه التحديد.

#### س: كيف يمكنني إضافة رؤوس وصفوف نص وتذييل إلى عنصر الجدول؟

ج: يشرح البرنامج التعليمي كيفية إنشاء وإضافة الرؤوس وصفوف النص والتذييل إلى عنصر الجدول باستخدام الطرق المناسبة التي يوفرها Aspose.PDF لـ .NET.

#### س: ما هو توافق PDF/UA، وكيف يمكنني التحقق من صحته بالنسبة لمستند PDF الذي تم وضع علامة عليه؟

 ج: يضمن التوافق مع PDF/UA أن مستند PDF يتوافق مع معايير إمكانية الوصول، مما يجعله في متناول المستخدمين ذوي الإعاقة. يوضح البرنامج التعليمي كيفية التحقق من صحة مطابقة PDF/UA باستخدام ملف`Validate()` الطريقة وإنشاء تقرير امتثال XML.

#### س: كيف يمكنني دمج هذه المفاهيم في تطبيقات .NET الخاصة بي؟

ج: يمكنك استخدام أمثلة التعليمات البرمجية المصدر لـ C# كدليل لتنفيذ تنسيق عناصر المصفوفة في تطبيقات .NET الخاصة بك. قم بتعديل الكود وتكييفه ليتوافق مع متطلباتك ودمجه في مشاريعك.

#### س: هل هناك أي أفضل الممارسات الموصى بها لتنسيق عناصر المصفوفة في مستندات PDF؟

ج: عند تنسيق عناصر المصفوفة (الجداول)، ضع في الاعتبار إمكانية قراءة المحتوى وإمكانية الوصول إليه. استخدم خطوطًا واضحة ومقروءة وألوانًا مناسبة وحافظ على تخطيط متسق. التحقق من صحة توافق PDF/UA لضمان استيفاء معايير إمكانية الوصول.

#### س: ما هي الميزات الأخرى لـ Aspose.PDF لـ .NET التي يمكنني استكشافها لتخصيص مستند PDF؟

ج: يوفر Aspose.PDF for .NET مجموعة من الميزات لتخصيص مستندات PDF، بما في ذلك معالجة النص وإدراج الصور وإدارة حقل النموذج والتوقيعات الرقمية والتعليقات التوضيحية والمزيد. راجع الوثائق والموارد الرسمية لاستكشاف وظائف إضافية.