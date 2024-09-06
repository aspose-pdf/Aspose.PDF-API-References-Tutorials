---
title: خلية جدول الأنماط
linktitle: خلية جدول الأنماط
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تصميم خلايا الجدول باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لإنشاء الجداول وتخصيصها.
type: docs
weight: 160
url: /ar/net/programming-with-tagged-pdf/style-table-cell/
---
مرحبًا بك في هذا البرنامج التعليمي المفصل حول تنسيق خلايا الجدول باستخدام Aspose.PDF لـ .NET. في هذا الدليل، سنشرح بالتفصيل كل خطوة من خطوات الكود المصدري C# المقدم لمساعدتك على فهم كيفية تنسيق خلايا الجدول. تأكد من تثبيت Aspose.PDF لـ .NET وإعداد بيئة التطوير الخاصة بك قبل البدء.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

لقد قمنا بإنشاء مستند جديد وقمنا بتعيين عنوان المستند واللغة.

## الخطوة 3: الحصول على عنصر البنية الجذرية

في هذه الخطوة سوف نحصل على عنصر البنية الجذرية لمستندنا.

```csharp
//الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
```

لقد حصلنا على عنصر البنية الجذرية الذي سيعمل كحاوية لعناصر المصفوفة.

## الخطوة 4: إنشاء عنصر هيكل المصفوفة

الآن دعونا نقوم بإنشاء عنصر هيكل جدول جديد للمستند الخاص بنا.

```csharp
// إنشاء عنصر هيكل المصفوفة
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

لقد قمنا بإنشاء عنصر هيكل مصفوفة جديد وأضفناه إلى عنصر الهيكل الجذري. كما قمنا بإنشاء عناصر رأس الجدول وجسمه وتذييله.

## الخطوة 5: إضافة رؤوس الجدول

في هذه الخطوة سوف نقوم بإضافة رؤوس الجدول إلى جدولنا.

```csharp
// عدد الصفوف والأعمدة في الجدول
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// إنشاء صف رأس الجدول
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

لقد أنشأنا صف رأس لجدولنا وأضفنا خلايا رأس مع خصائص التنسيق مثل لون الخلفية والحدود والحواف والمحاذاة.

## الخطوة 6: إضافة صفوف نص الجدول

الآن دعونا نضيف صفوف نص الجدول إلى جدولنا.
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

لقد أضفنا صفوفًا إلى نص الجدول باستخدام حلقات للتكرار على كل خلية في الجدول. لقد قمنا بتعيين خصائص التنسيق لكل خلية، مثل لون الخلفية والحدود والحواف ومحاذاة النص وما إلى ذلك.

## الخطوة 7: إضافة التذييل

وأخيرًا، سنضيف تذييل الجدول إلى جدولنا.

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



## الخطوة 8: حفظ مستند PDF المُوسوم

الآن بعد أن قمنا بإنشاء مستندنا بالجدول المصمم، سنقوم بحفظه كمستند PDF مميز.

```csharp
// احفظ مستند PDF المُوسوم
document.Save(dataDir + "StyleTableCell.pdf");
```

لقد قمنا بحفظ مستند PDF المُوسوم في الدليل المحدد.

## الخطوة 9: التحقق من توافق PDF/UA

بعد ذلك، سوف نقوم بالتحقق من تطابق PDF/UA الخاص بمستندنا.

