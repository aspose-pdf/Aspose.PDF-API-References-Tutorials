---
title: إنشاء عنصر هيكل الملاحظة
linktitle: إنشاء عنصر هيكل الملاحظة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإنشاء عناصر ملاحظات منظمة في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-tagged-pdf/create-note-structure-element/
---
في هذا البرنامج التعليمي، سنزودك بدليل خطوة بخطوة حول كيفية إنشاء عنصر بنية ملاحظة في مستند PDF باستخدام Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى المحددة في Aspose.PDF، يمكنك إضافة ملاحظات منظمة إلى مستند PDF الخاص بك.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Visual Studio مع إطار عمل .NET.
2. مكتبة Aspose.PDF لـ .NET.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع جديد في Visual Studio وقم بإضافة مرجع إلى مكتبة Aspose.PDF لـ .NET. يمكنك تنزيل المكتبة من موقع Aspose الرسمي وتثبيتها على جهازك.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

في ملف التعليمات البرمجية C# الخاص بك، قم باستيراد مساحات الأسماء المطلوبة للوصول إلى الفئات والأساليب التي يوفرها Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## الخطوة 3: إنشاء مستند PDF وعناصر الملاحظة المنظمة

استخدم الكود التالي لإنشاء مستند PDF وإضافة عناصر منظمة للملاحظة:

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

يقوم هذا الرمز بإنشاء مستند PDF فارغ وإضافة عناصر ملاحظة منظمة إلى الفقرة. يتم إنشاء كل ملاحظة باستخدام الطرق التي يوفرها Aspose.PDF.

## الخطوة 4: حفظ مستند PDF

استخدم الكود التالي لحفظ مستند PDF:

```csharp
document. Save(outFile);
```

يحفظ هذا الرمز مستند PDF مع العناصر المنظمة للملاحظة في ملف محدد.

### نموذج التعليمات البرمجية المصدر لإنشاء عنصر هيكل ملاحظة باستخدام Aspose.PDF لـ .NET 

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// إنشاء مستند PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// إضافة عنصر الفقرة
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// إضافة عنصر الملاحظة
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// إضافة عنصر الملاحظة
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// إضافة عنصر الملاحظة
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// يجب طرح استثناء - Aspose.Pdf.Tagged.TaggedException: عنصر البنية بالمعرف='note_002' موجود بالفعل
//note3.SetId("note_002");
// لا يتوافق المستند الناتج مع PDF/UA في حالة استخدام ClearId() لعنصر بنية الملاحظة
//note3.ClearId();
// حفظ وثيقة PDF ذات العلامات
document.Save(outFile);
// التحقق من توافق PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء عناصر بنية الملاحظة في مستند PDF باستخدام Aspose.PDF لـ .NET. تتيح لك عناصر الملاحظات المنظمة إضافة معلومات منظمة إضافية إلى مستند PDF الخاص بك.

### الأسئلة الشائعة

#### س: ما هو الغرض من إنشاء عناصر بنية الملاحظة في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: يتيح لك إنشاء عناصر بنية الملاحظة في مستند PDF باستخدام Aspose.PDF لـ .NET إضافة ملاحظات منظمة إلى محتوى المستند. يمكن أن توفر هذه الملاحظات سياقًا إضافيًا أو تفسيرات أو مراجع لأجزاء محددة من المحتوى.

#### س: كيف تساعد مكتبة Aspose.PDF في إنشاء عناصر بنية الملاحظة في مستند PDF؟

ج: Aspose.PDF for .NET هي مكتبة قوية توفر وظائف لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي، يتم استخدام ميزات بنية المحتوى المميزة بالمكتبة لإنشاء عناصر ملاحظة منظمة داخل محتوى مستند PDF.

#### س: ما هي المتطلبات الأساسية لإنشاء عناصر بنية الملاحظة في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ، تأكد من تثبيت Visual Studio مع إطار عمل .NET وأن مكتبة Aspose.PDF الخاصة بـ .NET مشار إليها في مشروعك.

#### س: كيف يقوم كود C# المقدم بإنشاء عناصر بنية الملاحظة في محتوى مستند PDF؟

ج: يوضح الكود كيفية إنشاء مستند PDF، وتحديد العناصر المنظمة للملاحظة، وإضافتها إلى فقرة. يتم إنشاء كل ملاحظة باستخدام الأساليب التي يوفرها Aspose.PDF، مما يسمح لك بدمج الملاحظات المنظمة في المحتوى.

#### س: هل يمكنني تخصيص محتوى وخصائص عناصر بنية الملاحظة التي أقوم بإنشائها؟

ج: نعم، يمكنك تخصيص محتوى وخصائص عناصر بنية الملاحظة باستخدام الطرق والخصائص التي توفرها مكتبة Aspose.PDF. يعرض الكود كيفية تعيين النص ومعرف عناصر الملاحظة، ولكن يمكنك تخصيصها بشكل أكبر حسب الحاجة.

#### س: كيف يتم إنشاء العلاقة الهرمية بين عناصر بنية الملاحظة ومحتوى الوثيقة؟

 ج: يتم إنشاء العلاقة الهرمية عن طريق إضافة عناصر بنية الملاحظة كعناصر فرعية لعناصر منظمة أخرى، مثل الفقرات. في التعليمات البرمجية، يتم إلحاق عناصر الملاحظة بعنصر فقرة باستخدام التابع`AppendChild` طريقة.

#### س: هل يمكنني تعيين معرفات فريدة لتدوين عناصر البنية؟

ج: نعم، يمكنك تعيين معرفات فريدة لملاحظة عناصر البنية باستخدام`SetId` طريقة. يوضح الكود كيفية تعيين معرفات عناصر الملاحظة على قيم فريدة.

#### س: ماذا يحدث إذا حاولت تعيين معرف مكرر لعنصر بنية الملاحظة؟

ج: ستؤدي محاولة تعيين معرف مكرر لعنصر بنية الملاحظة إلى حدوث استثناء. يتضمن الكود الموجود في البرنامج التعليمي تعليقًا يوضح هذا السيناريو.

#### س: كيف يمكنني ضمان التوافق مع PDF/UA عند إنشاء عناصر هيكل الملاحظة؟

 ج: يوضح الكود الموجود في البرنامج التعليمي كيفية التحقق من صحة توافق PDF/UA باستخدام ملف`Validate` طريقة. من خلال التحقق من صحة المستند مقابل معيار PDF/UA، يمكنك التأكد من أن عناصر بنية الملاحظة المضافة تلتزم بإرشادات إمكانية الوصول.

#### س: هل يمكنني استخدام هذا الأسلوب لإضافة عناصر بنية الملاحظة إلى مستند PDF موجود؟

ج: نعم، يمكنك تعديل النهج المقدم لإضافة عناصر بنية الملاحظة إلى مستند PDF موجود. بدلاً من إنشاء مستند جديد، يمكنك تحميل المستند الحالي باستخدام Aspose.PDF ثم اتباع خطوات مماثلة لإلحاق عناصر الملاحظة.
