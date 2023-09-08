---
title: صف نمط الجدول
linktitle: صف نمط الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تخصيص صفوف الجدول باستخدام دليل Aspose.PDF لـ .NET خطوة بخطوة لتصميم الصفوف وتنسيقها.
type: docs
weight: 180
url: /ar/net/programming-with-tagged-pdf/style-table-row/
---
في هذا البرنامج التعليمي المفصل، سنرشدك عبر التعليمات البرمجية المصدر لـ C# المتوفرة خطوة بخطوة لتنسيق صف الجدول باستخدام Aspose.PDF لـ .NET. اتبع الإرشادات أدناه لفهم كيفية تخصيص أنماط وخصائص صفوف الجدول.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## الخطوة 5: تخصيص أنماط وخصائص صفوف الجدول

في هذه الخطوة، سنقوم بتخصيص أنماط وخصائص صفوف الجدول.

```csharp
// تخصيص أنماط وخصائص صفوف الجدول
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// تخصيص صفوف نص الجدول
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// إنشاء سطر تذييل الجدول
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

لقد قمنا بتخصيص جوانب مختلفة من صف الجدول، مثل لون الخلفية والحدود وارتفاع الصف وترقيم الصفحات ونمط الخلية الافتراضي والمزيد.

## الخطوة 6: حفظ وثيقة PDF ذات العلامات

الآن بعد أن أنشأنا مستندنا بصف الجدول المصمم، سنقوم بحفظه كمستند PDF ذو علامات.
```csharp
// احفظ مستند PDF الذي تم وضع علامة عليه
document.Save(dataDir + "StyleTableRow.pdf");
```

لقد حفظنا مستند PDF الذي تم وضع علامة عليه في الدليل المحدد.

## الخطوة 7: التحقق من صحة التوافق مع PDF/UA

بعد ذلك، سوف نقوم بالتحقق من مطابقة PDF/UA لوثيقتنا.

```csharp
// فحص التوافق مع PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

لقد قمنا بتحميل مستند PDF الذي تم وضع علامة عليه وتحققنا من امتثاله لـ PDF/UA من خلال إنشاء تقرير XML.


### نموذج التعليمات البرمجية المصدر لـ Style Table Row باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر هيكل الجذر
StructureElement rootElement = taggedContent.RootElement;

// إنشاء عنصر هيكل الجدول
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تنسيق صف الجدول باستخدام Aspose.PDF لـ .NET. لقد قمنا بتخصيص أنماط وخصائص صفوف الجدول، وأضفنا الرؤوس وصفوف النص والتذييل، وحفظنا مستند PDF الذي تم وضع علامة عليه، وتحققنا من توافقه مع PDF/UA.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي حول تنسيق صفوف الجدول باستخدام Aspose.PDF لـ .NET؟

ج: الغرض من هذا البرنامج التعليمي هو إرشادك خلال عملية تنسيق صفوف الجدول في مستند PDF باستخدام Aspose.PDF لـ .NET. فهو يوفر إرشادات خطوة بخطوة وأمثلة التعليمات البرمجية المصدر لـ C# لمساعدتك في تخصيص أنماط وخصائص صفوف الجدول.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء، تأكد من أنك قمت بإعداد بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتكوين مشروعك للرجوع إليه.

#### س: كيف يمكنني إنشاء مستند PDF جديد وتعيين عنوانه ولغته باستخدام Aspose.PDF لـ .NET؟

 ج: لإنشاء مستند PDF جديد، تحتاج إلى إنشاء ملف`Document` كائن من مكتبة Aspose.PDF. يوضح الكود المصدري لـ C# المقدم في البرنامج التعليمي كيفية إنشاء مستند وتعيين عنوانه وخصائص اللغة الخاصة به.

#### س: ما هي أهمية عنصر البنية الجذرية في مستند PDF؟

ج: يعمل عنصر البنية الجذرية كحاوية لعناصر البنية الأخرى، مما يساعد على تنظيم وتصنيف محتوى مستند PDF. إنه يلعب دورًا حاسمًا في إنشاء البنية المنطقية للوثيقة.

#### س: كيف يمكنني إنشاء عنصر بنية جدول وتخصيصه لتنسيق صفوف الجدول باستخدام Aspose.PDF لـ .NET؟

ج: يشرح البرنامج التعليمي كيفية إنشاء عنصر هيكل الجدول وتخصيص خصائصه لتنسيق صفوف الجدول. ويغطي جوانب مثل لون الخلفية والحدود وارتفاع الصف وترقيم الصفحات ونمط الخلية الافتراضي والمزيد.

#### س: هل يمكنني تخصيص أنماط وخصائص الخلايا الفردية داخل صف الجدول؟

ج: نعم، يمكنك تخصيص أنماط وخصائص الخلايا الفردية داخل صف الجدول. يوضح البرنامج التعليمي كيفية تعيين خصائص مثل لون الخلفية والحدود ولون النص والحشو والمزيد لخلايا الجدول داخل صف الجدول المنسق.

#### س: كيف يمكنني إضافة رؤوس وصفوف نص وتذييل إلى صف الجدول المنسق؟

ج: يوفر البرنامج التعليمي أمثلة حول إنشاء وإضافة الرؤوس وصفوف النص والتذييل إلى عنصر بنية الجدول. يمكن تخصيص هذه العناصر بشكل أكبر باستخدام الخصائص الموضحة في البرنامج التعليمي.

#### س: ما هو توافق PDF/UA، وكيف يمكنني التحقق من صحته بالنسبة لمستند PDF الذي تم وضع علامة عليه؟

 ج: يضمن التوافق مع PDF/UA أن مستند PDF يتوافق مع معايير إمكانية الوصول، مما يجعله في متناول المستخدمين ذوي الإعاقة. يوضح البرنامج التعليمي كيفية التحقق من صحة مطابقة PDF/UA باستخدام ملف`Validate()` الطريقة وإنشاء تقرير امتثال XML.

#### س: كيف يمكنني دمج هذه المفاهيم في تطبيقات .NET الخاصة بي؟

ج: يمكنك استخدام أمثلة التعليمات البرمجية المصدر C# المتوفرة كدليل لتنفيذ تنسيق صف الجدول في تطبيقات .NET الخاصة بك. قم بتعديل الكود وتكييفه ليتوافق مع متطلباتك ودمجه في مشاريعك.

#### س: هل هناك أي أفضل الممارسات الموصى بها لتنسيق صفوف الجدول في مستندات PDF؟

ج: عند تنسيق صفوف الجدول، ضع في الاعتبار إمكانية قراءة المحتوى وإمكانية الوصول إليه. تأكد من أن الألوان تتمتع بتباين كافٍ، واستخدم خطوطًا واضحة ومقروءة، وحافظ على تخطيط متسق. التحقق من صحة توافق PDF/UA لضمان استيفاء معايير إمكانية الوصول.

#### س: ما هي الميزات الأخرى لـ Aspose.PDF لـ .NET التي يمكنني استكشافها لتخصيص مستند PDF؟

ج: يوفر Aspose.PDF for .NET نطاقًا واسعًا من الميزات لتخصيص مستندات PDF، بما في ذلك معالجة النص وإدراج الصور وإدارة حقل النموذج والتوقيعات الرقمية والتعليقات التوضيحية والمزيد. راجع الوثائق والموارد الرسمية لاستكشاف وظائف إضافية.