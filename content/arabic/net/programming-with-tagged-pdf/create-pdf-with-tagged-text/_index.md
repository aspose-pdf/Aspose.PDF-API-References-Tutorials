---
title: إنشاء PDF مع النص الموسوم
linktitle: إنشاء PDF مع النص الموسوم
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإنشاء ملف PDF يحتوي على نص مميز باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 50
url: /ar/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
في هذا البرنامج التعليمي، سنزودك بدليل خطوة بخطوة حول كيفية إنشاء مستند PDF يحتوي على نص مميز باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى ذات العلامات في Aspose.PDF، يمكنك إضافة نص ذو علامات تمييز إلى مستند PDF الخاص بك.

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

## الخطوة 3: إنشاء مستند PDF بنص مميز

استخدم الكود التالي لإنشاء مستند PDF يحتوي على نص مميز:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// أضف المزيد من الفقرات هنا

// احفظ مستند PDF
document.Save(dataDir + "PDFwithTagText.pdf");
```

ينشئ هذا الرمز مستند PDF فارغًا ويضيف نصًا مميزًا باستخدام الطرق التي يوفرها Aspose.PDF. يمكنك إضافة عناصر نصية أخرى ذات علامات تمييز مثل العناوين والفقرات باستخدام الطرق المناسبة.

### نموذج التعليمات البرمجية المصدر لإنشاء PDF مع نص مميز باستخدام Aspose.PDF لـ .NET 
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
// إنشاء عناصر بنية على مستوى كتلة النص
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// حفظ وثيقة PDF
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مستند PDF يحتوي على نص مميز باستخدام Aspose.PDF لـ .NET. تتيح لك ميزات بنية المحتوى المميزة في Aspose.PDF إمكانية هيكلة وتنظيم النص الخاص بك لتحسين إمكانية الوصول والدلالات.

### الأسئلة الشائعة

#### س: ما هو الغرض من إنشاء مستند PDF يحتوي على نص مميز باستخدام Aspose.PDF لـ .NET؟

ج: يتيح لك إنشاء مستند PDF يحتوي على نص مميز باستخدام Aspose.PDF لـ .NET هيكلة محتوى النص الخاص بك وتنظيمه داخل مستند PDF. يضيف النص ذو العلامات معنى دلاليًا ويحسن إمكانية الوصول للمستخدمين، وخاصة أولئك الذين يستخدمون التقنيات المساعدة.

#### س: كيف يساعد Aspose.PDF في إنشاء مستند PDF بنص مميز؟

ج: Aspose.PDF for .NET هي مكتبة قوية توفر وظائف لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي، يتم استخدام ميزات بنية المحتوى المميزة بالمكتبة لإضافة نص منظم وذو معنى دلالي إلى مستند PDF.

#### س: ما هي المتطلبات الأساسية لإنشاء مستند PDF يحتوي على نص مميز باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ، تأكد من تثبيت Visual Studio مع إطار عمل .NET وأن مكتبة Aspose.PDF الخاصة بـ .NET مشار إليها في مشروعك.

#### س: كيف يقوم كود C# المقدم بإنشاء مستند PDF يحتوي على نص مميز؟

ج: يوضح مثال التعليمات البرمجية كيفية إنشاء مستند PDF، وتحديد عناصر النص المتنوعة ذات العلامات (مثل الرؤوس والفقرات)، وإضافتها إلى محتوى المستند. يتم تحقيق ذلك باستخدام ميزات بنية المحتوى الموسومة التي يوفرها Aspose.PDF.

#### س: كيف يمكنني تخصيص عناصر النص ذات العلامات، مثل الرؤوس والفقرات؟

 ج: يمكنك تخصيص عناصر النص ذات العلامات باستخدام الطرق المناسبة، مثل`CreateHeaderElement` و`CreateParagraphElement` ، وتعيين خصائص مثل`ActualText` لتوفير نص ودلالات ذات معنى.

#### س: هل يمكنني إضافة عناصر نصية أخرى ذات علامات تمييز، مثل القوائم أو الروابط، باستخدام تقنيات مشابهة؟

ج: نعم، يمكنك إضافة عناصر نصية أخرى ذات علامات تمييز مثل القوائم أو الروابط أو غيرها من الهياكل المخصصة باستخدام تقنيات مشابهة. يوفر Aspose.PDF طرقًا متنوعة لإنشاء أنواع مختلفة من المحتوى ذي العلامات، مما يسمح لك بتحسين دلالات المستند.

####  س: كيف`SetTitle` method contribute to the PDF document's tagged text?

 ج: ال`SetTitle` تحدد هذه الطريقة عنوان محتوى مستند PDF الذي تم وضع علامة عليه، مما يوفر وصفًا موجزًا لغرض المستند أو موضوعه. تساعد هذه المعلومات المستخدمين على فهم سياق النص الذي تم وضع علامة عليه.

#### س: كيف يؤدي استخدام النص المميز إلى تحسين إمكانية الوصول إلى مستندات PDF؟

ج: يضيف النص ذو العلامات معنى دلاليًا إلى المستند، مما يجعله في متناول المستخدمين ذوي الإعاقة أو أولئك الذين يستخدمون التقنيات المساعدة. يمكن لقارئات الشاشة والأجهزة المساعدة الأخرى تفسير النص المميز وتقديمه لتحسين تجربة المستخدم.

####  س: كيف`SetLanguage` method enhance the tagged text in a PDF document?

 ج: ال`SetLanguage`تقوم الطريقة بتعيين سمة اللغة للمحتوى المميز بعلامة PDF. ويساعد ذلك في الإشارة إلى اللغة التي تمت بها كتابة النص المميز، مما يعمل على تحسين إمكانية الوصول وتمكين العرض المناسب للغة معينة.

#### س: هل من الممكن إضافة عناصر أخرى، مثل الصور أو الوسائط المتعددة، إلى جانب النص الموسوم باستخدام تقنيات مماثلة؟

ج: نعم، يمكنك إضافة عناصر أخرى مثل الصور أو الوسائط المتعددة أو التعليقات التوضيحية إلى جانب النص المميز باستخدام تقنيات مشابهة. يقدم Aspose.PDF مجموعة واسعة من الميزات لدمج أنواع مختلفة من المحتوى داخل المستند.