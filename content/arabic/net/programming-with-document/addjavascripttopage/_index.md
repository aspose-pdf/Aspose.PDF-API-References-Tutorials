---
title: إضافة جافا سكريبت إلى ملف PDF
linktitle: إضافة ملف جافا سكريبت PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة JavaScript إلى ملف PDF باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة مع دروس التعليمات البرمجية للبرمجة النصية على مستوى المستند والصفحة.
type: docs
weight: 10
url: /ar/net/programming-with-document/addjavascripttopage/
---
لإضافة JavaScript إلى ملف PDF، سوف نستخدم Aspose.PDF لـ .NET. توفر هذه المكتبة طريقة بسيطة وفعالة للعمل مع ملفات PDF في تطبيقات .NET. سترشدك الخطوات التالية خلال عملية إضافة JavaScript إلى ملف PDF باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: قم بتحميل ملف PDF

 الخطوة الأولى هي تحميل ملف PDF الذي تريد إضافة JavaScript إليه. يمكنك القيام بذلك باستخدام`Document` فئة مقدمة من Aspose.PDF لـ .NET. ال`Document` يوفر الفصل طرقًا لتحميل ملفات PDF وحفظها ومعالجتها.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملفات PDF الموجودة
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 2: إضافة JavaScript على مستوى المستند

لإضافة JavaScript على مستوى المستند، سوف نستخدم`JavascriptAction` فئة مقدمة من Aspose.PDF لـ .NET. تتيح لك هذه الفئة تحديد عبارة JavaScript التي تريد إضافتها إلى ملف PDF.

```csharp
// إضافة جافا سكريبت على مستوى الوثيقة
// إنشاء مثيل لـ JavascriptAction باستخدام عبارة JavaScript المطلوبة
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// قم بتعيين كائن JavascriptAction للإجراء المطلوب للمستند
doc.OpenAction = javaScript;
```

في هذا البرنامج التعليمي، نقوم بإضافة عبارة JavaScript التي ستقوم بطباعة ملف PDF بالخيارات المحددة عند فتح المستند.

## الخطوة 3: إضافة جافا سكريبت على مستوى الصفحة

 لإضافة JavaScript على مستوى الصفحة، سنستخدم الأمر`JavascriptAction` الطبقة و`Actions` الخاصية المقدمة من Aspose.PDF لـ .NET. تتيح لك هذه الخاصية تحديد عبارات JavaScript التي سيتم تنفيذها عند فتح الصفحة أو إغلاقها.

```csharp
// إضافة جافا سكريبت على مستوى الصفحة
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

في هذا البرنامج التعليمي، نقوم بإضافة عبارات JavaScript التي ستعرض رسالة تنبيه عند فتح الصفحة أو إغلاقها.

## الخطوة 4: احفظ ملف PDF

بعد إضافة JavaScript إلى ملف PDF، ستحتاج إلى حفظ الملف المعدل. يمكنك القيام بذلك باستخدام`Save` الطريقة المقدمة من`Document` فصل.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

سيحفظ هذا الرمز ملف PDF المعدل في الدليل المحدد.

### مثال على التعليمات البرمجية المصدر لإضافة Java Script إلى الصفحة باستخدام Aspose.PDF لـ .NET

```csharp
            
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملفات PDF الموجودة
Document doc = new Document(dataDir + "input.pdf");

// إضافة جافا سكريبت على مستوى الوثيقة
// إنشاء مثيل لـ JavascriptAction باستخدام عبارة JavaScript المرغوبة
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// قم بتعيين كائن JavascriptAction للإجراء المطلوب للمستند
doc.OpenAction = javaScript;

// إضافة جافا سكريبت على مستوى الصفحة
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## خاتمة

في هذه المقالة، شرحنا كيفية إضافة JavaScript إلى ملف PDF على مستوى المستند ومستوى الصفحة باستخدام Aspose.PDF لـ .NET. لقد قدمنا تعليمات خطوة بخطوة وقمنا بتضمين كود المصدر الكامل لكل مثال. باستخدام هذه المعرفة، يمكنك إضافة JavaScript إلى ملفات PDF الخاصة بك وتخصيص سلوكها وفقًا لاحتياجاتك.


### الأسئلة الشائعة لإضافة جافا سكريبت إلى ملف PDF

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تمكن المطورين من العمل مع ملفات PDF في تطبيقات .NET. يوفر مجموعة واسعة من الميزات لإنشاء مستندات PDF وتعديلها ومعالجتها.

#### س: هل يمكنني إضافة JavaScript إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يسمح لك Aspose.PDF for .NET بإضافة JavaScript إلى كل من مستوى المستند ومستوى الصفحة لملف PDF، مما يتيح لك إنشاء مستندات PDF ديناميكية وتفاعلية.

#### س: كيف يمكنني تحميل ملف PDF موجود باستخدام Aspose.PDF لـ .NET؟

 ج: يمكنك تحميل ملف PDF موجود باستخدام الملف`Document` الطبقة وأساليبها، كما هو موضح في الدليل خطوة بخطوة.

#### س: ما أنواع إجراءات JavaScript التي يمكنني إضافتها إلى مستند PDF؟

ج: باستخدام Aspose.PDF for .NET، يمكنك إضافة مجموعة واسعة من إجراءات JavaScript، مثل الطباعة ورسائل التنبيه ومعالجة حقل النموذج والمزيد.

#### س: هل Aspose.PDF for .NET مناسب للمشاريع التجارية؟

ج: نعم، Aspose.PDF for .NET هي مكتبة موثوقة وقوية تُستخدم بشكل شائع في المشاريع التجارية لمعالجة ملفات PDF ومهام الإنشاء.

