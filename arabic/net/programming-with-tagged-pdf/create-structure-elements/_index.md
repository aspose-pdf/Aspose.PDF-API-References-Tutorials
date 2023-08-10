---
title: تكوين عناصر الهيكل
linktitle: تكوين عناصر الهيكل
second_title: Aspose.PDF لمرجع .NET API
description: في هذا البرنامج التعليمي ، ستتعلم كيفية استخدام Aspose.PDF for .NET لإنشاء عناصر هيكلية في مستند PDF بعلامات تمييز.
type: docs
weight: 60
url: /ar/net/programming-with-tagged-pdf/create-structure-elements/
---
تستخدم التعليمات البرمجية المصدر C # التالية Aspose.PDF لـ .NET لإنشاء عناصر البنية. اتبع الخطوات أدناه لفهم كيفية عمل الكود.

## الخطوة 1: استيراد المكتبات الضرورية

```csharp
using Aspose.Pdf;
```

## الخطوة 2: تحديد دليل المستندات الخاصة بك

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

تأكد من تحديد المسار الصحيح إلى دليل المستندات الخاص بك.

## الخطوة 3: قم بإنشاء مستند PDF

```csharp
Document document = new Document();
```

نقوم بإنشاء كائن مستند جديد يمثل مستند PDF.

## الخطوة 4: احصل على محتوى للعمل مع TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

نقوم باسترداد المحتوى الموسوم لوثيقة PDF. سيسمح لنا هذا بمعالجة العناصر الهيكلية.

## الخطوة 5: حدد عنوان المستند ولغته

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

قمنا بتعيين عنوان ولغة مستند PDF الذي تم وضع علامة عليه. هذا يحسن الوصول إلى المستند.

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

نقوم بإنشاء عناصر هيكلية مختلفة لتجميع المحتوى في مستند PDF.

## الخطوة 7: إنشاء عناصر بنية الفقرة

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

نقوم بإنشاء عناصر هيكلية على مستوى الكتلة للفقرات والعناوين. يوضح المثال أعلاه إنشاء رأس من المستوى 1.

## الخطوة 8: إنشاء عناصر هيكل مستوى مضمنة

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

نقوم بإنشاء عناصر هيكل مستوى مضمن لأجزاء النص التي تظهر داخل فقرة أو عنوان.

## الخطوة 9: إنشاء عناصر هيكل العمل الفني

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

نقوم بإنشاء عناصر هيكلية للرسوم التوضيحية والصيغ الرياضية الموجودة في المستند.

## الخطوة 10: احفظ مستند PDF الذي تم وضع علامة عليه

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

نحفظ مستند PDF الموسوم بعناصر الهيكل التي تم إنشاؤها.

### نموذج التعليمات البرمجية المصدر لـ Create Structure Elements باستخدام Aspose.PDF for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بإنشاء مستند PDF
Document document = new Document();
// الحصول على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// تعيين العنوان واللغة للوثيقة
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
// تكوين عناصر هيكل مستوى كتلة النص
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// تكوين عناصر هيكل نص مضمن المستوى
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
// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "StructureElements.pdf");

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية استخدام Aspose.PDF لـ .NET لإنشاء عناصر هيكلية في مستند PDF ذي علامات تمييز. تساعد العناصر الهيكلية في تحسين إمكانية الوصول إلى المستندات وتنظيم المحتوى بطريقة هادفة. يمكنك الآن استخدام هذه المعرفة لإنشاء مستندات PDF منظمة وسهلة التنقل.

### التعليمات

#### س: ما هو الغرض من إنشاء عناصر هيكلية في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: يؤدي إنشاء عناصر هيكلية في مستند PDF باستخدام Aspose.PDF for .NET إلى تحسين إمكانية الوصول إلى محتوى المستند وتنظيمه. توفر عناصر الهيكل بنية هرمية تعمل على تحسين التنقل والدلالات والتوافق مع التقنيات المساعدة.

#### س: كيف ينشئ كود C # المقدم عناصر بنية في مستند PDF؟

