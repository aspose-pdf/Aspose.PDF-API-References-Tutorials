---
title: وضع علامة على الصورة في ملف PDF الموجود
linktitle: وضع علامة على الصورة في ملف PDF الموجود
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية ترميز صورة في ملف PDF موجود باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لإضافة العلامات إلى الصور.
type: docs
weight: 210
url: /ar/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
في هذا البرنامج التعليمي التفصيلي، سنرشدك عبر كود مصدر C# المقدم خطوة بخطوة لترميز صورة في ملف PDF موجود باستخدام Aspose.PDF for .NET. اتبع الإرشادات أدناه لفهم كيفية إضافة علامات إلى صورة في ملف PDF.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من تكوين بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتكوين مشروعك للرجوع إليه.

## الخطوة 2: افتح مستند PDF الموجود

في هذه الخطوة، سنقوم بفتح مستند PDF موجود باستخدام Aspose.PDF.

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

لقد فتحنا مستند PDF الحالي باستخدام Aspose.PDF.

## الخطوة 3: الحصول على المحتوى الموسوم وعنصر البنية الجذرية

سنحصل الآن على المحتوى المميز لمستند PDF وعنصر البنية الجذرية المقابل.

```csharp
// احصل على المحتوى الموسوم وعنصر البنية الجذرية
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

لقد حصلنا على المحتوى المميز لمستند PDF وعنصر البنية الجذرية المقابل.

## الخطوة 4: تحديد عنوان مستند PDF الذي تم وضع علامة عليه

لنقم الآن بتعيين عنوان مستند PDF الذي تم وضع علامة عليه.

```csharp
// حدد عنوان مستند PDF الذي تم وضع علامة عليه
taggedContent.SetTitle("Document with images");
```

لقد قمنا بتعيين عنوان مستند PDF الذي تم وضع علامة عليه.

## الخطوة 5: قم بتعيين النصوص البديلة والمربع المحيط بالصورة

الآن، لكل عنصر من عناصر الصورة، سنقوم بتعيين نص بديل ومربع محيط.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // تعيين نص بديل للصورة
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // إنشاء وتعيين المربع المحيط (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

لقد قمنا بتعيين نص بديل ومربع محيط لكل عنصر صورة في مستند PDF.

## الخطوة 6: نقل عنصر الامتداد إلى الفقرة

الآن دعنا ننقل عنصر Span إلى الفقرة.

```csharp
// انقل عنصر Span إلى الفقرة (ابحث عن مدى وفقرة غير صحيحة في TD الأول)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// انقل عنصر Span في الفقرة
spanElement.ChangeParentElement(paragraph);
```

قمنا بنقل عنصر Span إلى الفقرة المحددة.

## الخطوة 7: حفظ مستند PDF المعدل

الآن بعد أن قمنا بالتغييرات اللازمة، سنقوم بحفظ مستند PDF المعدل.

```csharp
// احفظ مستند PDF
document. Save(outFile);
```

لقد حفظنا مستند PDF المعدل في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Tag Image In Existing PDF باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// افتح المستند
Document document = new Document(inFile);

// يحصل على المحتوى الموسوم وعنصر البنية الجذرية
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// تعيين عنوان لوثيقة pdf الموسومة
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// تعيين النص البديل للشكل
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// إنشاء وتعيين سمة BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// انقل عنصر Span إلى الفقرة (ابحث عن نطاق خاطئ وفقرة في TD الأول)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// نقل عنصر Span إلى الفقرة
spanElement.ChangeParentElement(paragraph);

// حفظ المستند
document.Save(outFile);

//التحقق من توافق PDF/UA للوثيقة الخارجية
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية ترميز صورة في ملف PDF موجود باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام Aspose.PDF لإضافة علامات وإجراء تعديلات على الصور في مستندات PDF الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو الهدف الرئيسي لهذا البرنامج التعليمي حول وضع علامات على الصور في ملف PDF موجود باستخدام Aspose.PDF لـ .NET؟

ج: الهدف الأساسي من هذا البرنامج التعليمي هو إرشادك خلال عملية وضع علامات على صورة داخل مستند PDF موجود باستخدام Aspose.PDF لـ .NET. يوفر البرنامج التعليمي إرشادات خطوة بخطوة وأمثلة التعليمات البرمجية المصدر لـ C# لمساعدتك على فهم كيفية تعيين نص بديل ومربعات محيطة للصور، ونقل العناصر داخل المستند، وإضافة علامات إلى الصور.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي حول وضع علامات على الصور في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: قبل البدء، تأكد من أنك قمت بإعداد بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتكوين مشروعك للرجوع إليه.

#### س: كيف يمكنني فتح مستند PDF موجود والوصول إلى محتواه المميز باستخدام Aspose.PDF لـ .NET؟

ج: يوفر البرنامج التعليمي أمثلة على التعليمات البرمجية المصدر لـ C# التي توضح كيفية فتح مستند PDF موجود باستخدام Aspose.PDF لـ .NET والوصول إلى محتواه المميز لمزيد من المعالجة.

#### س: ما هو الغرض من تعيين نص بديل ومربعات محيطة للصور في مستند PDF؟

ج: يؤدي تعيين نص بديل ومربعات محيطة للصور إلى تحسين إمكانية الوصول من خلال توفير نص وصفي للصور وتحديد تخطيطها وموضعها داخل المستند. تعتبر هذه المعلومات ضرورية لقارئات الشاشة والتقنيات المساعدة الأخرى.

#### س: كيف يمكنني تعيين عنوان مستند PDF بعلامات باستخدام Aspose.PDF لـ .NET؟

ج: يشتمل البرنامج التعليمي على أمثلة التعليمات البرمجية المصدر لـ C# التي توضح كيفية تعيين عنوان لمستند PDF ذي علامات باستخدام Aspose.PDF لـ .NET.

#### س: ماذا تتضمن عملية نقل العناصر داخل مستند PDF؟

ج: يتضمن نقل العناصر داخل مستند PDF تغيير العنصر الأصلي لعنصر معين. ستتعلم في هذا البرنامج التعليمي كيفية نقل عنصر Span إلى عنصر فقرة محدد داخل الجدول.

#### س: كيف يمكنني حفظ مستند PDF المعدل بعد إضافة العلامات وإجراء التعديلات على الصور؟

 ج: بمجرد إضافة العلامات، وتعيين نص بديل، وتعيين المربعات المحيطة، وإجراء تعديلات على مستند PDF، يمكنك استخدام أمثلة التعليمات البرمجية المصدر C# المتوفرة لحفظ مستند PDF المعدل باستخدام`Save()` طريقة.

#### س: ما هو الغرض من نموذج التعليمات البرمجية المصدر الموجود في البرنامج التعليمي؟

ج: يعد نموذج التعليمات البرمجية المصدر بمثابة مرجع عملي لتنفيذ علامات الصور ومعالجتها باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الرمز كنقطة بداية وتعديله ليناسب متطلباتك المحددة.

#### س: هل يمكنني تطبيق هذه التقنيات على أنواع أخرى من العناصر في مستند PDF، وليس الصور فقط؟

ج: نعم، يمكن تكييف التقنيات الموضحة في هذا البرنامج التعليمي للعمل مع أنواع مختلفة من العناصر داخل مستند PDF. يمكنك تطبيق مبادئ مماثلة لوضع علامات على العناصر الأخرى ومعالجتها مثل النص والجداول والمزيد.

#### س: كيف يمكنني التحقق من امتثال PDF/UA لمستند PDF المعدل؟

 ج: يوفر البرنامج التعليمي أمثلة على التعليمات البرمجية المصدر لـ C# التي توضح كيفية التحقق من صحة توافق PDF/UA لمستند PDF المعدل باستخدام`Validate()` طريقة وإنشاء تقرير XML.

#### س: ما هي الميزات الأخرى التي يقدمها Aspose.PDF for .NET للعمل مع مستندات PDF؟

ج: يوفر Aspose.PDF for .NET نطاقًا واسعًا من الميزات للعمل مع مستندات PDF، بما في ذلك معالجة النص وإدراج الصور وإنشاء الجدول وإدارة حقل النموذج والتوقيعات الرقمية والتعليقات التوضيحية والمزيد. راجع الوثائق والموارد الرسمية لمزيد من الاستكشاف.