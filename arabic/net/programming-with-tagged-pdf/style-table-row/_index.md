---
title: نمط جدول الصف
linktitle: نمط جدول الصف
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تخصيص صفوف الجدول باستخدام Aspose.PDF for .NET دليل خطوة بخطوة لتصميم الصفوف وتنسيقها.
type: docs
weight: 180
url: /ar/net/programming-with-tagged-pdf/style-table-row/
---
في هذا البرنامج التعليمي المفصل ، سنرشدك خلال التعليمات البرمجية المصدر C # المقدمة خطوة بخطوة لتنسيق صف الجدول باستخدام Aspose.PDF for .NET. اتبع الإرشادات أدناه لفهم كيفية تخصيص أنماط صفوف الجدول وخصائصه.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من تكوين بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتهيئة مشروعك للرجوع إليه.

## الخطوة 2: إنشاء وثيقة

في هذه الخطوة ، سننشئ كائن مستند جديد Aspose.PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

لقد أنشأنا مستندًا جديدًا وحددنا عنوان المستند ولغته.

## الخطوة 3: الحصول على عنصر بنية الجذر

في هذه الخطوة ، سنحصل على عنصر بنية الجذر لوثيقتنا.

```csharp
//الحصول على عنصر بنية الجذر
StructureElement rootElement = taggedContent.RootElement;
```

حصلنا على عنصر بنية الجذر الذي سيكون بمثابة حاوية لعنصر المصفوفة.

## الخطوة 4: إنشاء عنصر بنية المصفوفة

لنقم الآن بإنشاء عنصر هيكل جدول جديد لوثيقتنا.

```csharp
// قم بإنشاء عنصر بنية المصفوفة
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

لقد أنشأنا عنصر هيكل مصفوفة جديد وأضفناه إلى عنصر بنية الجذر.

## الخطوة 5: تخصيص أنماط صفوف الجدول وخصائصه

في هذه الخطوة ، سنخصص أنماط وخصائص صف الجدول.

```csharp
// تخصيص أنماط صف الجدول وخصائصه
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

// تخصيص صفوف جسم الجدول
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

// قم بإنشاء سطر تذييل الجدول
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

لقد قمنا بتخصيص جوانب مختلفة لصف الجدول ، مثل لون الخلفية ، والحدود ، وارتفاع الصف ، وترقيم الصفحات ، ونمط الخلية الافتراضي ، والمزيد.

## الخطوة 6: حفظ مستند PDF الذي تم وضع علامة عليه

الآن بعد أن أنشأنا المستند الخاص بنا مع صف الجدول المصمم ، سنقوم بحفظه كمستند PDF مميز.
```csharp
// احفظ مستند PDF بعلامات
document.Save(dataDir + "StyleTableRow.pdf");
```

لقد حفظنا مستند PDF المميز بعلامات في الدليل المحدد.

## الخطوة 7: التحقق من توافق PDF / UA

بعد ذلك ، سوف نتحقق من توافق PDF / UA لوثيقتنا.

