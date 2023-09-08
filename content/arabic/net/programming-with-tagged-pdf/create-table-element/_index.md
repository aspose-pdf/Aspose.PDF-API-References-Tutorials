---
title: إنشاء عنصر الجدول
linktitle: إنشاء عنصر الجدول
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET. قم بإنشاء ملفات PDF ديناميكية باستخدام الجداول بسهولة.
type: docs
weight: 80
url: /ar/net/programming-with-tagged-pdf/create-table-element/
---
في هذا الدليل خطوة بخطوة، سنرشدك خلال عملية إنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك التعامل مع مستندات PDF برمجيًا. يعد إنشاء عنصر مصفوفة مطلبًا شائعًا عند إنشاء ملفات PDF ديناميكية، ويوفر Aspose.PDF طريقة سهلة وفعالة لتحقيق ذلك.

دعنا نتعمق في التعليمات البرمجية ونتعلم كيفية إنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت مكتبة Aspose.PDF لـ .NET.
2. معرفة أساسية بلغة البرمجة C#.

## الخطوة 1: تهيئة البيئة

للبدء، افتح بيئة تطوير C# الخاصة بك وقم بإنشاء مشروع جديد. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء الوثيقة

 الخطوة الأولى هي إنشاء مستند PDF جديد باستخدام الملف`Document` فصل.

```csharp
// قم بإنشاء المستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

هنا نقوم أيضًا بتعيين عنوان ولغة المحتوى الذي تم وضع علامة عليه.

## الخطوة 3: إنشاء عنصر المصفوفة

بعد ذلك، نحتاج إلى إنشاء عنصر المصفوفة وإضافته إلى المستند. نبدأ بالحصول على عنصر البنية الجذرية، ثم نقوم بإنشاء عنصر جدول جديد باستخدام التابع`CreateTableElement` طريقة.

```csharp
// الحصول على عنصر هيكل الجذر
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

// احفظ مستند PDF الذي تم وضع علامة عليه
document.Save(dataDir + "CreateTableElement.pdf");

// فحص التوافق مع PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### نموذج التعليمات البرمجية المصدر لإنشاء عنصر جدول باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر هيكل الجذر
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

// حفظ وثيقة PDF ذات العلامات
document.Save(dataDir + "CreateTableElement.pdf");

// التحقق من توافق PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

لقد تعلمت كيفية إنشاء عنصر صفيف باستخدام Aspose.PDF لـ .NET. يمكنك الآن إنشاء مستندات PDF بجداول ديناميكية باستخدام هذه الطريقة. لا تتردد في استكشاف المزيد من ميزات Aspose.PDF لاكتشاف إمكاناته الكاملة.

### الأسئلة الشائعة

#### س: ما هو عنصر المصفوفة في مستند PDF، ولماذا أحتاج إلى إنشاء عنصر باستخدام Aspose.PDF لـ .NET؟

ج: يمثل عنصر المصفوفة في مستند PDF مجموعة منظمة من البيانات، وغالبًا ما تستخدم لإنشاء الجداول أو الشبكات. قد تحتاج إلى إنشاء عنصر صفيف باستخدام Aspose.PDF لـ .NET عند إنشاء ملفات PDF ديناميكية تتطلب عرض بيانات منظمة، مثل المعلومات الجدولية أو الشبكات.

#### س: كيف يعمل Aspose.PDF for .NET على تبسيط عملية إنشاء عنصر صفيف؟

ج: يوفر Aspose.PDF for .NET مجموعة شاملة من الفئات والأساليب التي تسمح لك بإنشاء عناصر المصفوفة (الجداول) وتخصيصها وإدارتها في مستند PDF برمجيًا. وهذا يلغي الحاجة إلى معالجة ملفات PDF يدويًا ويبسط عملية إنشاء تمثيلات البيانات المنظمة.

#### س: ما هي الخطوات الأساسية المتبعة في إنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET؟

