---
title: وضع علامة على الصورة في ملف PDF الموجود
linktitle: وضع علامة على الصورة في ملف PDF الموجود
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية وضع علامات على صورة في ملف PDF موجود باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لإضافة علامات إلى الصور.
type: docs
weight: 210
url: /ar/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
في هذا البرنامج التعليمي المفصل، سنشرح لك خطوة بخطوة التعليمات البرمجية المصدرية بلغة C# المتوفرة لوضع علامات على صورة في ملف PDF موجود باستخدام Aspose.PDF لـ .NET. اتبع الإرشادات أدناه لفهم كيفية إضافة علامات إلى صورة في ملف PDF.

## الخطوة 1: إعداد البيئة

قبل أن تبدأ، تأكد من تكوين بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن هذا تثبيت مكتبة Aspose.PDF وتكوين مشروعك للإشارة إليها.

## الخطوة 2: افتح مستند PDF الموجود

في هذه الخطوة، سوف نقوم بفتح مستند PDF موجود باستخدام Aspose.PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// مسارات الملفات المدخلة والمخرجة
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// افتح المستند
Document document = new Document(inFile);
```

لقد فتحنا مستند PDF الموجود باستخدام Aspose.PDF.

## الخطوة 3: الحصول على المحتوى المميز وعناصر البنية الجذرية

سنحصل الآن على المحتوى المميز لمستند PDF وعناصر البنية الجذرية المقابلة.

```csharp
// احصل على محتوى مميز وعناصر هيكل الجذر
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

لقد حصلنا على المحتوى المميز لمستند PDF وعناصر البنية الجذرية المقابلة.

## الخطوة 4: تعيين عنوان مستند PDF المُوسوم

الآن دعونا نحدد عنوان مستند PDF المُوسوم.

```csharp
// قم بتحديد عنوان مستند PDF المُوسوم
taggedContent.SetTitle("Document with images");
```

لقد قمنا بتعيين العنوان لمستند PDF المُوسوم.

## الخطوة 5: تعيين نصوص بديلة ومربع محيط للصورة

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

لقد قمنا بتعيين نص بديل ومربع محدد لكل عنصر صورة في مستند PDF.

## الخطوة 6: نقل عنصر Span إلى الفقرة

الآن دعنا ننقل عنصر Span إلى الفقرة.

```csharp
// نقل عنصر Span إلى الفقرة (البحث عن امتداد وفقرات غير صحيحة في TD الأول)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// نقل عنصر Span في الفقرة
spanElement.ChangeParentElement(paragraph);
```

لقد نقلنا عنصر Span إلى الفقرة المحددة.

## الخطوة 7: حفظ مستند PDF المعدّل

الآن بعد أن أجرينا التغييرات اللازمة، سنقوم بحفظ مستند PDF المعدل.

```csharp
// حفظ مستند PDF
document. Save(outFile);
```

لقد قمنا بحفظ مستند PDF المعدل في الدليل المحدد.

### عينة من كود المصدر لصورة العلامة في ملف PDF موجود باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// فتح المستند
Document document = new Document(inFile);

// يحصل على محتوى مميز وعناصر بنية الجذر
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// تعيين عنوان لمستند pdf المُوسوم
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

// نقل عنصر النطاق إلى الفقرة (البحث عن النطاق والفقرة الخاطئة في أول TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// نقل عنصر النطاق إلى الفقرة
spanElement.ChangeParentElement(paragraph);

// حفظ المستند
document.Save(outFile);

//التحقق من توافق PDF/UA مع مستندنا
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية وضع علامات على صورة في ملف PDF موجود باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام Aspose.PDF لإضافة علامات وإجراء تعديلات على الصور في مستندات PDF الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو الهدف الرئيسي من هذا البرنامج التعليمي حول وضع علامات على الصور في ملف PDF موجود باستخدام Aspose.PDF لـ .NET؟

