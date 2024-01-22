---
title: إنشاء عناصر الهيكل
linktitle: إنشاء عناصر الهيكل
second_title: Aspose.PDF لمرجع .NET API
description: في هذا البرنامج التعليمي، ستتعلم كيفية استخدام Aspose.PDF لـ .NET لإنشاء عناصر هيكلية في وثيقة PDF ذات علامات.
type: docs
weight: 60
url: /ar/net/programming-with-tagged-pdf/create-structure-elements/
---
يستخدم كود مصدر C# التالي Aspose.PDF لـ .NET لإنشاء عناصر البنية. اتبع الخطوات أدناه لفهم كيفية عمل الكود.

## الخطوة 1: استيراد المكتبات اللازمة

```csharp
using Aspose.Pdf;
```

## الخطوة 2: تحديد دليل المستندات الخاصة بك

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

تأكد من تحديد المسار الصحيح لدليل المستندات الخاص بك.

## الخطوة 3: إنشاء مستند PDF

```csharp
Document document = new Document();
```

نقوم بإنشاء كائن مستند جديد يمثل مستند PDF.

## الخطوة 4: احصل على محتوى للعمل مع TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

نقوم باسترداد المحتوى الموسوم لوثيقة PDF. هذا سيسمح لنا بالتعامل مع العناصر الهيكلية.

## الخطوة 5: تعيين عنوان المستند واللغة

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

قمنا بتعيين عنوان ولغة مستند PDF الذي تم وضع علامة عليه. يؤدي هذا إلى تحسين إمكانية الوصول إلى المستند.

## الخطوة 6: إنشاء عناصر التجميع

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

نقوم بإنشاء عناصر هيكلية مختلفة لتجميع المحتوى في وثيقة PDF.

## الخطوة 7: إنشاء عناصر هيكل الفقرة

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

نقوم بإنشاء عناصر هيكلية على مستوى الكتلة للفقرات والعناوين. يوضح المثال أعلاه إنشاء رأس المستوى 1.

## الخطوة 8: إنشاء عناصر بنية المستوى المضمنة

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

نقوم بإنشاء عناصر بنية المستوى المضمنة لأجزاء النص التي تظهر داخل الفقرة أو العنوان.

## الخطوة 9: إنشاء عناصر هيكل العمل الفني

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

نقوم بإنشاء عناصر هيكلية للرسوم التوضيحية والصيغ الرياضية الموجودة في الوثيقة.

## الخطوة 10: احفظ مستند PDF الذي تم وضع علامة عليه

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

نقوم بحفظ وثيقة PDF ذات العلامات مع عناصر البنية التي تم إنشاؤها.

### نموذج التعليمات البرمجية المصدر لإنشاء عناصر البنية باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مستند PDF
Document document = new Document();
// احصل على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// قم بتعيين العنوان واللغة لـ Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// إنشاء عناصر التجميع
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// إنشاء عناصر بنية على مستوى كتلة النص
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// إنشاء عناصر بنية على مستوى النص
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// إنشاء عناصر هيكل التوضيح
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// الأساليب قيد التطوير
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// حفظ وثيقة PDF ذات العلامات
document.Save(dataDir + "StructureElements.pdf");

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.PDF لـ .NET لإنشاء عناصر هيكلية في وثيقة PDF ذات علامات. تساعد العناصر الهيكلية على تحسين إمكانية الوصول إلى المستندات وتنظيم المحتوى بطريقة مفيدة. يمكنك الآن استخدام هذه المعرفة لإنشاء مستندات PDF منظمة وسهلة التنقل.

### الأسئلة الشائعة

#### س: ما هو الغرض من إنشاء عناصر هيكلية في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: يؤدي إنشاء عناصر هيكلية في مستند PDF باستخدام Aspose.PDF لـ .NET إلى تحسين إمكانية الوصول إلى محتوى المستند وتنظيمه. توفر عناصر البنية بنية هرمية تعمل على تحسين التنقل والدلالات والتوافق مع التقنيات المساعدة.

#### س: كيف يقوم كود C# المقدم بإنشاء عناصر هيكلية في مستند PDF؟