ج: تتضمن الخطوات الأساسية إعداد البيئة، وإنشاء المستند، والحصول على عنصر البنية الجذرية، وإنشاء عنصر جدول، وتحديد الصفوف والخلايا داخل الجدول، وتحديد تنسيق العناصر وخصائصها. يوضح المثال التعليمات البرمجية المتوفرة هذه الخطوات.

####  س: ما هو الدور الذي يقوم به`taggedContent` object play in creating an array element?

 ج: ال`taggedContent` الكائن، الذي تم الحصول عليه من الوثيقة`TaggedContent`تتيح لك الخاصية تحديد بنية المحتوى الذي تم وضع علامة عليه داخل مستند PDF. يتضمن ذلك إنشاء وتنظيم عناصر المصفوفة وعناصرها الفرعية بطريقة هرمية.

#### س: كيف يضمن الكود إمكانية الوصول ودلالات عنصر الصفيف الذي تم إنشاؤه؟

 ج: يقوم الكود بتعيين سمات مثل`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` ، و`ColSpan` لتعزيز إمكانية الوصول ودلالات عنصر الصفيف. تساهم هذه السمات في تمثيل البيانات بشكل جيد التنظيم وغني بالمعلومات وجذاب بصريًا.

#### س: ما هي أهمية التوافق مع PDF/UA في سياق إنشاء عناصر الصفيف؟

 ج: يضمن التوافق مع PDF/UA (إمكانية الوصول الشامل) إمكانية وصول المستخدمين ذوي الإعاقة إلى مستندات PDF التي تم إنشاؤها وتلبية معايير معينة لإمكانية الوصول. يتحقق مثال التعليمات البرمجية من توافق PDF/UA باستخدام ملف`Validate` الطريقة، مما يساعدك على إنشاء مستندات شاملة ويمكن الوصول إليها.

#### س: هل يمكنني تخصيص تنسيق ومظهر عناصر المصفوفة بشكل أكبر؟

ج: نعم، يمكنك تخصيص تنسيق عناصر الصفيف ومظهرها عن طريق ضبط السمات مثل لون الخلفية ونمط الحدود وحجم الخط والمحاذاة. يوفر Aspose.PDF for .NET نطاقًا واسعًا من الخصائص لتخصيص العرض التقديمي المرئي وفقًا لمتطلباتك.

#### س: كيف يمكنني توسيع هذه المعرفة لإنشاء هياكل جدول أكثر تعقيدًا أو دمج عناصر المصفوفة في مستندات PDF أكبر؟

ج: يمكنك توسيع هذه المعرفة من خلال استكشاف ميزات إضافية لـ Aspose.PDF لـ .NET، مثل دمج عناصر مصفوفة متعددة وإنشاء جداول متداخلة وإضافة رؤوس وتذييلات ودمج عناصر المصفوفة في تخطيطات PDF أكبر. توفر وثائق المكتبة وأمثلتها إرشادات لهذه السيناريوهات المتقدمة.

#### س: هل من الممكن استيراد البيانات من مصادر خارجية، مثل قواعد البيانات أو جداول البيانات، لملء عناصر الصفيف؟

ج: نعم، يمكنك استيراد البيانات من مصادر خارجية لملء عناصر المصفوفة. يمكنك استخدام تقنيات استرجاع البيانات وتحويلها في لغة C# لجلب البيانات من قواعد البيانات أو جداول البيانات أو المصادر الأخرى ثم تعبئة عناصر الصفيف وفقًا لذلك.

#### س: كيف يمكنني استخدام المعرفة المكتسبة من هذا البرنامج التعليمي لتحسين جودة وسهولة استخدام مستندات PDF التي أقوم بإنشائها برمجيًا؟

ج: تتيح لك المعرفة المكتسبة من هذا البرنامج التعليمي إنشاء عناصر مصفوفة (جداول) منظمة وجذابة بصريًا في مستندات PDF. من خلال دمج هذه التقنيات، يمكنك تحسين إمكانية القراءة وإمكانية الوصول وتجربة المستخدم لملفات PDF التي تم إنشاؤها ديناميكيًا، مما يجعلها أكثر إفادة وسهولة في الاستخدام.