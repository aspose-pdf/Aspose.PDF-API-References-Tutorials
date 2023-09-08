---
title: نمط خلية الجدول
linktitle: نمط خلية الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تصميم خلايا الجدول باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لإنشاء الجداول وتخصيصها.
type: docs
weight: 160
url: /ar/net/programming-with-tagged-pdf/style-table-cell/
---
مرحبًا بك في هذا البرنامج التعليمي التفصيلي حول تنسيق خلايا الجدول باستخدام Aspose.PDF لـ .NET. في هذا الدليل، سنشرح بالتفصيل كل خطوة من التعليمات البرمجية المصدر لـ C# لمساعدتك على فهم كيفية تصميم خلايا الجدول. تأكد من تثبيت Aspose.PDF لـ .NET وإعداد بيئة التطوير الخاصة بك قبل البدء.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

لقد أنشأنا مستندًا جديدًا وقمنا بتعيين عنوان المستند ولغته.

## الخطوة 3: الحصول على عنصر البنية الجذرية

في هذه الخطوة سوف نحصل على عنصر البنية الجذرية لمستندنا.

```csharp
//الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
```

لقد حصلنا على عنصر البنية الجذرية الذي سيكون بمثابة حاوية لعناصر المصفوفة.

## الخطوة 4: إنشاء عنصر هيكل الصفيف

لنقم الآن بإنشاء عنصر هيكل جدول جديد لمستندنا.

```csharp
// إنشاء عنصر هيكل الصفيف
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

لقد أنشأنا عنصر بنية صفيف جديدًا وأضفناه إلى عنصر البنية الجذرية. لقد أنشأنا أيضًا عناصر رأس الجدول ونصه وتذييله.

## الخطوة 5: إضافة رؤوس الجدول

في هذه الخطوة سنقوم بإضافة رؤوس الجدول إلى طاولتنا.

```csharp
// عدد الصفوف والأعمدة في الجدول
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// قم بإنشاء صف رأس الجدول
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

لقد أنشأنا صف رأس لجدولنا وأضفنا خلايا رأس بخصائص التنسيق مثل لون الخلفية والحدود والهوامش والمحاذاة.

## الخطوة 6: إضافة صفوف نص الجدول

الآن دعونا نضيف صفوف نص الجدول إلى طاولتنا.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

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
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
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
```

أضفنا صفوفًا إلى نص الجدول باستخدام حلقات للتكرار فوق كل خلية في الجدول. نقوم بتعيين خصائص التنسيق لكل خلية، مثل لون الخلفية والحدود والهوامش ومحاذاة النص وما إلى ذلك.

## الخطوة 7: إضافة التذييل

وأخيرًا، سنضيف تذييل الجدول إلى طاولتنا.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

لقد أنشأنا تذييلًا لجدولنا وأضفنا خلايا تذييل تحتوي على نص.



## الخطوة 8: حفظ مستند PDF الذي تم وضع علامة عليه

الآن بعد أن أنشأنا مستندنا بالجدول المصمم، سنقوم بحفظه كمستند PDF ذو علامات.

```csharp
// احفظ مستند PDF الذي تم وضع علامة عليه
document.Save(dataDir + "StyleTableCell.pdf");
```

لقد حفظنا مستند PDF الذي تم وضع علامة عليه في الدليل المحدد.

## الخطوة 9: التحقق من صحة التوافق مع PDF/UA

بعد ذلك، سوف نقوم بالتحقق من مطابقة PDF/UA لوثيقتنا.

```csharp
// فحص التوافق مع PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

لقد قمنا بتحميل مستند PDF الذي تم وضع علامة عليه وتحققنا من امتثاله لـ PDF/UA من خلال إنشاء تقرير XML.

### نموذج التعليمات البرمجية المصدر لـ Style Table Cell باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر هيكل الجذر
StructureElement rootElement = taggedContent.RootElement;

// إنشاء عنصر هيكل الجدول
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
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
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// حفظ وثيقة PDF ذات العلامات
document.Save(dataDir + "StyleTableCell.pdf");

// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تصميم خلايا الجدول باستخدام Aspose.PDF لـ .NET. لقد رأينا كيفية إنشاء مستند وإضافة جدول يحتوي على رؤوس وصفوف نص وتذييل وتخصيص أنماط الخلايا. أخيرًا، قمنا بحفظ مستند PDF الذي تم وضع علامة عليه وتحققنا من امتثاله لـ PDF/UA. يمكنك الآن استخدام Aspose.PDF لـ .NET لإنشاء الجداول وتصميمها في تطبيقات .NET الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي حول تنسيق خلايا الجدول باستخدام Aspose.PDF لـ .NET؟