```csharp
// فحص التوافق مع PDF / UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

قمنا بتحميل مستند PDF الذي تم وضع علامة عليه وتحققنا من توافقه مع PDF / UA من خلال إنشاء تقرير XML.


### نموذج التعليمات البرمجية المصدر لـ Style Table Row باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء وثيقة
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر بنية الجذر
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

// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "StyleTableRow.pdf");

// التحقق من توافق PDF / UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تنسيق صف الجدول باستخدام Aspose.PDF for .NET. قمنا بتخصيص أنماط وخصائص صف الجدول ، وأضفنا الرؤوس ، وصفوف النص ، والتذييل ، وحفظنا وثيقة PDF المميزة ، وتحققنا من توافقها مع PDF / UA.

### التعليمات

#### س: ما هو الغرض من هذا البرنامج التعليمي حول تنسيق صفوف الجدول باستخدام Aspose.PDF for .NET؟

ج: الغرض من هذا البرنامج التعليمي هو إرشادك خلال عملية تنسيق صفوف الجدول في مستند PDF باستخدام Aspose.PDF for .NET. يوفر إرشادات خطوة بخطوة وأمثلة على التعليمات البرمجية المصدر لـ C # لمساعدتك في تخصيص أنماط صفوف الجدول وخصائصه.

#### س: ما هي المتطلبات الأساسية لاتباع هذا البرنامج التعليمي؟

ج: قبل أن تبدأ ، تأكد من قيامك بإعداد بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتكوين مشروعك للرجوع إليه.

#### س: كيف يمكنني إنشاء مستند PDF جديد وتعيين عنوانه ولغته باستخدام Aspose.PDF for .NET؟

 ج: لإنشاء مستند PDF جديد ، تحتاج إلى إنشاء ملف`Document` كائن من مكتبة Aspose.PDF. يوضح الكود المصدري C # المقدم من البرنامج التعليمي كيفية إنشاء مستند وتعيين عنوانه وخصائص اللغة.

#### س: ما هي أهمية عنصر البنية الجذرية في مستند PDF؟

ج: يعمل عنصر بنية الجذر كحاوية لعناصر بنية أخرى ، مما يساعد على تنظيم محتوى مستند PDF وتصنيفه. إنها تلعب دورًا حاسمًا في إنشاء البنية المنطقية للوثيقة.

#### س: كيف يمكنني إنشاء عنصر هيكل جدول وتخصيصه لتنسيق صفوف الجدول باستخدام Aspose.PDF for .NET؟

ج: يشرح البرنامج التعليمي كيفية إنشاء عنصر هيكل جدول وتخصيص خصائصه لتنسيق صفوف الجدول. يغطي جوانب مثل لون الخلفية والحدود وارتفاع الصف وترقيم الصفحات ونمط الخلية الافتراضي والمزيد.

#### س: هل يمكنني تخصيص أنماط وخصائص الخلايا الفردية داخل صف جدول؟

ج: نعم ، يمكنك تخصيص أنماط وخصائص الخلايا الفردية داخل صف الجدول. يوضح البرنامج التعليمي كيفية تعيين الخصائص مثل لون الخلفية والحدود ولون النص والحشو والمزيد لخلايا الجدول داخل صف الجدول المنسق.

#### س: كيف يمكنني إضافة رؤوس وصفوف نصية وتذييل إلى صف الجدول المنسق؟

ج: يقدم البرنامج التعليمي أمثلة لإنشاء الرؤوس وصفوف النص والتذييل وإضافتها إلى عنصر بنية الجدول. يمكن تخصيص هذه العناصر بشكل أكبر باستخدام الخصائص الموضحة في البرنامج التعليمي.

#### س: ما هو التوافق مع PDF / UA ، وكيف يمكنني التحقق من صحته لمستند PDF المميز بعلامات؟

 ج: يضمن التوافق مع PDF / UA أن مستند PDF يتوافق مع معايير إمكانية الوصول ، مما يجعله في متناول المستخدمين ذوي الاحتياجات الخاصة. يوضح البرنامج التعليمي كيفية التحقق من توافق PDF / UA باستخدام ملف`Validate()` طريقة وإنشاء تقرير امتثال XML.

#### س: كيف يمكنني دمج هذه المفاهيم في تطبيقات .NET الخاصة بي؟

ج: يمكنك استخدام أمثلة كود المصدر C # المتوفرة كدليل لتنفيذ تنسيق صف الجدول في تطبيقات .NET الخاصة بك. قم بتعديل وتكييف الكود ليتناسب مع متطلباتك ودمجها في مشاريعك.

#### س: هل هناك أفضل الممارسات الموصى بها لتنسيق صفوف الجدول في مستندات PDF؟

ج: عند تنسيق صفوف الجدول ، ضع في اعتبارك سهولة القراءة وسهولة الوصول إلى المحتوى. تأكد من أن الألوان بها تباين كافٍ ، واستخدم خطوطًا واضحة ومقروءة ، وحافظ على تنسيق ثابت. تحقق من توافق PDF / UA لضمان تلبية معايير إمكانية الوصول.

#### س: ما الميزات الأخرى لبرنامج Aspose.PDF for .NET التي يمكنني استكشافها لتخصيص مستند PDF؟

ج: يوفر Aspose.PDF for .NET مجموعة كبيرة من الميزات لتخصيص مستند PDF ، بما في ذلك معالجة النص وإدراج الصور وإدارة حقل النموذج والتوقيعات الرقمية والتعليقات التوضيحية والمزيد. استشر الوثائق الرسمية والموارد لاستكشاف وظائف إضافية.