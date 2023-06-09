---
title: صورة العلامة في ملف PDF الحالي
linktitle: صورة العلامة في ملف PDF الحالي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية ترميز صورة في ملف PDF موجود باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة لإضافة العلامات إلى الصور.
type: docs
weight: 210
url: /ar/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
في هذا البرنامج التعليمي المفصل ، سنرشدك عبر كود المصدر C # المقدم خطوة بخطوة لترميز صورة في ملف PDF موجود باستخدام Aspose.PDF for .NET. اتبع الإرشادات أدناه لفهم كيفية إضافة علامات إلى صورة في ملف PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من تكوين بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتهيئة مشروعك للرجوع إليه.

## الخطوة 2: افتح مستند PDF الحالي

في هذه الخطوة ، سنفتح مستند PDF موجود باستخدام Aspose.PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// مسارات ملفات الإدخال والإخراج
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// افتح المستند
Document document = new Document(inFile);
```

فتحنا مستند PDF الحالي باستخدام Aspose.PDF.

## الخطوة 3: الحصول على المحتوى ذي العلامات وعنصر بنية الجذر

الآن سوف نحصل على المحتوى المميز لمستند PDF وعنصر بنية الجذر المقابل.

```csharp
// احصل على المحتوى الذي تم وضع علامة عليه وعنصر بنية الجذر
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

لقد حصلنا على المحتوى الموسوم لمستند PDF وعنصر بنية الجذر المقابل.

## الخطوة 4: تعيين عنوان مستند PDF الذي تم وضع علامة عليه

لنقم الآن بتعيين عنوان مستند PDF الذي تم وضع علامة عليه.

```csharp
//حدد عنوان وثيقة PDF المميزة
taggedContent.SetTitle("Document with images");
```

لقد قمنا بتعيين عنوان وثيقة PDF الموسومة.

## الخطوة 5: تعيين نصوص بديلة ومربع إحاطة للصورة

الآن ، لكل عنصر صورة ، سنقوم بتعيين نص بديل ومربع محيط.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // تعيين نص بديل للصورة
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // إنشاء وتعيين الصندوق المحيط (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

لقد قمنا بتعيين نص بديل ومربع محيط لكل عنصر صورة في مستند PDF.

## الخطوة 6: نقل عنصر Span إلى الفقرة

الآن دعنا ننقل عنصر Span إلى الفقرة.

```csharp
// انقل عنصر Span إلى فقرة (ابحث عن مسافة وفقرة غير صحيحة في أول TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// انقل عنصر Span في الفقرة
spanElement.ChangeParentElement(paragraph);
```

قمنا بنقل عنصر Span إلى الفقرة المحددة.

## الخطوة 7: حفظ مستند PDF المعدل

الآن بعد أن أجرينا التغييرات اللازمة ، سنقوم بحفظ مستند PDF المعدل.

```csharp
// احفظ مستند PDF
document. Save(outFile);
```

قمنا بحفظ مستند PDF المعدل في الدليل المحدد.

### عينة من التعليمات البرمجية المصدر لصورة العلامات في ملف PDF الحالي باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// افتح المستند
Document document = new Document(inFile);

// يحصل على علامات المحتوى وعنصر بنية الجذر
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// تعيين عنوان وثيقة pdf الموسومة
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// تعيين نص بديل للشكل
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// إنشاء وتعيين سمة BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// انقل Span Element إلى Paragraph (ابحث عن مسافة وفقرة خاطئة في أول TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// نقل عنصر النطاق إلى فقرة
spanElement.ChangeParentElement(paragraph);

// احفظ المستند
document.Save(outFile);

// التحقق من توافق PDF / UA للمستند الخارج
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تمييز صورة في ملف PDF موجود باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام Aspose.PDF لإضافة علامات وإجراء تعديلات على الصور في مستندات PDF الخاصة بك.
