---
title: إضافة عنصر هيكلي إلى العنصر
linktitle: إضافة عنصر هيكلي إلى العنصر
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لإضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 20
url: /ar/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
في هذا البرنامج التعليمي، سنزودك بدليل خطوة بخطوة حول كيفية إضافة عنصر هيكلي إلى عنصر في مستند PDF باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات هيكل المحتوى المميزة في Aspose.PDF، يمكنك إنشاء هيكل هرمي في مستند PDF الخاص بك.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Visual Studio مع إطار عمل .NET.
2. مكتبة Aspose.PDF لـ .NET.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع جديد في Visual Studio وأضف مرجعًا إلى مكتبة Aspose.PDF for .NET. يمكنك تنزيل المكتبة من موقع Aspose الرسمي وتثبيتها على جهازك.

## الخطوة 2: استيراد المساحات الاسمية الضرورية

في ملف الكود C# الخاص بك، قم باستيراد المساحات الأساسية المطلوبة للوصول إلى الفئات والطرق التي يوفرها Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## الخطوة 3: إنشاء مستند PDF وتحديد العناصر المنظمة

استخدم الكود التالي لإنشاء مستند PDF وتحديد العناصر المنظمة:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

يقوم هذا الكود بإنشاء مستند PDF فارغ وإضافة عناصر منظمة مثل الفقرات والامتدادات. يتم إنشاء كل عنصر من عناصر الهيكل باستخدام الطرق التي يوفرها Aspose.PDF.

## الخطوة 4: حفظ مستند PDF

استخدم الكود التالي لحفظ مستند PDF:

```csharp
document. Save(outFile);
```

يحفظ هذا الكود مستند PDF مع العناصر المنظمة في ملف محدد.

### عينة من كود المصدر لإضافة عنصر هيكلي إلى عنصر باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
//إنشاء مستند والحصول على محتوى Pdf المميز
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// تعيين لغة العنوان والطبيعة للمستند
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// الحصول على عنصر بنية الجذر (عنصر بنية المستند)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// حفظ مستند PDF المُوسوم
document.Save(outFile);
// التحقق من توافق PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET. باستخدام ميزات هيكل المحتوى المميزة في Aspose.PDF، يمكنك إنشاء هيكل هرمي في مستند PDF الخاص بك، مما يجعل إدارة المحتوى والتنقل عبره أسهل.

### الأسئلة الشائعة

#### س: ما هو الغرض من إضافة عنصر هيكلي إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: إن إضافة عنصر هيكلي إلى عنصر في مستند PDF باستخدام Aspose.PDF for .NET يسمح لك بإنشاء هيكل هرمي داخل محتوى المستند. يعزز هذا الهيكل الهرمي تنظيم المحتوى والتنقل فيه، مما يجعل إدارة عناصر معينة والوصول إليها أسهل.

#### س: كيف تساعد مكتبة Aspose.PDF في إضافة عناصر الهيكل إلى مستند PDF؟

ج: Aspose.PDF for .NET هي مكتبة قوية توفر إمكانيات لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي، يتم الاستفادة من ميزات بنية المحتوى المميزة للمكتبة لإنشاء عناصر بنية وإضافتها إلى محتوى مستند PDF.

#### س: ما هي المتطلبات الأساسية لإضافة عناصر الهيكل إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ، تأكد من تثبيت Visual Studio مع إطار عمل .NET ومن وجود مكتبة Aspose.PDF لـ .NET مذكورة في مشروعك.

#### س: كيف يقوم الكود C# المقدم بإنشاء عناصر الهيكل وإضافتها إلى محتوى مستند PDF؟

ج: يوضح الكود كيفية إنشاء مستند PDF، وتحديد عنصر هيكلي جذري، وإضافة عناصر هيكلية مختلفة مثل الفقرات والامتدادات إليه. يتم إنشاء كل عنصر هيكلي باستخدام الأساليب التي يوفرها Aspose.PDF، مما يسمح لك ببناء هيكل هرمي.

#### س: هل يمكنني تخصيص أنواع عناصر الهيكل التي أقوم بإضافتها إلى مستند PDF؟

ج: نعم، يمكنك تخصيص أنواع عناصر الهيكل من خلال استكشاف الطرق المختلفة التي توفرها مكتبة Aspose.PDF. يعرض الكود الفقرات والامتدادات كأمثلة، ولكن يمكنك إنشاء وإضافة أنواع أخرى من العناصر الهيكلية حسب الحاجة.

#### س: كيف يمكنني تحديد العلاقة الهرمية بين عناصر الهيكل المضافة؟

 أ: يتم تحديد العلاقة الهرمية بين عناصر البنية من خلال الترتيب الذي تلحقها به بعناصرها الأصلية. في الكود، يتم إنشاء علاقات الوالد والطفل باستخدام`AppendChild` طريقة.

#### س: ما هي فوائد إنشاء هيكل هرمي في مستند PDF؟

أ: إن إنشاء هيكل هرمي في مستند PDF يعزز إمكانية الوصول إليه والتنقل فيه وتنظيمه. كما يسمح لتقنيات المساعدة بتفسير محتوى المستند ونقله بشكل أفضل، مما يجعله أكثر سهولة في الاستخدام للأشخاص ذوي الإعاقة.

#### س: كيف يمكنني التحقق من توافق PDF/UA بعد إضافة عناصر الهيكل؟

أ: يوضح الكود المقدم في البرنامج التعليمي كيفية التحقق من توافق PDF/UA باستخدام`Validate` الطريقة. من خلال التحقق من صحة المستند وفقًا لمعيار PDF/UA، يمكنك التأكد من أن عناصر البنية المضافة تتوافق مع إرشادات إمكانية الوصول.

#### س: هل يمكنني استخدام هذا النهج لإضافة عناصر هيكلية إلى مستند PDF موجود؟

ج: نعم، يمكنك تعديل النهج المقدم لإضافة عناصر البنية إلى مستند PDF موجود. فبدلاً من إنشاء مستند جديد، يمكنك تحميل المستند الموجود باستخدام Aspose.PDF ثم اتباع خطوات مماثلة لإضافة عناصر البنية.