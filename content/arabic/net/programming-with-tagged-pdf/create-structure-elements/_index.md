---
title: إنشاء عناصر الهيكل
linktitle: إنشاء عناصر الهيكل
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: في هذا البرنامج التعليمي، سوف تتعلم كيفية استخدام Aspose.PDF لـ .NET لإنشاء عناصر هيكلية في مستند PDF مُوسم.
type: docs
weight: 60
url: /ar/net/programming-with-tagged-pdf/create-structure-elements/
---
يستخدم الكود المصدر C# التالي ملف Aspose.PDF لـ .NET لإنشاء عناصر البنية. اتبع الخطوات التالية لفهم كيفية عمل الكود.

## الخطوة 1: استيراد المكتبات الضرورية

```csharp
using Aspose.Pdf;
```

## الخطوة 2: قم بتحديد دليل مستنداتك

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

تأكد من تحديد المسار الصحيح إلى دليل المستندات الخاص بك.

## الخطوة 3: إنشاء مستند PDF

```csharp
Document document = new Document();
```

نقوم بإنشاء كائن مستند جديد يمثل مستند PDF.

## الخطوة 4: الحصول على محتوى للعمل مع TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

نقوم باسترجاع المحتوى المُوسوم لمستند PDF. وهذا سيسمح لنا بالتعامل مع العناصر الهيكلية.

## الخطوة 5: تعيين عنوان المستند واللغة

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

لقد قمنا بتعيين عنوان ولغة مستند PDF المُوسوم. وهذا يحسن إمكانية الوصول إلى المستند.

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

## الخطوة 8: إنشاء عناصر هيكل المستوى المضمن

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

نقوم بإنشاء عناصر هيكلية على مستوى الخط لأجزاء النص التي تظهر داخل فقرة أو عنوان.

## الخطوة 9: إنشاء عناصر هيكل العمل الفني

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

نقوم بإنشاء العناصر الهيكلية للرسوم التوضيحية والصيغ الرياضية الموجودة في المستند.

## الخطوة 10: احفظ مستند PDF المُوسوم

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

نقوم بحفظ مستند PDF المُوسوم بعناصر البنية التي تم إنشاؤها.

### نموذج لمصدر التعليمات البرمجية لإنشاء عناصر الهيكل باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مستند PDF
Document document = new Document();
// احصل على محتوى للعمل باستخدام TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// تعيين العنوان واللغة لـDocumnet
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
// إنشاء عناصر هيكلية على مستوى كتلة النص
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// إنشاء عناصر بنية نصية على مستوى السطر
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// إنشاء عناصر هيكلية توضيحية
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
// حفظ مستند PDF المُوسوم
document.Save(dataDir + "StructureElements.pdf");

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.PDF لـ .NET لإنشاء عناصر هيكلية في مستند PDF مُوسَم. تساعد العناصر الهيكلية في تحسين إمكانية الوصول إلى المستند وتنظيم المحتوى بطريقة مفيدة. يمكنك الآن استخدام هذه المعرفة لإنشاء مستندات PDF منظمة وسهلة التنقل.

### الأسئلة الشائعة

#### س: ما هو الغرض من إنشاء عناصر الهيكل في مستند PDF باستخدام Aspose.PDF لـ .NET؟

أ: إن إنشاء عناصر هيكلية في مستند PDF باستخدام Aspose.PDF لـ .NET يعزز إمكانية الوصول إلى محتوى المستند وتنظيمه. توفر عناصر الهيكلية هيكلًا هرميًا يحسن التنقل والدلالات والتوافق مع التقنيات المساعدة.

#### س: كيف يقوم الكود C# المقدم بإنشاء عناصر هيكلية في مستند PDF؟

