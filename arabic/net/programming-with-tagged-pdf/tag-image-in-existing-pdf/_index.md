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
// حدد عنوان وثيقة PDF المميزة
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

//التحقق من توافق PDF / UA للمستند الخارج
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تمييز صورة في ملف PDF موجود باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام Aspose.PDF لإضافة علامات وإجراء تعديلات على الصور في مستندات PDF الخاصة بك.

### التعليمات

#### س: ما هو الهدف الرئيسي من هذا البرنامج التعليمي حول وضع علامات على الصور في ملف PDF موجود باستخدام Aspose.PDF for .NET؟

ج: الهدف الأساسي من هذا البرنامج التعليمي هو إرشادك خلال عملية تمييز صورة داخل مستند PDF موجود باستخدام Aspose.PDF for .NET. يوفر البرنامج التعليمي إرشادات خطوة بخطوة وأمثلة على التعليمات البرمجية المصدر لـ C # لمساعدتك على فهم كيفية تعيين نص بديل ومربعات إحاطة للصور ، ونقل العناصر داخل المستند ، وإضافة علامات إلى الصور.

#### س: ما هي المتطلبات الأساسية لاتباع هذا البرنامج التعليمي حول وضع علامات على الصور في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ ، تأكد من قيامك بإعداد بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتكوين مشروعك للرجوع إليه.

#### س: كيف يمكنني فتح مستند PDF موجود والوصول إلى محتواه المميز باستخدام Aspose.PDF for .NET؟

ج: يقدم البرنامج التعليمي أمثلة على الكود المصدري لـ C # والتي توضح كيفية فتح مستند PDF موجود باستخدام Aspose.PDF لـ .NET والوصول إلى محتواه الموسوم لمزيد من المعالجة.

#### س: ما هو الغرض من تخصيص نص بديل ومربعات إحاطة للصور في مستند PDF؟

ج: يؤدي تعيين نص بديل ومربعات إحاطة للصور إلى تحسين إمكانية الوصول من خلال توفير نص وصفي للصور وتحديد تخطيطها وموضعها داخل المستند. هذه المعلومات ضرورية لقارئات الشاشة والتقنيات المساعدة الأخرى.

#### س: كيف يمكنني تعيين عنوان مستند PDF مميز باستخدام Aspose.PDF لـ .NET؟

ج: يتضمن البرنامج التعليمي أمثلة على التعليمات البرمجية المصدر C # التي توضح كيفية تعيين عنوان مستند PDF بعلامات باستخدام Aspose.PDF لـ .NET.

#### س: ما الذي تتضمنه عملية نقل العناصر داخل مستند PDF؟

ج: يتضمن نقل العناصر داخل مستند PDF تغيير العنصر الأصل لعنصر معين. في هذا البرنامج التعليمي ، ستتعلم كيفية نقل عنصر Span إلى عنصر فقرة محدد داخل جدول.

#### س: كيف يمكنني حفظ مستند PDF المعدل بعد إضافة العلامات وإجراء التعديلات على الصور؟

 ج: بمجرد إضافة العلامات ، وتعيين نص بديل ، وتعيين المربعات المحيطة ، وإجراء تعديلات على مستند PDF ، يمكنك استخدام أمثلة التعليمات البرمجية المصدر C # المتوفرة لحفظ مستند PDF المعدل باستخدام`Save()` طريقة.

#### س: ما هو الغرض من نموذج التعليمات البرمجية المقدم في البرنامج التعليمي؟

ج: نموذج التعليمات البرمجية بمثابة مرجع عملي لتطبيق علامات الصور ومعالجتها باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الرمز كنقطة بداية وتعديله ليناسب متطلباتك الخاصة.

#### س: هل يمكنني تطبيق هذه الأساليب على أنواع أخرى من العناصر في مستند PDF ، وليس الصور فقط؟

ج: نعم ، يمكن تكييف التقنيات الموضحة في هذا البرنامج التعليمي للعمل مع أنواع مختلفة من العناصر داخل مستند PDF. يمكنك تطبيق مبادئ مماثلة لتمييز العناصر الأخرى ومعالجتها مثل النص والجداول والمزيد.

#### س: كيف يمكنني التحقق من توافق PDF / UA لمستند PDF المعدل؟

 ج: يوفر البرنامج التعليمي أمثلة على التعليمات البرمجية المصدر لـ C # والتي توضح كيفية التحقق من توافق PDF / UA لمستند PDF المعدل باستخدام`Validate()` طريقة وإنشاء تقرير XML.

#### س: ما الميزات الأخرى التي يوفرها Aspose.PDF for .NET للعمل مع مستندات PDF؟

ج: يوفر Aspose.PDF for .NET مجموعة كبيرة من الميزات للعمل مع مستندات PDF ، بما في ذلك معالجة النص وإدراج الصور وإنشاء الجدول وإدارة حقل النموذج والتوقيعات الرقمية والتعليقات التوضيحية والمزيد. استشر الوثائق الرسمية والموارد لمزيد من الاستكشاف.