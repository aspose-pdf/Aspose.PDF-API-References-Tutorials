---
title: نمط خلية الجدول
linktitle: نمط خلية الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تصميم خلايا الجدول باستخدام Aspose.PDF for .NET. دليل تفصيلي لإنشاء الجداول وتخصيصها.
type: docs
weight: 160
url: /ar/net/programming-with-tagged-pdf/style-table-cell/
---
مرحبًا بك في هذا البرنامج التعليمي المفصل حول تنسيق خلايا الجدول باستخدام Aspose.PDF for .NET. في هذا الدليل ، سنشرح بالتفصيل كل خطوة من التعليمات البرمجية المصدر C # المقدمة لمساعدتك على فهم كيفية تصميم خلايا الجدول. تأكد من تثبيت Aspose.PDF for .NET وقم بإعداد بيئة التطوير الخاصة بك قبل أن تبدأ.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

لقد أنشأنا مستندًا جديدًا وحددنا عنوان المستند ولغته.

## الخطوة 3: الحصول على عنصر بنية الجذر

في هذه الخطوة ، سنحصل على عنصر بنية الجذر لوثيقتنا.

```csharp
// الحصول على عنصر بنية الجذر
StructureElement rootElement = taggedContent.RootElement;
```

حصلنا على عنصر بنية الجذر الذي سيكون بمثابة حاوية لعناصر المصفوفة.

## الخطوة 4: إنشاء عنصر بنية المصفوفة

لنقم الآن بإنشاء عنصر هيكل جدول جديد لوثيقتنا.

```csharp
// قم بإنشاء عنصر بنية المصفوفة
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

لقد أنشأنا عنصر هيكل مصفوفة جديد وأضفناه إلى عنصر بنية الجذر. أنشأنا أيضًا عناصر رأس الجدول والجسم والتذييل.

## الخطوة 5: إضافة رؤوس الجدول

في هذه الخطوة سنضيف رؤوس الجدول إلى طاولتنا.

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

أنشأنا صف رأس لجدولنا وأضفنا خلايا رأس بخصائص التنسيق مثل لون الخلفية والحدود والهوامش والمحاذاة.

## الخطوة 6: إضافة صفوف نص الجدول

لنقم الآن بإضافة صفوف جسم الجدول إلى طاولتنا.
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

أضفنا صفوفًا إلى جسم الجدول باستخدام حلقات للتكرار فوق كل خلية في الجدول. قمنا بتعيين خصائص التنسيق لكل خلية ، مثل لون الخلفية ، والحدود ، والهوامش ، ومحاذاة النص ، وما إلى ذلك.

## الخطوة 7: إضافة التذييل

أخيرًا ، سنضيف تذييل الجدول إلى الجدول.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

أنشأنا تذييلًا لجدولنا وأضفنا خلايا تذييل تحتوي على نص.



## الخطوة 8: حفظ مستند PDF الذي تم وضع علامة عليه

الآن بعد أن أنشأنا وثيقتنا مع الجدول المصمم ، سنحفظه كمستند PDF مميز.

```csharp
// احفظ مستند PDF بعلامات
document.Save(dataDir + "StyleTableCell.pdf");
```

لقد حفظنا مستند PDF المميز بعلامات في الدليل المحدد.

## الخطوة 9: التحقق من توافق PDF / UA

بعد ذلك ، سوف نتحقق من توافق PDF / UA لوثيقتنا.

```csharp
// فحص التوافق مع PDF / UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

قمنا بتحميل مستند PDF الذي تم وضع علامة عليه وتحققنا من توافقه مع PDF / UA من خلال إنشاء تقرير XML.

### نموذج التعليمات البرمجية المصدر لـ Style Table Cell باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء وثيقة
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// احصل على عنصر بنية الجذر
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

// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "StyleTableCell.pdf");

// التحقق من توافق PDF / UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تصميم خلايا الجدول باستخدام Aspose.PDF لـ .NET. لقد رأينا كيفية إنشاء مستند وإضافة جدول برؤوس وصفوف النص وتذييل الصفحة وتخصيص أنماط الخلايا. أخيرًا ، قمنا بحفظ مستند PDF الذي تم وضع علامة عليه وتحققنا من توافقه مع PDF / UA. يمكنك الآن استخدام Aspose.PDF for .NET لإنشاء جداول وتصميمها في تطبيقات .NET.
