---
title: الحصول على نافذة الوثيقة
linktitle: الحصول على نافذة الوثيقة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام ميزة GetDocumentWindow في Aspose.PDF لـ .NET لاسترداد معلومات حول خصائص نافذة مستند PDF.
type: docs
weight: 170
url: /ar/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF for .NET هي مكتبة قوية لمعالجة ملفات PDF تتيح للمطورين إنشاء ملفات PDF وتحريرها وتحويلها في تطبيقات .NET الخاصة بهم. إحدى الميزات التي تقدمها هذه المكتبة هي القدرة على استرداد المعلومات حول خصائص نافذة المستند. سيرشدك هذا البرنامج التعليمي خلال خطوات استخدام`GetDocumentWindow` ميزة Aspose.PDF لـ .NET لاسترداد معلومات حول خصائص نافذة مستند PDF.

## الخطوة 1: تثبيت Aspose.PDF لـ .NET

 لاستخدام Aspose.PDF لـ .NET في تطبيقات .NET الخاصة بك، يجب عليك أولاً تثبيت المكتبة. يمكنك تنزيل أحدث إصدار من المكتبة من[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net).

بمجرد تنزيل المكتبة، قم باستخراج محتويات الملف المضغوط إلى مجلد على جهاز الكمبيوتر الخاص بك. ستحتاج بعد ذلك إلى إضافة مرجع إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

## الخطوة 2: قم بتحميل مستند PDF

بمجرد تثبيت Aspose.PDF لـ .NET وإضافة مرجع إلى DLL في مشروع .NET الخاص بك، يمكنك البدء في استخدام`GetDocumentWindow` ميزة لاسترداد معلومات حول خصائص نافذة مستند PDF.

الخطوة الأولى في استخدام هذه الميزة هي تحميل مستند PDF الذي تريد استرداد معلومات عنه. للقيام بذلك، يمكنك استخدام الكود التالي:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//افتح مستند بي دي إف
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 في الكود أعلاه، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك. سيقوم هذا الرمز بتحميل مستند PDF إلى ملف`Document` كائن، والذي يمكنك بعد ذلك استخدامه لاسترداد معلومات حول خصائص نافذة المستند.

## الخطوة 3: استرداد خصائص نافذة المستند

لاسترداد معلومات حول خصائص نافذة مستند PDF، يمكنك استخدام الكود التالي:

```csharp
// استرداد خصائص نافذة الوثيقة
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

في الكود أعلاه، يسترد كل سطر خاصية نافذة مختلفة لمستند PDF ويخرجها إلى وحدة التحكم. يمكنك تخصيص هذا الرمز لاسترداد الخصائص التي تهمك فقط.

### مثال على التعليمات البرمجية المصدر للحصول على نافذة مستند لملف PDF باستخدام Aspose.PDF لـ .NET 

 إليك الكود المصدري الكامل لاسترداد خصائص نافذة مستند PDF باستخدام ملف`GetDocumentWindow` ميزة Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// الحصول على خصائص وثيقة مختلفة
// موضع نافذة المستند - الافتراضي: خطأ
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// ترتيب القراءة السائد؛ يحدد موضع الصفحة
// عند العرض جنبًا إلى جنب - الافتراضي: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// ما إذا كان شريط عنوان النافذة يجب أن يعرض عنوان المستند
// إذا كان خطأ، فسيعرض شريط العنوان اسم ملف PDF - الافتراضي: خطأ
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// ما إذا كان سيتم تغيير حجم نافذة المستند لتناسب حجمها
// الصفحة المعروضة الأولى - الافتراضي: خطأ
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// ما إذا كان سيتم إخفاء شريط القائمة لتطبيق العارض - الافتراضي: خطأ
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//ما إذا كان سيتم إخفاء شريط الأدوات الخاص بتطبيق العارض - الافتراضي: خطأ
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// ما إذا كان سيتم إخفاء عناصر واجهة المستخدم مثل أشرطة التمرير
// وترك فقط محتويات الصفحة المعروضة - الافتراضي: خطأ
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// وضع صفحة المستند. كيفية عرض المستند عند الخروج من وضع ملء الشاشة.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// تخطيط الصفحة، أي صفحة واحدة وعمود واحد
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// كيف ينبغي أن تظهر الوثيقة عند فتحها
// أي إظهار الصور المصغرة، بملء الشاشة، وإظهار لوحة المرفقات
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.PDF لـ .NET لاسترداد معلومات حول خصائص نافذة مستند PDF. من خلال تحميل مستند PDF والوصول إلى خصائص نافذته، يمكنك جمع معلومات حول كيفية عرض المستند عند فتحه في تطبيق العارض. يوفر Aspose.PDF for .NET مجموعة قوية من الميزات للعمل مع ملفات PDF برمجيًا، مما يجعله أداة قيمة لمعالجة PDF في تطبيقات .NET.

### الأسئلة الشائعة

#### س: ما هو الغرض من استرجاع خصائص نافذة مستند PDF؟

ج: يتيح لك استرداد خصائص نافذة مستند PDF جمع معلومات حول كيفية عرض مستند PDF عند فتحه في تطبيق العارض. تتحكم هذه الخصائص في جوانب مختلفة مثل موضع النافذة ووضع العرض ورؤية عناصر واجهة المستخدم.

#### س: كيف يمكنني تثبيت Aspose.PDF لـ .NET في مشروع .NET الخاص بي؟

 ج: لتثبيت Aspose.PDF لـ .NET، تحتاج إلى تنزيل المكتبة من ملف[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net). بعد التنزيل، قم باستخراج محتويات الملف المضغوط وإضافة مرجع إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

#### س: هل يمكنني تخصيص التعليمات البرمجية لاسترداد خصائص نافذة معينة فقط؟

ج: نعم، يمكنك تخصيص التعليمات البرمجية لاسترداد خصائص نافذة محددة عن طريق التعليق على السطور التي لا تحتاج إليها. يتوافق كل سطر في التعليمات البرمجية مع خاصية نافذة محددة، بحيث يمكنك تضمين الخصائص أو استبعادها بناءً على متطلباتك.

#### س: ما هي أنواع خصائص النافذة التي يمكنني استردادها باستخدام Aspose.PDF لـ .NET؟

ج: باستخدام Aspose.PDF for .NET، يمكنك استرداد خصائص نافذة متنوعة لمستند PDF، بما في ذلك توسيط النافذة، وتعيين تخطيط الصفحة، والتحكم في عرض أشرطة الأدوات وأشرطة القوائم، والمزيد.