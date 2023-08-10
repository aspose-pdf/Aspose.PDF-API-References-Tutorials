---
title: إنشاء عنصر الجدول
linktitle: إنشاء عنصر الجدول
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإنشاء عنصر صفيف باستخدام Aspose.PDF for .NET. قم بإنشاء ملفات PDF ديناميكية باستخدام الجداول بسهولة.
type: docs
weight: 80
url: /ar/net/programming-with-tagged-pdf/create-table-element/
---
في هذا الدليل المفصل خطوة بخطوة ، سنرشدك خلال عملية إنشاء عنصر مصفوفة باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك معالجة مستندات PDF برمجيًا. يعد إنشاء عنصر مصفوفة مطلبًا شائعًا عند إنشاء ملفات PDF ديناميكية ، ويوفر Aspose.PDF طريقة سهلة وفعالة لإنجاز ذلك.

دعنا نتعمق في الكود ونتعلم كيفية إنشاء عنصر مصفوفة باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

1. تثبيت مكتبة Aspose.PDF لـ .NET.
2. معرفة أساسية بلغة البرمجة C #.

## الخطوة الأولى: تهيئة البيئة

للبدء ، افتح بيئة التطوير C # وأنشئ مشروعًا جديدًا. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند

 تتمثل الخطوة الأولى في إنشاء مستند PDF جديد باستخدام امتداد`Document` فصل.

```csharp
// قم بإنشاء المستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

هنا نقوم أيضًا بتعيين العنوان واللغة للمحتوى الذي تم وضع علامة عليه.

## الخطوة 3: إنشاء عنصر المصفوفة

بعد ذلك ، نحتاج إلى إنشاء عنصر المصفوفة وإضافته إلى المستند. نبدأ بالحصول على عنصر بنية الجذر ، ثم نقوم بإنشاء عنصر جدول جديد باستخدام`CreateTableElement` طريقة.

```csharp
// احصل على عنصر بنية الجذر
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

// احفظ مستند PDF بعلامات
document.Save(dataDir + "CreateTableElement.pdf");

// فحص التوافق مع PDF / UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### نموذج التعليمات البرمجية المصدر لـ Create Table Element باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء وثيقة
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر بنية الجذر
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

// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "CreateTableElement.pdf");

// التحقق من توافق PDF / UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

لقد تعلمت كيفية إنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET. يمكنك الآن إنشاء مستندات PDF بجداول ديناميكية باستخدام هذه الطريقة. لا تتردد في استكشاف المزيد من ميزات Aspose.PDF لاكتشاف إمكاناتها الكاملة.

### التعليمات

#### س: ما هو عنصر المصفوفة في مستند PDF ، ولماذا سأحتاج إلى إنشاء واحد باستخدام Aspose.PDF لـ .NET؟

ج: يمثل عنصر مصفوفة في مستند PDF مجموعة منظمة من البيانات ، تُستخدم غالبًا لإنشاء جداول أو شبكات. قد تحتاج إلى إنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET عند إنشاء ملفات PDF ديناميكية تتطلب عرضًا منظمًا للبيانات ، مثل المعلومات الجدولية أو الشبكات.

#### س: كيف يعمل Aspose.PDF for .NET على تبسيط عملية تكوين عنصر مصفوفة؟

ج: يوفر Aspose.PDF for .NET مجموعة شاملة من الفئات والطرق التي تتيح لك إنشاء عناصر الصفيف (الجداول) وتخصيصها وإدارتها في مستند PDF برمجيًا. هذا يلغي الحاجة إلى معالجة PDF يدويًا ويبسط إنشاء تمثيلات البيانات المنظمة.

#### س: ما هي الخطوات الأساسية المتضمنة في إنشاء عنصر مصفوفة باستخدام Aspose.PDF for .NET؟

