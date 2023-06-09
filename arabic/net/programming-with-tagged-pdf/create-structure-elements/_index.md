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
// إنشاء مستند PDF
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
//تكوين عناصر هيكل نص مضمن المستوى
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