ج: يهدف هذا البرنامج التعليمي إلى توفير دليل شامل حول كيفية تصميم خلايا الجدول في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. وهو يغطي إرشادات خطوة بخطوة وأمثلة التعليمات البرمجية المصدر لـ C# لمساعدتك على فهم تنسيق خلايا الجدول وتنفيذه.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل أن تبدأ، تأكد من أنك قمت بتثبيت Aspose.PDF لـ .NET وقمت بإعداد بيئة التطوير الخاصة بك. يتضمن ذلك تكوين مشروعك للإشارة إلى مكتبة Aspose.PDF.

#### س: كيف يمكنني إنشاء مستند PDF جديد باستخدام Aspose.PDF لـ .NET؟

ج: لإنشاء مستند PDF جديد، تحتاج إلى إنشاء نسخة`Document` كائن من مكتبة Aspose.PDF. يوضح كود مصدر C# المقدم كيفية إنشاء مستند وتعيين عنوانه ولغته.

#### س: ما هي أهمية عنصر البنية الجذرية في مستند PDF؟

ج: يعمل عنصر البنية الجذرية كحاوية لعناصر البنية الأخرى، مما يساعد على تنظيم وتصنيف محتوى مستند PDF. إنه يلعب دورًا حاسمًا في إنشاء البنية المنطقية للوثيقة.

#### س: كيف يمكنني إنشاء عنصر هيكل جدول وتخصيص مظهره باستخدام Aspose.PDF لـ .NET؟

 ج: يمكنك إنشاء عنصر هيكل الجدول باستخدام ملف`CreateTableElement()` طريقة. يوضح الكود المصدري المقدم كيفية تخصيص مظهر الجدول، بما في ذلك رأسه ونصه وتذييله، عن طريق تعيين خصائص مثل لون الخلفية والحدود والهوامش والمحاذاة.

#### س: هل يمكنني إضافة صفوف وأعمدة متعددة إلى نص الجدول وتخصيص تنسيقها؟

ج: نعم، يوضح البرنامج التعليمي كيفية إضافة صفوف وأعمدة متعددة إلى نص الجدول باستخدام الحلقات. كما يوفر أيضًا أمثلة لتخصيص تنسيق الخلايا، مثل لون الخلفية والحدود ومحاذاة النص ونمط الخط والمزيد.

#### س: ما هو الغرض من التحقق من صحة توافق PDF/UA، وكيف يمكنني إجراء هذا التحقق من الصحة؟

 ج: يضمن التحقق من توافق PDF/UA أن مستند PDF يلتزم بمعايير إمكانية الوصول، مما يجعله في متناول المستخدمين ذوي الإعاقة. يوضح البرنامج التعليمي كيفية التحقق من صحة مطابقة PDF/UA باستخدام ملف`Validate()` الطريقة وإنشاء تقرير XML.

#### س: كيف يمكنني تطبيق هذه المفاهيم على تطبيقات .NET الخاصة بي؟

ج: يمكنك استخدام أمثلة التعليمات البرمجية المصدر C# المتوفرة كدليل لتنفيذ تنسيق خلايا الجدول في تطبيقات .NET الخاصة بك. قم بتخصيص الكود حسب الحاجة ليناسب متطلباتك ودمجه في مشاريعك.

#### س: هل هناك أي أفضل الممارسات الموصى بها لتصميم خلايا الجدول في مستندات PDF؟

ج: عند تصميم خلايا الجدول، ضع في اعتبارك احتياجات جمهورك، بما في ذلك متطلبات إمكانية الوصول. استخدم الألوان المتباينة والخطوط المناسبة ومحاذاة الخلايا الواضحة لتحسين إمكانية القراءة. بالإضافة إلى ذلك، التحقق من صحة توافق PDF/UA لضمان استيفاء معايير إمكانية الوصول.

#### س: ما هي الميزات الأخرى لـ Aspose.PDF لـ .NET التي يمكنني استكشافها لمعالجة مستندات PDF؟

ج: يوفر Aspose.PDF for .NET نطاقًا واسعًا من الميزات لمعالجة مستندات PDF، بما في ذلك استخراج النص وإدراج الصور وإدارة حقل النموذج والتوقيعات الرقمية والمزيد. استكشف الوثائق والموارد الرسمية للتعرف على الوظائف الإضافية.
