---
title: إنشاء ملف PDF مع صورة مميزة
linktitle: إنشاء ملف PDF مع صورة مميزة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لإنشاء ملف PDF مع صورة مُوسومة باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 40
url: /ar/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
في هذا البرنامج التعليمي، سنقدم لك دليلًا خطوة بخطوة حول كيفية إنشاء مستند PDF بصورة مُوسومة باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى المُوسومة في Aspose.PDF، يمكنك إضافة صور مُوسومة إلى مستند PDF الخاص بك.

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

## الخطوة 3: إنشاء مستند PDF مع صورة مُوسومة

استخدم الكود التالي لإنشاء مستند PDF يحتوي على صورة مميزة:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

يقوم هذا الكود بإنشاء مستند PDF فارغ وإضافة صورة مُوسومة باستخدام الطرق التي يوفرها Aspose.PDF. يتم تحديد الصورة باستخدام نص بديل وعنوان وعلامة.

## الخطوة 4: حفظ مستند PDF

استخدم الكود التالي لحفظ مستند PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

يحفظ هذا الكود مستند PDF الذي يحتوي على الصورة المحددة في ملف محدد.

### عينة من كود المصدر لإنشاء ملف PDF مع صورة مميزة باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// أضف صورة بدقة 300 نقطة في البوصة (افتراضيًا)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// حفظ مستند PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مستند PDF بصورة مُوسومة باستخدام Aspose.PDF لـ .NET. تضيف الصور المُوسومة معلومات إضافية منظمة إلى مستند PDF الخاص بك.

### الأسئلة الشائعة

#### س: ما هو الغرض من إنشاء مستند PDF مع صورة مميزة باستخدام Aspose.PDF لـ .NET؟

أ: يتيح لك إنشاء مستند PDF يحتوي على صورة مُوسومة باستخدام Aspose.PDF for .NET إضافة صور مُوسومة إلى محتوى المستند. توفر الصور المُوسومة معلومات منظمة، مثل النص البديل والعناوين، مما يعزز إمكانية الوصول والتنظيم.

#### س: كيف تساعد مكتبة Aspose.PDF في إنشاء مستند PDF يحتوي على صورة مميزة؟

ج: Aspose.PDF for .NET هي مكتبة قوية توفر وظائف لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي، يتم استخدام ميزات بنية المحتوى المميز للمكتبة لإضافة صورة مميزة إلى مستند PDF.

#### س: ما هي المتطلبات الأساسية لإنشاء مستند PDF يحتوي على صورة مميزة باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ، تأكد من تثبيت Visual Studio مع إطار عمل .NET ومن وجود مكتبة Aspose.PDF لـ .NET مذكورة في مشروعك.

#### س: كيف يقوم الكود C# المقدم بإنشاء مستند PDF يحتوي على صورة مميزة؟

ج: يوضح الكود كيفية إنشاء مستند PDF، وتحديد عنصر صورة مُميز، وإضافته إلى محتوى المستند. تتضمن الصورة المُميزة نصًا بديلًا وعنوانًا وعلامة باستخدام الطرق التي يوفرها Aspose.PDF.

#### س: هل يمكنني استخدام تنسيقات صور مختلفة للصورة التي تم وضع علامة عليها؟

ج: نعم، يمكنك استخدام تنسيقات صور مختلفة للصورة التي تم وضع علامة عليها، مثل JPEG وPNG وGIF وما إلى ذلك. يستخدم مثال التعليمات البرمجية المقدم في البرنامج التعليمي صورة JPEG، ولكن يمكنك استبدالها بمسار ملف صورة بالتنسيق المفضل لديك.

#### س: كيف يتم استخدام النص البديل (النص البديل) في الصور التي تم وضع علامات عليها؟

 أ: يوفر النص البديل وصفًا نصيًا للصورة، والذي تتم قراءته بصوت عالٍ بواسطة برامج قراءة الشاشة للمستخدمين الذين يعانون من ضعف البصر. في الكود المقدم، يتم تعيين النص البديل باستخدام`AlternativeText` ممتلكات`IllustrationElement` تمثل الصورة المميزة.

####  س: كيف يتم ذلك؟`SetTitle` method contribute to the PDF document's tagged image?

 أ: ال`SetTitle` تحدد الطريقة عنوان المحتوى المميز في مستند PDF، مما يوفر سياقًا إضافيًا للصورة المميزة. يمكن أن يساعد هذا العنوان في تحديد الغرض أو موضوع المحتوى المميز.

#### س: هل يمكنني تخصيص العلامة وعنوان الصورة التي تم وضع العلامة عليها؟

 ج: نعم، يمكنك تخصيص العلامة وعنوان الصورة المُوسومة باستخدام`SetTag` و`Title` طرق`IllustrationElement`يوضح مثال الكود كيفية تعيين العلامة إلى "Fig" والعنوان إلى "Picture 1".

#### س: كيف يمكنني التأكد من أن الصورة التي تم وضع علامة عليها يمكن الوصول إليها وتتوافق مع معايير إمكانية الوصول؟

ج: من خلال استخدام ميزات بنية المحتوى المُوسوم في Aspose.PDF وتوفير نص بديل ومعلومات أخرى ذات صلة، فإنك تساهم في إمكانية الوصول إلى الصورة المُوسومة. يتضمن ضمان الامتثال لمعايير إمكانية الوصول اتباع أفضل الممارسات للنص البديل وبنية المستند.

#### س: هل من الممكن إضافة صور متعددة ذات علامات إلى نفس مستند PDF باستخدام تقنيات مماثلة؟

 ج: نعم، يمكنك إضافة صور متعددة مُميزة إلى نفس مستند PDF باستخدام تقنيات مماثلة. يمكنك إنشاء صور إضافية`IllustrationElement` أمثلة لكل صورة مُوسومة وتخصيص خصائصها حسب الحاجة.