ج: تتضمن الخطوات الأساسية إعداد البيئة ، وإنشاء المستند ، والحصول على عنصر البنية الجذرية ، وإنشاء عنصر جدول ، وتحديد الصفوف والخلايا داخل الجدول ، وتحديد التنسيق والخصائص للعناصر. يوضح مثال الكود المقدم هذه الخطوات.

####  س: ما هو الدور الذي يقوم به`taggedContent` object play in creating an array element?

 ج: إن`taggedContent` تم الحصول عليها من المستند`TaggedContent`الخاصية ، تتيح لك تحديد بنية المحتوى المميز بعلامات داخل مستند PDF. يتضمن ذلك إنشاء وتنظيم عناصر المصفوفة وعناصرها الفرعية بطريقة هرمية.

#### س: كيف يضمن الكود إمكانية الوصول والدلالات لعنصر الصفيف الذي تم إنشاؤه؟

 ج: يقوم الكود بتعيين سمات مثل`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` ، و`ColSpan` لتعزيز إمكانية الوصول ودلالات عنصر المصفوفة. تساهم هذه السمات في تمثيل بيانات منظم جيدًا وغني بالمعلومات وجذاب بصريًا.

#### س: ما هي أهمية توافق PDF / UA في سياق إنشاء عناصر مصفوفة؟

 ج: يضمن التوافق مع PDF / UA (إمكانية الوصول العالمي) إمكانية الوصول إلى مستندات PDF المُنشأة للمستخدمين ذوي الاحتياجات الخاصة وتلبية معايير وصول معينة. يتحقق مثال الرمز من توافق PDF / UA باستخدام امتداد`Validate` طريقة تساعدك على إنشاء مستندات شاملة ويمكن الوصول إليها.

#### س: هل يمكنني تخصيص تنسيق ومظهر عناصر الصفيف بشكل أكبر؟

ج: نعم ، يمكنك تخصيص تنسيق عناصر المصفوفة ومظهرها عن طريق ضبط السمات مثل لون الخلفية ونمط الحد وحجم الخط والمحاذاة. يوفر Aspose.PDF for .NET نطاقًا واسعًا من الخصائص لتكييف العرض المرئي وفقًا لمتطلباتك.

#### س: كيف يمكنني توسيع نطاق هذه المعرفة لإنشاء هياكل جدول أكثر تعقيدًا أو دمج عناصر صفيف في مستندات PDF أكبر؟

ج: يمكنك توسيع هذه المعرفة من خلال استكشاف ميزات إضافية لـ Aspose.PDF for .NET ، مثل دمج عناصر صفيف متعددة وإنشاء جداول متداخلة وإضافة رؤوس وتذييلات ودمج عناصر الصفيف في تخطيطات PDF أكبر. توفر وثائق وأمثلة المكتبة إرشادات لهذه السيناريوهات المتقدمة.

#### س: هل من الممكن استيراد البيانات من مصادر خارجية ، مثل قواعد البيانات أو جداول البيانات ، لتعبئة عناصر الصفيف؟

ج: نعم ، يمكنك استيراد البيانات من مصادر خارجية لتعبئة عناصر الصفيف. يمكنك استخدام تقنيات استرداد البيانات وتحويلها في C # لجلب البيانات من قواعد البيانات أو جداول البيانات أو مصادر أخرى ثم تعبئة عناصر الصفيف وفقًا لذلك.

#### س: كيف يمكنني استخدام المعرفة المكتسبة من هذا البرنامج التعليمي لتحسين جودة وسهولة استخدام مستندات PDF التي أقوم بإنشائها برمجيًا؟

ج: تتيح لك المعرفة المكتسبة من هذا البرنامج التعليمي إنشاء عناصر مصفوفة منظمة وجذابة بصريًا (جداول) في مستندات PDF. من خلال دمج هذه التقنيات ، يمكنك تحسين قابلية القراءة وإمكانية الوصول وتجربة المستخدم لملفات PDF التي يتم إنشاؤها ديناميكيًا ، مما يجعلها أكثر إفادة وسهولة في الاستخدام.