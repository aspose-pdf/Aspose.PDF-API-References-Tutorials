---
title: صف جدول الأنماط
linktitle: صف جدول الأنماط
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تخصيص صفوف الجدول باستخدام دليل Aspose.PDF لـ .NET خطوة بخطوة لتصميم وتنسيق الصفوف.
type: docs
weight: 180
url: /ar/net/programming-with-tagged-pdf/style-table-row/
---
في هذا البرنامج التعليمي المفصل، سنشرح لك خطوة بخطوة التعليمات البرمجية المصدرية المقدمة بلغة C# لتنسيق صف الجدول باستخدام Aspose.PDF لـ .NET. اتبع الإرشادات أدناه لفهم كيفية تخصيص أنماط وخصائص صف الجدول.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

// إنشاء صف رأس الجدول
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

// إنشاء خط تذييل الجدول
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

لقد قمنا بتخصيص جوانب مختلفة من صف الجدول، مثل لون الخلفية، والحدود، وارتفاع الصف، والترقيم، ونمط الخلية الافتراضي، والمزيد.

## الخطوة 6: حفظ مستند PDF المُوسوم

الآن بعد أن قمنا بإنشاء مستندنا باستخدام صف الجدول المصمم، سنقوم بحفظه كمستند PDF مميز.
```csharp
// احفظ مستند PDF المُوسوم
document.Save(dataDir + "StyleTableRow.pdf");
```

لقد قمنا بحفظ مستند PDF المُوسوم في الدليل المحدد.

## الخطوة 7: التحقق من توافق PDF/UA

بعد ذلك، سوف نقوم بالتحقق من تطابق PDF/UA الخاص بمستندنا.

```csharp
// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

لقد قمنا بتحميل مستند PDF الذي تم وضع العلامة عليه وقمنا بالتحقق من توافقه مع PDF/UA من خلال إنشاء تقرير XML.


### عينة من كود المصدر لجدول الأنماط باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر البنية الجذرية
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

// حفظ مستند PDF المُوسوم
document.Save(dataDir + "StyleTableRow.pdf");

// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تنسيق صف الجدول باستخدام Aspose.PDF لـ .NET. قمنا بتخصيص أنماط وخصائص صف الجدول، وأضفنا الرؤوس وصفوف النص والتذييل، وحفظنا مستند PDF المُوسوم، وتحققنا من توافقه مع PDF/UA.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي حول تنسيق صفوف الجدول باستخدام Aspose.PDF لـ .NET؟

ج: الغرض من هذا البرنامج التعليمي هو إرشادك خلال عملية تنسيق صفوف الجدول في مستند PDF باستخدام Aspose.PDF لـ .NET. وهو يوفر تعليمات خطوة بخطوة وأمثلة لأكواد المصدر C# لمساعدتك في تخصيص أنماط وخصائص صفوف الجدول.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء، تأكد من إعداد بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن هذا تثبيت مكتبة Aspose.PDF وتكوين مشروعك للإشارة إليها.

#### س: كيف يمكنني إنشاء مستند PDF جديد وتعيين عنوانه ولغته باستخدام Aspose.PDF لـ .NET؟

 أ: لإنشاء مستند PDF جديد، تحتاج إلى إنشاء`Document` كائن من مكتبة Aspose.PDF. يوضح كود المصدر C# المقدم في البرنامج التعليمي كيفية إنشاء مستند وتعيين عنوانه وخصائص اللغة الخاصة به.

#### س: ما أهمية عنصر البنية الجذرية في مستند PDF؟

ج: يعمل عنصر البنية الجذرية كحاوية لعناصر البنية الأخرى، مما يساعد في تنظيم وتصنيف محتوى مستند PDF. ويلعب دورًا حاسمًا في تحديد البنية المنطقية للمستند.

#### س: كيف أقوم بإنشاء عنصر بنية جدول وتخصيصه لتنسيق صفوف الجدول باستخدام Aspose.PDF لـ .NET؟

أ: يشرح البرنامج التعليمي كيفية إنشاء عنصر بنية الجدول وتخصيص خصائصه لتنسيق صفوف الجدول. ويغطي جوانب مثل لون الخلفية والحدود وارتفاع الصف والترقيم ونمط الخلية الافتراضي والمزيد.

#### س: هل يمكنني تخصيص أنماط وخصائص الخلايا الفردية ضمن صف الجدول؟

ج: نعم، يمكنك تخصيص أنماط وخصائص الخلايا الفردية ضمن صف الجدول. يوضح البرنامج التعليمي كيفية تعيين خصائص مثل لون الخلفية والحدود ولون النص والحشو والمزيد لخلايا الجدول ضمن صف الجدول المنسق.

#### س: كيف يمكنني إضافة رؤوس الصفحات وصفوف النص وتذييل الصفحة إلى صف الجدول المنسق؟

ج: يوفر البرنامج التعليمي أمثلة لإنشاء وإضافة رؤوس وصفوف نص وتذييل إلى عنصر بنية الجدول. يمكن تخصيص هذه العناصر بشكل أكبر باستخدام الخصائص الموضحة في البرنامج التعليمي.

#### س: ما هو التوافق مع PDF/UA، وكيف يمكنني التحقق من صحته لمستند PDF الذي قمت بوضع علامة عليه؟

 أ: يضمن توافق PDF/UA أن مستند PDF يتوافق مع معايير إمكانية الوصول، مما يجعله أكثر سهولة في الوصول للمستخدمين ذوي الإعاقة. يوضح البرنامج التعليمي كيفية التحقق من صحة توافق PDF/UA باستخدام`Validate()` الطريقة وإنشاء تقرير امتثال XML.

#### س: كيف يمكنني دمج هذه المفاهيم في تطبيقات .NET الخاصة بي؟

ج: يمكنك استخدام أمثلة التعليمات البرمجية المصدرية بلغة C# المقدمة كدليل لتنفيذ تنسيق صفوف الجدول في تطبيقات .NET الخاصة بك. قم بتعديل التعليمات البرمجية وتكييفها لتتناسب مع متطلباتك ودمجها في مشاريعك.

#### س: هل هناك أي ممارسات أفضل موصى بها لتنسيق صفوف الجدول في مستندات PDF؟

أ: عند تنسيق صفوف الجدول، ضع في اعتبارك قابلية قراءة المحتوى وإمكانية الوصول إليه. تأكد من أن الألوان تحتوي على تباين كافٍ، واستخدم خطوطًا واضحة وقابلة للقراءة، وحافظ على تخطيط متناسق. تحقق من توافق PDF/UA لضمان تلبية معايير إمكانية الوصول.

#### س: ما هي الميزات الأخرى لـ Aspose.PDF لـ .NET التي يمكنني استكشافها لتخصيص مستند PDF؟

ج: يوفر Aspose.PDF for .NET مجموعة واسعة من الميزات لتخصيص مستندات PDF، بما في ذلك معالجة النصوص، وإدراج الصور، وإدارة حقول النماذج، والتوقيعات الرقمية، والتعليقات التوضيحية، والمزيد. راجع الوثائق والموارد الرسمية لاستكشاف الوظائف الإضافية.