ج: يوضح مثال الكود كيفية إنشاء أنواع مختلفة من عناصر البنية ، بما في ذلك عناصر التجميع (مثل الأجزاء والأقسام و divs) ، وعناصر مستوى الكتلة (مثل الفقرات والعناوين) ، والعناصر المضمنة (الامتداد ، والاقتباس ، والملاحظة ) ، وعناصر العمل الفني (مثل الأشكال والصيغ). تساعد عناصر الهيكل هذه في تنظيم المحتوى.

####  س: لماذا من المهم تعيين عنوان المستند ولغته باستخدام`SetTitle` and `SetLanguage` methods?

 ج: تحديد عنوان المستند ولغته باستخدام`SetTitle` و`SetLanguage`أساليب تحسين إمكانية الوصول إلى المستندات ودلالاتها. يوفر العنوان وصفًا موجزًا للغرض من المستند ، بينما تعمل سمة اللغة على تحسين العرض وإمكانية الوصول الخاصين باللغة.

####  س: كيف يتم تجميع العناصر مثل`PartElement` and `SectElement`, contribute to the structure of the PDF document?

ج: تُنشئ عناصر التجميع هيكلًا هرميًا داخل مستند PDF ، مما يسمح لك بالتنظيم المنطقي للمحتوى ذي الصلة وتجميعه. هذا يعزز التنقل ويوفر بنية واضحة للمستخدمين.

#### س: ما هي عناصر البنية على مستوى الكتلة وعلى مستوى المضمنة ، وكيف تختلف؟

ج: تمثل عناصر البنية على مستوى الكتلة كتلًا أكبر من المحتوى ، مثل الفقرات والعناوين ، بينما تمثل العناصر على مستوى السطر أجزاء من النص داخل فقرة أو عنوان ، مثل الامتدادات والاقتباسات والملاحظات. إنها تساعد في تحديد التسلسل الهرمي وعلاقات المحتوى.

####  س: كيف تعمل عناصر هيكل العمل الفني ، مثل`FigureElement` and `FormulaElement`, contribute to the document?

ج: تسمح لك عناصر بنية العمل الفني بإضافة الرسوم التوضيحية والأشكال والصيغ الرياضية إلى المستند. أنها توفر طريقة منظمة لتضمين المحتوى المرئي والرياضي.

#### س: هل يمكنني استخدام تقنيات مماثلة لإنشاء أنواع أخرى من عناصر البنية ، مثل القوائم أو الجداول أو التعليقات التوضيحية؟

ج: نعم ، يمكنك استخدام تقنيات مماثلة لإنشاء أنواع أخرى من عناصر البنية مثل القوائم والجداول والتعليقات التوضيحية والمراجع والمزيد. يوفر Aspose.PDF مجموعة واسعة من طرق إنشاء عنصر الهيكل.

####  س: كيف يتم حفظ مستند PDF المميز بعلامات باستخدام امتداد`Save` method ensure the preservation of structure elements?

 ج: إن`Save` تقوم الطريقة بحفظ مستند PDF مع عناصر البنية التي تم إنشاؤها ، مما يضمن الاحتفاظ بالهيكل الهرمي والدلالي للمستند لإمكانية الوصول والتنقل.

#### س: ما الفوائد التي تجلبها عناصر الهيكل إلى مستندات PDF من حيث إمكانية الوصول والتوافق مع التقنيات المساعدة؟

ج: تعمل عناصر الهيكل على تحسين إمكانية الوصول من خلال توفير بنية ذات مغزى ودلالات للمستند. يسمح هذا للتقنيات المساعدة مثل برامج قراءة الشاشة بتفسير محتوى المستند ونقله بشكل أكثر فاعلية للمستخدمين ذوي الاحتياجات الخاصة.

#### س: كيف يمكنني تخصيص أنواع مختلفة من عناصر البنية ودمجها في مستندات PDF الخاصة بي؟

ج: يمكنك دمج عناصر الهيكل وتخصيصها باستخدام طرق الإنشاء المناسبة التي يوفرها Aspose.PDF. جرب العناصر المختلفة وخصائصها لإنشاء مستند PDF منظم جيدًا.