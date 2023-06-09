---
title: احصل على نافذة الوثيقة
linktitle: احصل على نافذة الوثيقة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام ميزة GetDocumentWindow الخاصة بـ Aspose.PDF for .NET لاسترداد معلومات حول خصائص نافذة مستند PDF.
type: docs
weight: 170
url: /ar/net/programming-with-document/getdocumentwindow/
---

 Aspose.PDF for .NET هي مكتبة قوية لمعالجة ملفات PDF تتيح للمطورين إنشاء ملفات PDF وتحريرها وتحويلها في تطبيقات .NET الخاصة بهم. إحدى الميزات التي توفرها هذه المكتبة هي القدرة على استرداد معلومات حول خصائص نافذة المستند. سيرشدك هذا البرنامج التعليمي خلال خطوات استخدام ملف`GetDocumentWindow` ميزة Aspose.PDF for .NET لاسترداد معلومات حول خصائص نافذة وثيقة PDF.

## الخطوة 1: قم بتثبيت Aspose.PDF for .NET

 لاستخدام Aspose.PDF for .NET في تطبيقات .NET ، يجب عليك أولاً تثبيت المكتبة. يمكنك تنزيل أحدث إصدار من المكتبة من ملف[Aspose.PDF لصفحة تنزيل .NET](https://releases.aspose.com/pdf/net).

بمجرد تنزيل المكتبة ، قم باستخراج محتويات ملف ZIP إلى مجلد على جهاز الكمبيوتر الخاص بك. ستحتاج بعد ذلك إلى إضافة مرجع إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

## الخطوة 2: قم بتحميل مستند PDF

 بمجرد تثبيت Aspose.PDF for .NET وإضافة مرجع إلى DLL في مشروع .NET الخاص بك ، يمكنك البدء في استخدام`GetDocumentWindow` لاسترداد معلومات حول خصائص نافذة مستند PDF.

تتمثل الخطوة الأولى في استخدام هذه الميزة في تحميل مستند PDF الذي تريد استرداد معلومات عنه. للقيام بذلك ، يمكنك استخدام الكود التالي:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح مستند PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 في الكود أعلاه ، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يوجد مستند PDF الخاص بك. سيقوم هذا الرمز بتحميل مستند PDF إلى ملف`Document` الذي يمكنك استخدامه بعد ذلك لاسترداد معلومات حول خصائص نافذة المستند.

## الخطوة 3: استرجع خصائص نافذة المستند

لاسترداد معلومات حول خصائص نافذة مستند PDF ، يمكنك استخدام الكود التالي:

```csharp
// استرجع خصائص نافذة المستند
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

في الكود أعلاه ، يسترد كل سطر خاصية نافذة مختلفة لمستند PDF ويخرجها إلى وحدة التحكم. يمكنك تخصيص هذا الرمز لاسترداد الخصائص التي تهتم بها فقط.

### مثال على الكود المصدري للحصول على نافذة وثيقة لملف PDF باستخدام Aspose.PDF for .NET 

 فيما يلي رمز المصدر الكامل لاسترداد خصائص نافذة مستند PDF باستخدام امتداد`GetDocumentWindow` ميزة Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// الحصول على خصائص وثيقة مختلفة
// موضع نافذة المستند - الافتراضي: خطأ
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// ترتيب القراءة السائد ؛ يحدد موضع الصفحة
// عند عرضها جنبًا إلى جنب - الافتراضي: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// ما إذا كان يجب أن يعرض شريط عنوان النافذة عنوان المستند
// إذا كان خطأ ، يعرض شريط العنوان اسم ملف PDF - الافتراضي: خطأ
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// ما إذا كان سيتم تغيير حجم نافذة المستند لتناسب حجم
// أول صفحة معروضة - الافتراضي: خطأ
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// ما إذا كان سيتم إخفاء شريط قوائم تطبيق العارض - الإعداد الافتراضي: خطأ
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//ما إذا كان سيتم إخفاء شريط الأدوات لتطبيق العارض - الإعداد الافتراضي: خطأ
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// ما إذا كان سيتم إخفاء عناصر واجهة المستخدم مثل أشرطة التمرير
// وترك فقط محتويات الصفحة معروضة - الافتراضي: خطأ
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// وضع صفحة المستند. كيفية عرض المستند عند الخروج من وضع ملء الشاشة.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// تخطيط الصفحة أي صفحة واحدة ، عمود واحد
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// كيف يجب أن يظهر المستند عند فتحه
// أي عرض الصور المصغرة ، ملء الشاشة ، إظهار لوحة المرفقات
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```