ج: يوضح مثال التعليمات البرمجية كيفية إنشاء أنواع مختلفة من عناصر البنية، بما في ذلك عناصر التجميع (مثل الأجزاء والأقسام والأقسام الفرعية)، وعناصر مستوى الكتلة (مثل الفقرات والعناوين)، وعناصر مستوى السطر (الامتداد والاقتباس والملاحظة)، وعناصر العمل الفني (مثل الأشكال والصيغ). تساعد عناصر البنية هذه في تنظيم المحتوى.

####  س: لماذا من المهم تعيين عنوان المستند واللغة باستخدام`SetTitle` and `SetLanguage` methods?

 أ: ضبط عنوان المستند واللغة باستخدام`SetTitle` و`SetLanguage`تعمل الأساليب على تحسين إمكانية الوصول إلى المستند ودلالاته. يوفر العنوان وصفًا موجزًا لغرض المستند، بينما تعمل سمة اللغة على تحسين العرض وإمكانية الوصول الخاصة باللغة.

####  س: كيف يتم تجميع العناصر، مثل`PartElement` and `SectElement`, contribute to the structure of the PDF document?

أ: تعمل عناصر التجميع على إنشاء هيكل هرمي داخل مستند PDF، مما يسمح لك بتنظيم المحتوى المرتبط وتجميعه منطقيًا. وهذا يعزز التنقل ويوفر هيكلًا واضحًا للمستخدمين.

#### س: ما هي عناصر البنية على مستوى الكتلة وعناصر البنية على المستوى المضمن، وكيف تختلف؟

أ: تمثل عناصر البنية على مستوى الكتلة كتلًا أكبر من المحتوى، مثل الفقرات والعناوين، بينما تمثل العناصر على مستوى السطر أجزاء من النص داخل فقرة أو عنوان، مثل الفواصل والاقتباسات والملاحظات. وهي تساعد في تحديد التسلسل الهرمي والعلاقات بين المحتوى.

####  س: كيف يتم بناء العناصر في العمل الفني، مثل`FigureElement` and `FormulaElement`, contribute to the document?

أ: تتيح لك عناصر بنية العمل الفني إضافة الرسوم التوضيحية والأشكال والصيغ الرياضية إلى المستند. وهي توفر طريقة منظمة لتضمين المحتوى المرئي والرياضي.

#### س: هل يمكنني استخدام تقنيات مماثلة لإنشاء أنواع أخرى من عناصر الهيكل، مثل القوائم أو الجداول أو التعليقات التوضيحية؟

ج: نعم، يمكنك استخدام تقنيات مماثلة لإنشاء أنواع أخرى من عناصر البنية مثل القوائم والجداول والتعليقات التوضيحية والمراجع والمزيد. يوفر Aspose.PDF مجموعة واسعة من طرق إنشاء عناصر البنية.

####  س: كيف يتم حفظ مستند PDF المُوسوم باستخدام`Save` method ensure the preservation of structure elements?

 أ: ال`Save` تحفظ الطريقة مستند PDF مع عناصر الهيكل التي تم إنشاؤها، مما يضمن الحفاظ على الهيكل الهرمي والدلالي للمستند من أجل إمكانية الوصول إليه والتنقل فيه.

#### س: ما هي الفوائد التي تجلبها عناصر البنية إلى مستندات PDF من حيث إمكانية الوصول والتوافق مع التقنيات المساعدة؟

أ: تعمل عناصر البنية على تعزيز إمكانية الوصول من خلال توفير بنية ودلالات مفيدة للمستند. وهذا يسمح لتقنيات المساعدة مثل برامج قراءة الشاشة بتفسير محتوى المستند ونقله بشكل أكثر فعالية للمستخدمين ذوي الإعاقة.

#### س: كيف يمكنني تخصيص ودمج أنواع مختلفة من عناصر الهيكل في مستندات PDF الخاصة بي؟

ج: يمكنك دمج عناصر البنية وتخصيصها باستخدام طرق الإنشاء المناسبة التي يوفرها Aspose.PDF. يمكنك تجربة عناصر مختلفة وخصائصها لإنشاء مستند PDF منظم وذو بنية جيدة.