```csharp
// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

لقد قمنا بتحميل مستند PDF الذي تم وضع العلامة عليه وقمنا بالتحقق من توافقه مع PDF/UA من خلال إنشاء تقرير XML.

### عينة من كود المصدر لـ Style Table Cell باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر البنية الجذرية
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

// حفظ مستند PDF المُوسوم
document.Save(dataDir + "StyleTableCell.pdf");

// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تنسيق خلايا الجدول باستخدام Aspose.PDF for .NET. لقد رأينا كيفية إنشاء مستند وإضافة جدول برؤوس وصفوف نص وتذييل وتخصيص أنماط الخلايا. أخيرًا، قمنا بحفظ مستند PDF المُوسوم والتحقق من توافقه مع PDF/UA. يمكنك الآن استخدام Aspose.PDF for .NET لإنشاء الجداول وتنسيقها في تطبيقات .NET الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي حول تنسيق خلايا الجدول باستخدام Aspose.PDF لـ .NET؟

أ: يهدف هذا البرنامج التعليمي إلى تقديم دليل شامل حول كيفية تنسيق خلايا الجدول في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. وهو يغطي تعليمات خطوة بخطوة وأمثلة كود مصدر C# لمساعدتك على فهم تنسيق خلايا الجدول وتنفيذه.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل أن تبدأ، تأكد من تثبيت Aspose.PDF لـ .NET وإعداد بيئة التطوير الخاصة بك. ويتضمن هذا تكوين مشروعك للإشارة إلى مكتبة Aspose.PDF.

#### س: كيف أقوم بإنشاء مستند PDF جديد باستخدام Aspose.PDF لـ .NET؟

أ: لإنشاء مستند PDF جديد، تحتاج إلى إنشاء مثيل لـ`Document` كائن من مكتبة Aspose.PDF. يوضح كود المصدر C# المقدم كيفية إنشاء مستند وتعيين عنوانه ولغته.

#### س: ما أهمية عنصر البنية الجذرية في مستند PDF؟

ج: يعمل عنصر البنية الجذرية كحاوية لعناصر البنية الأخرى، مما يساعد في تنظيم وتصنيف محتوى مستند PDF. ويلعب دورًا حاسمًا في تحديد البنية المنطقية للمستند.

#### س: كيف يمكنني إنشاء عنصر بنية الجدول وتخصيص مظهره باستخدام Aspose.PDF لـ .NET؟

 أ: يمكنك إنشاء عنصر بنية الجدول باستخدام`CreateTableElement()` يوضح كود المصدر المقدم كيفية تخصيص مظهر الجدول، بما في ذلك رأسه وجسمه وتذييله، عن طريق تعيين خصائص مثل لون الخلفية والحدود والحواف والمحاذاة.

#### س: هل يمكنني إضافة صفوف وأعمدة متعددة إلى نص الجدول وتخصيص تنسيقها؟

ج: نعم، يوضح البرنامج التعليمي كيفية إضافة صفوف وأعمدة متعددة إلى نص الجدول باستخدام الحلقات. كما يوفر أمثلة لتخصيص تنسيق الخلايا، مثل لون الخلفية والحدود ومحاذاة النص ونمط الخط والمزيد.

#### س: ما هو الغرض من التحقق من توافق PDF/UA، وكيف يمكنني إجراء هذا التحقق؟

 أ: يضمن التحقق من توافق PDF/UA أن مستند PDF يلتزم بمعايير إمكانية الوصول، مما يجعله أكثر سهولة في الوصول للمستخدمين ذوي الإعاقة. يوضح البرنامج التعليمي كيفية التحقق من توافق PDF/UA باستخدام`Validate()` الطريقة وإنشاء تقرير XML.

#### س: كيف يمكنني تطبيق هذه المفاهيم على تطبيقات .NET الخاصة بي؟

ج: يمكنك استخدام أمثلة التعليمات البرمجية المصدرية بلغة C# المقدمة كدليل لتنفيذ تنسيق خلايا الجدول في تطبيقات .NET الخاصة بك. قم بتخصيص التعليمات البرمجية حسب الحاجة لتناسب متطلباتك ودمجها في مشاريعك.

#### س: هل هناك أي ممارسات أفضل موصى بها لتصميم خلايا الجدول في مستندات PDF؟

ج: عند تصميم خلايا الجدول، ضع في اعتبارك احتياجات جمهورك، بما في ذلك متطلبات إمكانية الوصول. استخدم الألوان المتباينة والخطوط المناسبة ومحاذاة الخلايا بوضوح لتحسين قابلية القراءة. بالإضافة إلى ذلك، تحقق من توافق PDF/UA لضمان تلبية معايير إمكانية الوصول.

#### س: ما هي الميزات الأخرى لـ Aspose.PDF لـ .NET التي يمكنني استكشافها لمعالجة مستندات PDF؟

ج: يوفر Aspose.PDF for .NET مجموعة واسعة من الميزات لمعالجة مستندات PDF، بما في ذلك استخراج النص، وإدراج الصور، وإدارة حقول النماذج، والتوقيعات الرقمية، والمزيد. استكشف الوثائق والموارد الرسمية لمعرفة المزيد عن الوظائف الإضافية.
