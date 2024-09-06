---
title: الحصول على نافذة المستند
linktitle: الحصول على نافذة المستند
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام ميزة GetDocumentWindow في Aspose.PDF لـ .NET لاسترداد معلومات حول خصائص نافذة مستند PDF.
type: docs
weight: 170
url: /ar/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF for .NET هي مكتبة معالجة PDF قوية تتيح للمطورين إنشاء ملفات PDF وتحريرها وتحويلها في تطبيقات .NET الخاصة بهم. إحدى الميزات التي تقدمها هذه المكتبة هي القدرة على استرداد المعلومات حول خصائص نافذة المستند. سيرشدك هذا البرنامج التعليمي خلال خطوات استخدام`GetDocumentWindow` ميزة Aspose.PDF لـ .NET لاسترجاع معلومات حول خصائص نافذة مستند PDF.

## الخطوة 1: تثبيت Aspose.PDF لـ .NET

 لاستخدام Aspose.PDF لـ .NET في تطبيقات .NET الخاصة بك، يجب عليك أولاً تثبيت المكتبة. يمكنك تنزيل أحدث إصدار من المكتبة من[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net).

بمجرد تنزيل المكتبة، قم باستخراج محتويات ملف ZIP إلى مجلد على جهاز الكمبيوتر الخاص بك. ستحتاج بعد ذلك إلى إضافة مرجع إلى ملف Aspose.PDF for .NET DLL في مشروع .NET الخاص بك.

## الخطوة 2: تحميل مستند PDF

 بمجرد تثبيت Aspose.PDF لـ .NET وإضافة مرجع إلى DLL في مشروع .NET الخاص بك، يمكنك البدء في استخدام`GetDocumentWindow`ميزة لاسترجاع معلومات حول خصائص نافذة مستند PDF.

الخطوة الأولى لاستخدام هذه الميزة هي تحميل مستند PDF الذي تريد استرجاع معلومات عنه. للقيام بذلك، يمكنك استخدام الكود التالي:

```csharp
// المسار إلى مستند PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح مستند PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 في الكود أعلاه، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك. سيقوم هذا الكود بتحميل مستند PDF إلى`Document` الكائن، والذي يمكنك استخدامه بعد ذلك لاسترجاع المعلومات حول خصائص نافذة المستند.

## الخطوة 3: استرداد خصائص نافذة المستند

لاسترجاع معلومات حول خصائص نافذة مستند PDF، يمكنك استخدام الكود التالي:

```csharp
// استرداد خصائص نافذة المستند
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

في الكود أعلاه، يقوم كل سطر باسترداد خاصية نافذة مختلفة من مستند PDF وإخراجها إلى وحدة التحكم. يمكنك تخصيص هذا الكود لاسترداد الخصائص التي تهمك فقط.

### مثال على كود المصدر للحصول على نافذة مستند لملف PDF باستخدام Aspose.PDF لـ .NET 

 فيما يلي الكود المصدر الكامل لاسترجاع خصائص نافذة مستند PDF باستخدام`GetDocumentWindow` ميزات Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// فتح المستند
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// الحصول على خصائص مختلفة للوثيقة
// موضع نافذة المستند - افتراضي: خطأ
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// ترتيب القراءة السائد؛ يحدد موضع الصفحة
// عند العرض جنبًا إلى جنب - الافتراضي: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// ما إذا كان شريط عنوان النافذة يجب أن يعرض عنوان المستند
// إذا كانت القيمة false، يعرض شريط العنوان اسم ملف PDF - الافتراضي: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// ما إذا كان سيتم تغيير حجم نافذة المستند لتناسب حجم
// الصفحة المعروضة أولاً - الافتراضي: خطأ
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// ما إذا كان سيتم إخفاء شريط القائمة لتطبيق العارض - افتراضي: خطأ
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// ما إذا كان سيتم إخفاء شريط أدوات تطبيق العارض - الافتراضي: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// ما إذا كان سيتم إخفاء عناصر واجهة المستخدم مثل أشرطة التمرير
// وترك محتويات الصفحة فقط معروضة - افتراضي: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//وضع الصفحة للمستند. كيفية عرض المستند عند الخروج من وضع ملء الشاشة.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// تخطيط الصفحة أي صفحة واحدة وعمود واحد
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// كيف ينبغي أن يظهر المستند عند فتحه
// إظهار الصور المصغرة، وعرض ملء الشاشة، وإظهار لوحة المرفقات
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.PDF for .NET لاسترداد معلومات حول خصائص نافذة مستند PDF. من خلال تحميل مستند PDF والوصول إلى خصائص نافذته، يمكنك جمع معلومات حول كيفية عرض المستند عند فتحه في تطبيق عارض. يوفر Aspose.PDF for .NET مجموعة قوية من الميزات للعمل مع ملفات PDF برمجيًا، مما يجعله أداة قيمة لمعالجة PDF في تطبيقات .NET.

### الأسئلة الشائعة

#### س: ما هو الغرض من استرجاع خصائص نافذة مستند PDF؟

أ: يتيح لك استرداد خصائص نافذة مستند PDF جمع معلومات حول كيفية عرض مستند PDF عند فتحه في تطبيق عارض. تتحكم هذه الخصائص في جوانب مختلفة مثل موضع النافذة ووضع العرض ورؤية عناصر واجهة المستخدم.

#### س: كيف يمكنني تثبيت Aspose.PDF لـ .NET في مشروع .NET الخاص بي؟

 أ: لتثبيت Aspose.PDF لـ .NET، تحتاج إلى تنزيل المكتبة من[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net)بعد التنزيل، قم باستخراج محتويات ملف ZIP وأضف مرجعًا إلى Aspose.PDF for .NET DLL في مشروع .NET الخاص بك.

#### س: هل يمكنني تخصيص الكود لاسترجاع خصائص نافذة محددة فقط؟

ج: نعم، يمكنك تخصيص الكود لاسترجاع خصائص نافذة معينة من خلال التعليق على الأسطر التي لا تحتاج إليها. يتوافق كل سطر في الكود مع خاصية نافذة معينة، لذا يمكنك تضمين أو استبعاد الخصائص بناءً على متطلباتك.

#### س: ما هي أنواع خصائص النافذة التي يمكنني استرجاعها باستخدام Aspose.PDF لـ .NET؟

ج: باستخدام Aspose.PDF لـ .NET، يمكنك استرداد خصائص النافذة المختلفة لمستند PDF، بما في ذلك مركز النافذة، وتعيين تخطيط الصفحة، والتحكم في عرض أشرطة الأدوات وأشرطة القوائم، والمزيد.