ج: يوضح مثال التعليمات البرمجية كيفية إنشاء أنواع مختلفة من عناصر البنية، بما في ذلك عناصر التجميع (مثل الأجزاء والأقسام وdivs)، وعناصر مستوى الكتلة (مثل الفقرات والعناوين)، وعناصر المستوى المضمّن (الامتداد، والاقتباس، والملاحظة )، وعناصر العمل الفني (مثل الأشكال والصيغ). تساعد عناصر البنية هذه في تنظيم المحتوى.

####  س: لماذا من المهم تعيين عنوان المستند ولغته باستخدام`SetTitle` and `SetLanguage` methods?

 ج: قم بتعيين عنوان المستند ولغته باستخدام`SetTitle` و`SetLanguage`تعمل الأساليب على تحسين إمكانية الوصول إلى المستندات ودلالاتها. يوفر العنوان وصفًا موجزًا للغرض من المستند، بينما تعمل سمة اللغة على تحسين العرض وإمكانية الوصول الخاصة باللغة.

####  س: كيف يتم تجميع العناصر، مثل`PartElement` and `SectElement`, contribute to the structure of the PDF document?

ج: تقوم عناصر التجميع بإنشاء هيكل هرمي داخل مستند PDF، مما يسمح لك بتنظيم المحتوى ذي الصلة وتجميعه بشكل منطقي. وهذا يعزز التنقل ويوفر بنية واضحة للمستخدمين.

#### س: ما هي عناصر البنية على مستوى الكتلة والمستوى المضمن، وكيف تختلف؟

ج: تمثل عناصر البنية على مستوى الكتلة كتلًا أكبر من المحتوى، مثل الفقرات والعناوين، بينما تمثل عناصر المستوى المضمن أجزاء من النص داخل فقرة أو عنوان، مثل الامتدادات وعلامات الاقتباس والملاحظات. فهي تساعد في تحديد التسلسل الهرمي وعلاقات المحتوى.

####  س: كيف يمكن لعناصر هيكل العمل الفني، مثل`FigureElement` and `FormulaElement`, contribute to the document?

ج: تتيح لك عناصر هيكل العمل الفني إضافة الرسوم التوضيحية والأشكال والصيغ الرياضية إلى المستند. أنها توفر طريقة منظمة لتضمين المحتوى المرئي والرياضي.

#### س: هل يمكنني استخدام تقنيات مشابهة لإنشاء أنواع أخرى من عناصر البنية، مثل القوائم أو الجداول أو التعليقات التوضيحية؟

ج: نعم، يمكنك استخدام تقنيات مشابهة لإنشاء أنواع أخرى من عناصر البنية مثل القوائم والجداول والتعليقات التوضيحية والمراجع والمزيد. يوفر Aspose.PDF نطاقًا واسعًا من طرق إنشاء عناصر البنية.

####  س: كيف يمكن حفظ مستند PDF الذي تم وضع علامة عليه باستخدام ملف`Save` method ensure the preservation of structure elements?

 ج: ال`Save` تقوم هذه الطريقة بحفظ مستند PDF مع عناصر البنية التي تم إنشاؤها، مما يضمن الحفاظ على البنية الهرمية والدلالية للمستند من أجل إمكانية الوصول والتنقل.

#### س: ما هي الفوائد التي تجلبها عناصر البنية إلى مستندات PDF من حيث إمكانية الوصول والتوافق مع التقنيات المساعدة؟

ج: تعمل عناصر البنية على تحسين إمكانية الوصول من خلال توفير بنية ودلالات ذات معنى للمستند. يتيح ذلك للتقنيات المساعدة، مثل قارئات الشاشة، تفسير ونقل محتوى المستند بشكل أكثر فعالية للمستخدمين ذوي الإعاقة.

#### س: كيف يمكنني تخصيص ودمج أنواع مختلفة من عناصر البنية في مستندات PDF الخاصة بي؟

ج: يمكنك دمج عناصر البنية وتخصيصها باستخدام طرق الإنشاء المناسبة التي يوفرها Aspose.PDF. قم بتجربة عناصر مختلفة وخصائصها لإنشاء مستند PDF منظم وجيد التنظيم.