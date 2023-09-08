---
title: أضف عنصر الهيكل إلى العنصر
linktitle: أضف عنصر الهيكل إلى العنصر
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإضافة عنصر هيكلي إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 20
url: /ar/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
في هذا البرنامج التعليمي، سنزودك بدليل خطوة بخطوة حول كيفية إضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى المحددة في Aspose.PDF، يمكنك إنشاء هيكل هرمي في مستند PDF الخاص بك.

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

يقوم هذا الكود بإنشاء مستند PDF فارغ وإضافة عناصر منظمة مثل الفقرات والامتدادات. يتم إنشاء كل عنصر هيكلي باستخدام الطرق التي يوفرها Aspose.PDF.

## الخطوة 4: حفظ مستند PDF

استخدم الكود التالي لحفظ مستند PDF:

```csharp
document. Save(outFile);
```

يحفظ هذا الرمز مستند PDF مع العناصر المنظمة في ملف محدد.

### نموذج التعليمات البرمجية المصدر لإضافة عنصر هيكلي إلى عنصر باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// إنشاء مستند والحصول على محتوى Pdf ذو علامة
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// تحديد العنوان واللغة الطبيعية للمستند
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
// حفظ وثيقة PDF ذات العلامات
document.Save(outFile);
// التحقق من توافق PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET. باستخدام ميزات بنية المحتوى المحددة في Aspose.PDF، يمكنك إنشاء هيكل هرمي في مستند PDF الخاص بك، مما يسهل إدارة المحتوى والتنقل خلاله.

### الأسئلة الشائعة

#### س: ما هو الغرض من إضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: تتيح لك إضافة عنصر هيكل إلى عنصر في مستند PDF باستخدام Aspose.PDF لـ .NET إنشاء هيكل هرمي داخل محتوى المستند. يعمل هذا الهيكل الهرمي على تحسين تنظيم المحتوى والتنقل فيه، مما يسهل إدارة عناصر محددة والوصول إليها.

#### س: كيف تساعد مكتبة Aspose.PDF في إضافة عناصر هيكلية إلى مستند PDF؟

ج: Aspose.PDF for .NET هي مكتبة قوية توفر إمكانيات لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي، يتم الاستفادة من ميزات بنية المحتوى المميزة بالمكتبة لإنشاء عناصر هيكل وإلحاقها بمحتوى مستند PDF.

#### س: ما هي المتطلبات الأساسية لإضافة عناصر هيكلية إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ، تأكد من تثبيت Visual Studio مع إطار عمل .NET وأن مكتبة Aspose.PDF الخاصة بـ .NET مشار إليها في مشروعك.

#### س: كيف يقوم كود C# المقدم بإنشاء عناصر هيكلية وإلحاقها بمحتوى مستند PDF؟

ج: يوضح الكود كيفية إنشاء مستند PDF، وتحديد عنصر البنية الجذرية، وإلحاق عناصر منظمة مختلفة مثل الفقرات والامتدادات به. يتم إنشاء كل عنصر منظم باستخدام الأساليب التي يوفرها Aspose.PDF، مما يسمح لك ببناء هيكل هرمي.

#### س: هل يمكنني تخصيص أنواع عناصر البنية التي أقوم بإلحاقها بمستند PDF؟

ج: نعم، يمكنك تخصيص أنواع عناصر البنية من خلال استكشاف الطرق المختلفة التي توفرها مكتبة Aspose.PDF. تعرض التعليمات البرمجية الفقرات والامتدادات كأمثلة، ولكن يمكنك إنشاء وإلحاق أنواع أخرى من العناصر المنظمة حسب الحاجة.

#### س: كيف يمكنني تحديد العلاقة الهرمية بين عناصر البنية المضافة؟

 ج: يتم تحديد العلاقة الهرمية بين عناصر البنية بالترتيب الذي تقوم به بإلحاقها بالعناصر الأصلية الخاصة بها. في التعليمات البرمجية، يتم إنشاء العلاقات بين الوالدين والطفل باستخدام`AppendChild` طريقة.

#### س: ما هي فوائد إنشاء هيكل هرمي في مستند PDF؟

ج: يؤدي إنشاء هيكل هرمي في مستند PDF إلى تحسين إمكانية الوصول إليه والتنقل فيه وتنظيمه. فهو يسمح للتقنيات المساعدة بتفسير محتوى المستند ونقله بشكل أفضل، مما يجعله أكثر سهولة في الاستخدام للأفراد ذوي الإعاقة.

#### س: كيف يمكنني التحقق من توافق PDF/UA بعد إضافة عناصر الهيكل؟

 ج: يوضح الكود الموجود في البرنامج التعليمي كيفية التحقق من صحة توافق PDF/UA باستخدام ملف`Validate` طريقة. من خلال التحقق من صحة المستند مقابل معيار PDF/UA، يمكنك التأكد من أن عناصر البنية المضافة تتوافق مع إرشادات إمكانية الوصول.

#### س: هل يمكنني استخدام هذا الأسلوب لإضافة عناصر هيكلية إلى مستند PDF موجود؟

ج: نعم، يمكنك تعديل النهج المقدم لإضافة عناصر هيكلية إلى مستند PDF موجود. بدلاً من إنشاء مستند جديد، يمكنك تحميل المستند الموجود باستخدام Aspose.PDF ثم اتباع خطوات مماثلة لإلحاق عناصر البنية.