ج: الهدف الأساسي من هذا البرنامج التعليمي هو إرشادك خلال عملية وضع علامات على صورة داخل مستند PDF موجود باستخدام Aspose.PDF لـ .NET. يوفر البرنامج التعليمي تعليمات خطوة بخطوة وأمثلة لأكواد المصدر C# لمساعدتك على فهم كيفية تعيين نص بديل ومربعات حدود للصور، ونقل العناصر داخل المستند، وإضافة علامات إلى الصور.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي حول وضع علامات على الصور في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: قبل البدء، تأكد من إعداد بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن هذا تثبيت مكتبة Aspose.PDF وتكوين مشروعك للإشارة إليها.

#### س: كيف يمكنني فتح مستند PDF موجود والوصول إلى محتواه المميز باستخدام Aspose.PDF لـ .NET؟

ج: يوفر البرنامج التعليمي أمثلة لأكواد المصدر C# التي توضح كيفية فتح مستند PDF موجود باستخدام Aspose.PDF لـ .NET والوصول إلى محتواه المميز لمزيد من المعالجة.

#### س: ما هو الغرض من تعيين نص بديل ومربعات حدود للصور في مستند PDF؟

أ: إن تخصيص نص بديل ومربعات حدود للصور يعزز إمكانية الوصول إليها من خلال توفير نص وصفي للصور وتحديد تخطيطها وموقعها داخل المستند. وهذه المعلومات بالغة الأهمية لقارئي الشاشة وتقنيات المساعدة الأخرى.

#### س: كيف يمكنني تعيين عنوان مستند PDF مميز باستخدام Aspose.PDF لـ .NET؟

أ: يتضمن البرنامج التعليمي أمثلة لأكواد المصدر C# التي توضح كيفية تعيين عنوان مستند PDF المُوسوم باستخدام Aspose.PDF لـ .NET.

#### س: ما هي عملية نقل العناصر داخل مستند PDF؟

ج: يتضمن نقل العناصر داخل مستند PDF تغيير العنصر الأساسي لعنصر معين. في هذا البرنامج التعليمي، ستتعلم كيفية نقل عنصر Span إلى عنصر Paragraph محدد داخل جدول.

#### س: كيف يمكنني حفظ مستند PDF المعدل بعد إضافة العلامات وإجراء التعديلات على الصور؟

 أ: بمجرد إضافة العلامات وتعيين نص بديل وتعيين مربعات تحديد وإجراء تعديلات على مستند PDF، يمكنك استخدام أمثلة التعليمات البرمجية المصدرية C# المقدمة لحفظ مستند PDF المعدل باستخدام`Save()` طريقة.

#### س: ما هو الغرض من رمز المصدر النموذجي المقدم في البرنامج التعليمي؟

ج: يعمل كود المصدر النموذجي كمرجع عملي لتطبيق وسم الصور ومعالجتها باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الكود كنقطة بداية وتعديله ليناسب متطلباتك المحددة.

#### س: هل يمكنني تطبيق هذه التقنيات على أنواع أخرى من العناصر في مستند PDF، وليس فقط الصور؟

ج: نعم، يمكن تكييف التقنيات الموضحة في هذا البرنامج التعليمي للعمل مع أنواع مختلفة من العناصر داخل مستند PDF. يمكنك تطبيق مبادئ مماثلة لوضع العلامات على عناصر أخرى مثل النصوص والجداول والمزيد والتلاعب بها.

#### س: كيف يمكنني التحقق من توافق PDF/UA للمستند PDF المعدل؟

 أ: يوفر البرنامج التعليمي أمثلة لأكواد المصدر C# التي توضح كيفية التحقق من توافق PDF/UA لمستند PDF المعدل باستخدام`Validate()` الطريقة وإنشاء تقرير XML.

#### س: ما هي الميزات الأخرى التي يوفرها Aspose.PDF لـ .NET للعمل مع مستندات PDF؟

ج: يوفر Aspose.PDF for .NET مجموعة واسعة من الميزات للعمل مع مستندات PDF، بما في ذلك معالجة النصوص، وإدراج الصور، وإنشاء الجداول، وإدارة حقول النماذج، والتوقيعات الرقمية، والتعليقات التوضيحية، والمزيد. راجع الوثائق والموارد الرسمية لمزيد من الاستكشاف.