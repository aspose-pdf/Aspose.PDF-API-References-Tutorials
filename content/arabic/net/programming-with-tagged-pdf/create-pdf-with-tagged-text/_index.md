---
title: إنشاء ملف PDF مع نص مميز
linktitle: إنشاء ملف PDF مع نص مميز
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لإنشاء ملف PDF يحتوي على نص مُوسم باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 50
url: /ar/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
في هذا البرنامج التعليمي، سنقدم لك دليلًا خطوة بخطوة حول كيفية إنشاء مستند PDF بنص مُوسم باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى المُوسم في Aspose.PDF، يمكنك إضافة نص مُوسم إلى مستند PDF الخاص بك.

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

## الخطوة 3: إنشاء مستند PDF بنص مُوسم

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

// حفظ مستند PDF
document.Save(dataDir + "PDFwithTagText.pdf");
```

يقوم هذا الكود بإنشاء مستند PDF فارغ ويضيف نصًا مميزًا باستخدام الطرق التي يوفرها Aspose.PDF. يمكنك إضافة عناصر نص مميزة أخرى مثل العناوين والفقرات باستخدام الطرق المناسبة.

### عينة من كود المصدر لإنشاء ملف PDF بنص مُوسم باستخدام Aspose.PDF لـ .NET 
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
// إنشاء عناصر هيكلية على مستوى كتلة النص
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
// حفظ مستند PDF
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مستند PDF بنص مُوسم باستخدام Aspose.PDF for .NET. تتيح لك ميزات بنية المحتوى المُوسم في Aspose.PDF هيكلة النص وتنظيمه لتحسين إمكانية الوصول إليه ودلالاته.

### الأسئلة الشائعة

#### س: ما هو الغرض من إنشاء مستند PDF بنص مُوسم باستخدام Aspose.PDF لـ .NET؟

أ: إن إنشاء مستند PDF يحتوي على نص مُوسم باستخدام Aspose.PDF for .NET يسمح لك بهيكلة وتنظيم محتوى النص داخل مستند PDF. يضيف النص المُوسم معنى دلاليًا ويحسن إمكانية الوصول للمستخدمين، وخاصة أولئك الذين يستخدمون التقنيات المساعدة.

#### س: كيف يساعد Aspose.PDF في إنشاء مستند PDF يحتوي على نص مميز؟

ج: Aspose.PDF for .NET هي مكتبة قوية توفر وظائف لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي، يتم استخدام ميزات بنية المحتوى المميزة للمكتبة لإضافة نص منظم وذو معنى دلالي إلى مستند PDF.

#### س: ما هي المتطلبات الأساسية لإنشاء مستند PDF يحتوي على نص مُوسم باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ، تأكد من تثبيت Visual Studio مع إطار عمل .NET ومن وجود مكتبة Aspose.PDF لـ .NET مذكورة في مشروعك.

#### س: كيف يقوم الكود C# المقدم بإنشاء مستند PDF يحتوي على نص مميز؟

ج: يوضح مثال التعليمات البرمجية كيفية إنشاء مستند PDF، وتحديد عناصر نصية مميزة (مثل العناوين والفقرات)، وإضافتها إلى محتوى المستند. ويتم تحقيق ذلك باستخدام ميزات بنية المحتوى المميز التي يوفرها Aspose.PDF.

#### س: كيف يمكنني تخصيص عناصر النص المميزة، مثل العناوين والفقرات؟

 أ: يمكنك تخصيص عناصر النص المُوسومة باستخدام الطرق المناسبة، مثل`CreateHeaderElement` و`CreateParagraphElement` ، وتعيين خصائص مثل`ActualText` لتوفير نص ودلالات ذات معنى.

#### س: هل يمكنني إضافة عناصر نصية أخرى مميزة، مثل القوائم أو الروابط، باستخدام تقنيات مماثلة؟

ج: نعم، يمكنك إضافة عناصر نصية أخرى مميزة مثل القوائم أو الروابط أو غيرها من الهياكل المخصصة باستخدام تقنيات مماثلة. يوفر Aspose.PDF طرقًا مختلفة لإنشاء أنواع مختلفة من المحتوى المميز، مما يسمح لك بتعزيز دلالات المستند.

#### س: كيف يتم ذلك؟`SetTitle` method contribute to the PDF document's tagged text?

 أ: ال`SetTitle` تحدد الطريقة عنوان المحتوى المميز في مستند PDF، مما يوفر وصفًا موجزًا لغرض المستند أو موضوعه. تساعد هذه المعلومات المستخدمين على فهم سياق النص المميز.

#### س: كيف يساعد استخدام النص المميز على تحسين إمكانية الوصول إلى مستندات PDF؟

أ: يضيف النص المُوسوم معنى دلاليًا إلى المستند، مما يجعله أكثر سهولة في الوصول إليه للمستخدمين ذوي الإعاقة أو أولئك الذين يستخدمون التقنيات المساعدة. يمكن لقارئات الشاشة والأجهزة المساعدة الأخرى تفسير النص المُوسوم وتقديمه لتحسين تجربة المستخدم.

#### س: كيف يتم ذلك؟`SetLanguage` method enhance the tagged text in a PDF document?

 أ: ال`SetLanguage` تحدد الطريقة سمة اللغة لمحتوى مستند PDF المُوسوم. يساعد هذا في تحديد اللغة التي كُتب بها النص المُوسوم، مما يحسن إمكانية الوصول إليه ويمكّن من عرض اللغة بشكل صحيح.

#### س: هل من الممكن إضافة عناصر أخرى، مثل الصور أو الوسائط المتعددة، إلى جانب النص المميز باستخدام تقنيات مماثلة؟

ج: نعم، يمكنك إضافة عناصر أخرى مثل الصور أو الوسائط المتعددة أو التعليقات التوضيحية إلى جانب النص المُوسوم باستخدام تقنيات مماثلة. يوفر Aspose.PDF مجموعة واسعة من الميزات لدمج أنواع مختلفة من المحتوى داخل المستند.