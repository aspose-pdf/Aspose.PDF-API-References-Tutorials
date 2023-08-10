---
title: أضف عنصر البنية إلى العنصر
linktitle: أضف عنصر البنية إلى العنصر
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 20
url: /ar/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
في هذا البرنامج التعليمي ، سنزودك بدليل تفصيلي حول كيفية إضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح لك بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى المميزة لـ Aspose.PDF ، يمكنك إنشاء هيكل هرمي في مستند PDF الخاص بك.

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

## الخطوة 3: إنشاء مستند PDF وتحديد العناصر المهيكلة

استخدم الكود التالي لإنشاء مستند PDF وتحديد العناصر المهيكلة:

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

ينشئ هذا الرمز مستند PDF فارغًا ويضيف عناصر منظمة مثل الفقرات والمسافات. يتم إنشاء كل عنصر من عناصر الهيكل باستخدام الطرق التي يوفرها Aspose.PDF.

## الخطوة 4: حفظ مستند PDF

استخدم الكود التالي لحفظ مستند PDF:

```csharp
document. Save(outFile);
```

يحفظ هذا الرمز مستند PDF مع العناصر المهيكلة في ملف محدد.

### نموذج التعليمات البرمجية المصدر لـ Add Structure Element Into Element باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// مستند الإنشاء والحصول على محتوى بتنسيق PDF ذي علامات
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// تحديد العنوان ولغة الطبيعة للوثيقة
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
// حفظ وثيقة PDF الموسومة
document.Save(outFile);
// التحقق من توافق PDF / UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET. باستخدام ميزات بنية المحتوى المحددة في Aspose.PDF ، يمكنك إنشاء هيكل هرمي في مستند PDF الخاص بك ، مما يسهل إدارة المحتوى والتنقل خلاله.

### التعليمات

#### س: ما هو الغرض من إضافة عنصر بنية إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: إضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF for .NET يسمح لك بإنشاء هيكل هرمي داخل محتوى المستند. يعزز هذا الهيكل الهرمي تنظيم المحتوى والتنقل فيه ، مما يسهل إدارة عناصر محددة والوصول إليها.

#### س: كيف تساعد مكتبة Aspose.PDF في إضافة عناصر هيكلية إلى وثيقة PDF؟

ج: Aspose.PDF for .NET مكتبة قوية توفر إمكانيات لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي ، يتم الاستفادة من ميزات بنية المحتوى المميزة الخاصة بالمكتبة لإنشاء عناصر هيكلية وإلحاقها بمحتوى مستند PDF.

#### س: ما هي المتطلبات الأساسية لإضافة عناصر بنية إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ ، تأكد من تثبيت Visual Studio مع إطار عمل .NET وأن لديك مكتبة Aspose.PDF لـ .NET المشار إليها في مشروعك.

#### س: كيف ينشئ كود C # المقدم عناصر هيكلية ويلحقها بمحتوى مستند PDF؟

ج: يوضح الكود كيفية إنشاء مستند PDF ، وتعريف عنصر البنية الجذرية ، وإلحاق العديد من العناصر الهيكلية مثل الفقرات والمسافات إليه. يتم إنشاء كل عنصر منظم باستخدام طرق يوفرها Aspose.PDF ، مما يسمح لك ببناء هيكل هرمي.

#### س: هل يمكنني تخصيص أنواع عناصر الهيكل التي أقوم بإلحاقها بمستند PDF؟

ج: نعم ، يمكنك تخصيص أنواع عناصر الهيكل من خلال استكشاف الطرق المختلفة التي توفرها مكتبة Aspose.PDF. تعرض الكود الفقرات والمسافات كأمثلة ، ولكن يمكنك إنشاء وإلحاق أنواع أخرى من العناصر المهيكلة حسب الحاجة.

#### س: كيف يمكنني تحديد العلاقة الهرمية بين عناصر الهيكل المضافة؟

 ج: يتم تحديد العلاقة الهرمية بين عناصر الهيكل بالترتيب الذي قمت بإلحاقها بعناصرها الأصلية. في الكود ، يتم إنشاء العلاقات بين الوالدين والطفل باستخدام`AppendChild` طريقة.

#### س: ما هي فوائد إنشاء هيكل هرمي في مستند PDF؟

ج: يؤدي إنشاء هيكل هرمي في مستند PDF إلى تحسين إمكانية الوصول والتنقل والتنظيم. يسمح للتقنيات المساعدة بتفسير محتوى المستند ونقله بشكل أفضل ، مما يجعله أكثر سهولة في الاستخدام للأفراد ذوي الإعاقة.

#### س: كيف يمكنني التحقق من توافق PDF / UA بعد إضافة عناصر الهيكل؟

 ج: يوضح الكود المقدم في البرنامج التعليمي كيفية التحقق من توافق PDF / UA باستخدام`Validate` طريقة. من خلال التحقق من صحة الوثيقة مقابل معيار PDF / UA ، يمكنك التأكد من أن عناصر الهيكل المضافة تتوافق مع إرشادات إمكانية الوصول.

#### س: هل يمكنني استخدام هذا الأسلوب لإضافة عناصر هيكلية إلى مستند PDF موجود؟

ج: نعم ، يمكنك تعديل الأسلوب المتوفر لإضافة عناصر هيكلية إلى مستند PDF موجود. بدلاً من إنشاء مستند جديد ، يمكنك تحميل المستند الحالي باستخدام Aspose.PDF ثم اتباع خطوات مماثلة لإلحاق عناصر الهيكل.