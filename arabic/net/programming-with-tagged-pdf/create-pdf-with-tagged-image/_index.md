---
title: إنشاء ملف PDF مع صورة ذات علامات
linktitle: إنشاء ملف PDF مع صورة ذات علامات
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإنشاء ملف PDF مع صورة مميزة باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
في هذا البرنامج التعليمي ، سنزودك بدليل تفصيلي حول كيفية إنشاء مستند PDF مع صورة مميزة باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح لك بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى الموسومة في Aspose.PDF ، يمكنك إضافة صور ذات علامات إلى مستند PDF الخاص بك.

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

## الخطوة 3: إنشاء مستند PDF بصورة مميزة

استخدم الكود التالي لإنشاء مستند PDF مع صورة ذات علامات:

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

ينشئ هذا الرمز مستند PDF فارغًا ويضيف صورة ذات علامات باستخدام الطرق التي يوفرها Aspose.PDF. يتم تحديد الصورة بنص بديل وعنوان وعلامة.

## الخطوة 4: حفظ مستند PDF

استخدم الكود التالي لحفظ مستند PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

يحفظ هذا الرمز مستند PDF مع الصورة ذات العلامات في ملف محدد.

### عينة من التعليمات البرمجية المصدر لإنشاء PDF مع صورة ذات علامات باستخدام Aspose.PDF for .NET 
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
// إضافة صورة بدقة 300 نقطة في البوصة (افتراضيًا)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// حفظ وثيقة PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إنشاء مستند PDF مع صورة مميزة باستخدام Aspose.PDF for .NET. تضيف الصور ذات العلامات معلومات منظمة إضافية إلى مستند PDF الخاص بك.

### التعليمات

#### س: ما هو الغرض من إنشاء مستند PDF مع صورة ذات علامات باستخدام Aspose.PDF for .NET؟

ج: إنشاء مستند PDF مع صورة مميزة باستخدام Aspose.PDF for .NET يسمح لك بإضافة صور ذات علامات تمييز إلى محتوى المستند. توفر الصور ذات العلامات معلومات منظمة ، مثل النص البديل والعناوين ، مما يعزز إمكانية الوصول والتنظيم.

#### س: كيف تساعد مكتبة Aspose.PDF في إنشاء مستند PDF بصورة ذات علامات تمييز؟

ج: Aspose.PDF for .NET مكتبة قوية توفر وظائف لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي ، يتم استخدام ميزات بنية المحتوى الموسومة بالمكتبة لإضافة صورة ذات علامات تمييز إلى مستند PDF.

#### س: ما هي المتطلبات الأساسية لإنشاء مستند PDF بصورة ذات علامات تمييز باستخدام Aspose.PDF for .NET؟

ج: قبل أن تبدأ ، تأكد من تثبيت Visual Studio مع إطار عمل .NET وأن لديك مكتبة Aspose.PDF لـ .NET المشار إليها في مشروعك.

#### س: كيف ينشئ كود C # المقدم مستند PDF مع صورة ذات علامات؟

ج: يوضح الكود كيفية إنشاء مستند PDF ، وتعريف عنصر صورة مميز وإضافته إلى محتوى المستند. تتضمن الصورة ذات العلامات نصًا بديلًا وعنوانًا وعلامة باستخدام الطرق التي يوفرها Aspose.PDF.

#### س: هل يمكنني استخدام تنسيقات صور مختلفة للصورة التي تم وضع علامة عليها؟

ج: نعم ، يمكنك استخدام تنسيقات صور مختلفة للصورة ذات العلامات ، مثل JPEG ، و PNG ، و GIF ، وما إلى ذلك. يستخدم مثال الرمز المقدم في البرنامج التعليمي صورة JPEG ، ولكن يمكنك استبدالها بالمسار إلى ملف صورة في الشكل المفضل لديك.

#### س: كيف يتم استخدام النص البديل (نص بديل) في الصور ذات العلامات؟

 ج: يوفر النص البديل وصفًا نصيًا للصورة ، يتم قراءته بصوت عالٍ بواسطة برامج قراءة الشاشة للمستخدمين ضعاف البصر. في الكود المتوفر ، يتم تعيين النص البديل باستخدام امتداد`AlternativeText` ممتلكات`IllustrationElement` تمثل الصورة الموسومة.

####  س: كيف يعمل ملف`SetTitle` method contribute to the PDF document's tagged image?

 ج: إن`SetTitle` تحدد الطريقة عنوان محتوى مستند PDF المميز ، مما يوفر سياقًا إضافيًا للصورة المميزة. يمكن أن يساعد هذا العنوان في تحديد الغرض أو موضوع المحتوى الذي تم وضع علامة عليه.

#### س: هل يمكنني تخصيص العلامة وعنوان الصورة التي تم وضع علامة عليها؟

 ج: نعم ، يمكنك تخصيص العلامة وعنوان الصورة التي تم وضع علامة عليها باستخدام`SetTag` و`Title` طرق`IllustrationElement`. يوضح مثال الكود كيفية تعيين العلامة على "Fig" والعنوان إلى "Picture 1."

#### س: كيف يمكنني التأكد من أن الصورة التي تم وضع علامة عليها يمكن الوصول إليها ومتوافقة مع معايير إمكانية الوصول؟

ج: باستخدام ميزات بنية المحتوى الموسومة في Aspose.PDF وتوفير نص بديل ومعلومات أخرى ذات صلة ، فإنك تساهم في إمكانية الوصول إلى الصورة التي تم وضع علامة عليها. يتضمن ضمان التوافق مع معايير إمكانية الوصول اتباع أفضل الممارسات للنص البديل وهيكل المستند.

#### س: هل من الممكن إضافة صور متعددة بعلامات تمييز إلى نفس مستند PDF باستخدام تقنيات مماثلة؟

 ج: نعم ، يمكنك إضافة صور متعددة بعلامات تمييز إلى نفس مستند PDF باستخدام تقنيات مماثلة. يمكنك إنشاء ملفات`IllustrationElement` مثيلات لكل صورة مميزة وتخصيص خصائصها حسب الحاجة.