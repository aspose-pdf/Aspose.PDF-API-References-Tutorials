---
title: إنشاء عنصر الجدول
linktitle: إنشاء عنصر الجدول
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لإنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET. إنشاء ملفات PDF ديناميكية تحتوي على جداول بسهولة.
type: docs
weight: 80
url: /ar/net/programming-with-tagged-pdf/create-table-element/
---
في هذا الدليل التفصيلي، سنوضح لك عملية إنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك التعامل مع مستندات PDF برمجيًا. يعد إنشاء عنصر مصفوفة متطلبًا شائعًا عند إنشاء ملفات PDF ديناميكية، ويوفر Aspose.PDF طريقة سهلة وفعالة لإنجاز هذه المهمة.

دعنا نتعمق في الكود ونتعلم كيفية إنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت مكتبة Aspose.PDF لـ .NET.
2. المعرفة الأساسية للغة البرمجة C#.

## الخطوة 1: إعداد البيئة

للبدء، افتح بيئة تطوير C# وقم بإنشاء مشروع جديد. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند

 الخطوة الأولى هي إنشاء مستند PDF جديد باستخدام`Document` فصل.

```csharp
// إنشاء المستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

هنا قمنا أيضًا بتعيين العنوان واللغة للمحتوى المُوسوم.

## الخطوة 3: إنشاء عنصر المصفوفة

بعد ذلك، نحتاج إلى إنشاء عنصر المصفوفة وإضافته إلى المستند. نبدأ بالحصول على عنصر البنية الجذرية، ثم ننشئ عنصر جدول جديد باستخدام`CreateTableElement` طريقة.

```csharp
// الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
TableTRElement trElement = tableTBodyElement.CreateTR();
trElement.AlternativeText = String.Format("Row {0}", rowIndex);
for (colIndex = 0; colIndex < colCount; colIndex++)
{
int colSpan = 1;
int rowSpan = 1;
if (colIndex == 1 && rowIndex == 1)
{
colSpan = 2;
rowSpan = 2;
}
else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
{
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
tdElement.BackgroundColor = Color.Yellow;
tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
tdElement.IsNoBorder = false;
tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
tdElement.Alignment = HorizontalAlignment.Center;
TextState cellTextState = new TextState();
cellTextState.ForegroundColor = Color.DarkBlue;
cellTextState.FontSize = 7.5F;
cellTextState.FontStyle = FontStyles.Bold;
cellTextState.Font = FontRepository.FindFont("Arial");
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// احفظ مستند PDF المُوسوم
document.Save(dataDir + "CreateTableElement.pdf");

// التحقق من توافق PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### عينة من كود المصدر لإنشاء عنصر جدول باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// حفظ مستند PDF المُوسوم
document.Save(dataDir + "CreateTableElement.pdf");

// التحقق من توافق PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

لقد تعلمت كيفية إنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET. يمكنك الآن إنشاء مستندات PDF بجداول ديناميكية باستخدام هذه الطريقة. لا تتردد في استكشاف المزيد من ميزات Aspose.PDF لاكتشاف إمكاناتها الكاملة.

### الأسئلة الشائعة

#### س: ما هو عنصر المصفوفة في مستند PDF، ولماذا أحتاج إلى إنشاء عنصر باستخدام Aspose.PDF لـ .NET؟

ج: يمثل عنصر المصفوفة في مستند PDF مجموعة منظمة من البيانات، والتي تُستخدم غالبًا لإنشاء الجداول أو الشبكات. قد تحتاج إلى إنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET عند إنشاء ملفات PDF ديناميكية تتطلب عرض بيانات منظمة، مثل المعلومات الجدولية أو الشبكات.

#### س: كيف يقوم Aspose.PDF لـ .NET بتبسيط عملية إنشاء عنصر المصفوفة؟

ج: يوفر Aspose.PDF for .NET مجموعة شاملة من الفئات والطرق التي تسمح لك بإنشاء عناصر المصفوفة (الجداول) وتخصيصها وإدارتها في مستند PDF برمجيًا. وهذا يلغي الحاجة إلى معالجة PDF يدويًا ويبسط إنشاء تمثيلات البيانات المنظمة.

#### س: ما هي الخطوات الأساسية المتبعة في إنشاء عنصر المصفوفة باستخدام Aspose.PDF لـ .NET؟

ج: تتضمن الخطوات الأساسية إعداد البيئة وإنشاء المستند والحصول على عنصر البنية الجذرية وإنشاء عنصر جدول وتحديد الصفوف والخلايا داخل الجدول وتحديد التنسيق والخصائص للعناصر. يوضح مثال التعليمات البرمجية المقدم هذه الخطوات.

####  س: ما هو الدور الذي يلعبه`taggedContent` object play in creating an array element?

 أ: ال`taggedContent` الكائن الذي تم الحصول عليه من المستند`TaggedContent`تتيح لك الخاصية تحديد بنية المحتوى المُوسوم داخل مستند PDF. ويتضمن ذلك إنشاء عناصر المصفوفة وعناصرها الفرعية وتنظيمها بطريقة هرمية.

#### س: كيف يضمن الكود إمكانية الوصول ودلالات عنصر المصفوفة الذي تم إنشاؤه؟

 أ: يحدد الكود السمات مثل`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` ، و`ColSpan` لتعزيز إمكانية الوصول إلى عناصر المصفوفة ودلالاتها. تساهم هذه السمات في تمثيل البيانات بشكل جيد ومفيد وجذاب بصريًا.

#### س: ما هي أهمية التوافق مع PDF/UA في سياق إنشاء عناصر المصفوفة؟

 أ: يضمن توافق PDF/UA (إمكانية الوصول الشامل) أن مستندات PDF الناتجة يمكن الوصول إليها من قبل المستخدمين ذوي الإعاقة وتلبي معايير إمكانية الوصول المحددة. يتحقق مثال التعليمات البرمجية من توافق PDF/UA باستخدام`Validate` الطريقة التي تساعدك على إنشاء مستندات شاملة وسهلة الوصول إليها.

#### س: هل يمكنني تخصيص تنسيق ومظهر عناصر المصفوفة بشكل أكبر؟

ج: نعم، يمكنك تخصيص تنسيق ومظهر عناصر المصفوفة من خلال ضبط السمات مثل لون الخلفية ونمط الحدود وحجم الخط والمحاذاة. يوفر Aspose.PDF for .NET مجموعة واسعة من الخصائص لتخصيص العرض المرئي وفقًا لمتطلباتك.

#### س: كيف يمكنني توسيع هذه المعرفة لإنشاء هياكل جدول أكثر تعقيدًا أو دمج عناصر المصفوفة في مستندات PDF أكبر حجمًا؟

ج: يمكنك توسيع هذه المعرفة من خلال استكشاف الميزات الإضافية لبرنامج Aspose.PDF for .NET، مثل دمج عناصر مصفوفة متعددة، وإنشاء جداول متداخلة، وإضافة رؤوس وتذييلات، ودمج عناصر المصفوفة في تخطيطات PDF أكبر. توفر وثائق المكتبة وأمثلتها إرشادات لهذه السيناريوهات المتقدمة.

#### س: هل من الممكن استيراد البيانات من مصادر خارجية، مثل قواعد البيانات أو جداول البيانات، لملء عناصر المصفوفة؟

ج: نعم، يمكنك استيراد البيانات من مصادر خارجية لتعبئة عناصر المصفوفة. يمكنك استخدام تقنيات استرجاع البيانات وتحويلها في لغة C# لجلب البيانات من قواعد البيانات أو جداول البيانات أو مصادر أخرى ثم تعبئة عناصر المصفوفة وفقًا لذلك.

#### س: كيف يمكنني استخدام المعرفة المكتسبة من هذا البرنامج التعليمي لتحسين جودة وسهولة استخدام مستندات PDF التي أقوم بإنشائها برمجيًا؟

ج: تتيح لك المعرفة المكتسبة من هذا البرنامج التعليمي إنشاء عناصر مصفوفة (جداول) منظمة وجذابة بصريًا في مستندات PDF. من خلال دمج هذه التقنيات، يمكنك تحسين قابلية القراءة وإمكانية الوصول وتجربة المستخدم لملفات PDF المولدة ديناميكيًا، مما يجعلها أكثر إفادة وسهولة في الاستخدام.