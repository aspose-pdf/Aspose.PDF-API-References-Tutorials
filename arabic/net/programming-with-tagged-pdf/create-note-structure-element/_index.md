---
title: تكوين عنصر بنية الملاحظة
linktitle: تكوين عنصر بنية الملاحظة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإنشاء عناصر ملاحظات منظمة في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-tagged-pdf/create-note-structure-element/
---
في هذا البرنامج التعليمي ، سنزودك بدليل تفصيلي حول كيفية إنشاء عنصر بنية ملاحظة في مستند PDF باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح لك بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى المحددة في Aspose.PDF ، يمكنك إضافة ملاحظات منظمة إلى مستند PDF الخاص بك.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio مثبت مع .NET framework.
2. مكتبة Aspose.PDF لـ .NET.

## الخطوة 1: إعداد المشروع

للبدء ، أنشئ مشروعًا جديدًا في Visual Studio وأضف مرجعًا إلى Aspose.PDF لمكتبة .NET. يمكنك تنزيل المكتبة من موقع Aspose الرسمي وتثبيتها على جهازك.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

في ملف كود C # الخاص بك ، قم باستيراد مساحات الأسماء المطلوبة للوصول إلى الفئات والطرق التي يوفرها Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## الخطوة 3: إنشاء مستند PDF وملاحظة العناصر الهيكلية

استخدم الكود التالي لإنشاء مستند PDF وإضافة عناصر منظمة للملاحظات:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

ينشئ هذا الرمز مستند PDF فارغًا ويضيف عناصر ملاحظة منظمة إلى فقرة. يتم إنشاء كل ملاحظة باستخدام الطرق التي يوفرها Aspose.PDF.

## الخطوة 4: حفظ مستند PDF

استخدم الكود التالي لحفظ مستند PDF:

```csharp
document. Save(outFile);
```

يحفظ هذا الرمز مستند PDF مع عناصر بنية الملاحظة في ملف محدد.

### نموذج التعليمات البرمجية المصدر لـ Create Note Structure Element باستخدام Aspose.PDF for .NET 

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// قم بإنشاء مستند PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// أضف عنصر فقرة
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// إضافة عنصر ملاحظة
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// إضافة عنصر ملاحظة
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// إضافة عنصر ملاحظة
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// يجب طرح استثناء - Aspose.Pdf.Tagged.TaggedException: عنصر الهيكل بالمعرف = 'note_002' موجود بالفعل
//note3.SetId ("note_002") ؛
// المستند الناتج لا يتوافق مع PDF / UA إذا تم استخدام ClearId () لعنصر بنية الملاحظة
//note3.ClearId () ،
// حفظ وثيقة PDF الموسومة
document.Save(outFile);
// التحقق من توافق PDF / UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إنشاء عناصر بنية الملاحظات في مستند PDF باستخدام Aspose.PDF for .NET. تسمح لك عناصر الملاحظات المنظمة بإضافة معلومات منظمة إضافية إلى مستند PDF الخاص بك.

### التعليمات

#### س: ما هو الغرض من إنشاء عناصر بنية الملاحظات في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: إنشاء عناصر هيكل الملاحظات في مستند PDF باستخدام Aspose.PDF for .NET يسمح لك بإضافة ملاحظات منظمة إلى محتوى المستند. يمكن أن توفر هذه الملاحظات سياقًا إضافيًا أو تفسيرات أو مراجع لأجزاء معينة من المحتوى.

#### س: كيف تساعد مكتبة Aspose.PDF في إنشاء عناصر هيكل الملاحظات في وثيقة PDF؟

ج: Aspose.PDF for .NET مكتبة قوية توفر وظائف لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي ، يتم استخدام ميزات بنية المحتوى المميزة الخاصة بالمكتبة لإنشاء عناصر ملاحظات منظمة داخل محتوى مستند PDF.

#### س: ما هي المتطلبات الأساسية لإنشاء عناصر بنية الملاحظات في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ ، تأكد من تثبيت Visual Studio مع إطار عمل .NET وأن لديك مكتبة Aspose.PDF لـ .NET المشار إليها في مشروعك.

#### س: كيف ينشئ كود C # المقدم عناصر بنية الملاحظة في محتوى مستند PDF؟

ج: يوضح الكود كيفية إنشاء مستند PDF وتحديد عناصر هيكل الملاحظات وإضافتها إلى فقرة. يتم إنشاء كل ملاحظة باستخدام طرق يوفرها Aspose.PDF ، مما يسمح لك بدمج الملاحظات المنظمة في المحتوى.

#### س: هل يمكنني تخصيص محتوى وخصائص عناصر بنية الملاحظة التي أقوم بإنشائها؟

ج: نعم ، يمكنك تخصيص محتوى وخصائص عناصر بنية الملاحظة باستخدام الأساليب والخصائص التي توفرها مكتبة Aspose.PDF. يعرض الكود كيفية تعيين النص ومعرف عناصر الملاحظة ، ولكن يمكنك تخصيصها بشكل أكبر حسب الحاجة.

#### س: كيف يتم إنشاء العلاقة الهرمية بين عناصر بنية الملاحظة ومحتوى المستند؟

 ج: يتم إنشاء العلاقة الهرمية عن طريق إضافة عناصر بنية الملاحظة كأبناء لعناصر منظمة أخرى ، مثل الفقرات. في الكود ، يتم إلحاق عناصر الملاحظة بعنصر فقرة باستخدام`AppendChild` طريقة.

#### س: هل يمكنني تعيين معرفات فريدة لعناصر بنية الملاحظات؟

ج: نعم ، يمكنك تعيين معرفات فريدة لعناصر بنية الملاحظات باستخدام`SetId` طريقة. يوضح الكود كيفية تعيين معرفات عناصر الملاحظة على قيم فريدة.

#### س: ماذا يحدث إذا حاولت تعيين معرف مكرر لعنصر بنية الملاحظة؟

ج: ستؤدي محاولة تعيين معرف مكرر لعنصر بنية الملاحظة إلى استثناء. يتضمن الكود المقدم في البرنامج التعليمي تعليقًا يوضح هذا السيناريو.

#### س: كيف يمكنني ضمان التوافق مع PDF / UA عند إنشاء عناصر بنية الملاحظة؟

 ج: يوضح الكود المقدم في البرنامج التعليمي كيفية التحقق من توافق PDF / UA باستخدام`Validate` طريقة. من خلال التحقق من صحة المستند مقابل معيار PDF / UA ، يمكنك التأكد من أن عناصر هيكل الملاحظات المضافة تلتزم بإرشادات إمكانية الوصول.

#### س: هل يمكنني استخدام هذا الأسلوب لإضافة عناصر هيكل الملاحظات إلى مستند PDF موجود؟

ج: نعم ، يمكنك تعديل الطريقة المتوفرة لإضافة عناصر بنية الملاحظة إلى مستند PDF موجود. بدلاً من إنشاء مستند جديد ، يمكنك تحميل المستند الحالي باستخدام Aspose.PDF ثم اتباع خطوات مماثلة لإلحاق عناصر الملاحظة.
