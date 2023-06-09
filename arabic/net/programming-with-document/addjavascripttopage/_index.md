---
title: إضافة Java Script إلى الصفحة
linktitle: إضافة Java Script إلى الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة JavaScript إلى ملفات PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة مع البرامج التعليمية للكود للبرمجة النصية على مستوى الصفحة والمستندات.
type: docs
weight: 10
url: /ar/net/programming-with-document/addjavascripttopage/
---

لإضافة JavaScript إلى ملف PDF ، سنستخدم Aspose.PDF لـ .NET. توفر هذه المكتبة طريقة بسيطة وفعالة للعمل مع ملفات PDF في تطبيقات .NET. ستوجهك الخطوات التالية خلال عملية إضافة JavaScript إلى ملف PDF باستخدام Aspose.PDF for .NET.

## الخطوة 1: قم بتحميل ملف PDF

 الخطوة الأولى هي تحميل ملف PDF الذي تريد إضافة JavaScript إليه. يمكنك القيام بذلك باستخدام ملف`Document` فئة مقدمة من Aspose.PDF لـ .NET. ال`Document` توفر class طرقًا لتحميل ملفات PDF وحفظها ومعالجتها.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملفات PDF موجودة
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 2: أضف JavaScript على مستوى المستند

 لإضافة JavaScript على مستوى المستند ، سنستخدم الامتداد`JavascriptAction` فئة مقدمة من Aspose.PDF لـ .NET. تسمح لك هذه الفئة بتحديد عبارة JavaScript التي تريد إضافتها إلى ملف PDF.

```csharp
// إضافة JavaScript على مستوى المستند
// قم بإنشاء JavascriptAction باستخدام عبارة JavaScript المطلوبة
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// قم بتعيين كائن JavascriptAction للإجراء المطلوب من المستند
doc.OpenAction = javaScript;
```

في هذا البرنامج التعليمي ، نضيف عبارة JavaScript التي ستطبع ملف PDF بالخيارات المحددة عند فتح المستند.

## الخطوة 3: أضف JavaScript على مستوى الصفحة

 لإضافة JavaScript على مستوى الصفحة ، سنستخدم الامتداد`JavascriptAction` الطبقة و`Actions`الخاصية المقدمة من Aspose.PDF لـ .NET. تتيح لك هذه الخاصية تحديد عبارات JavaScript التي سيتم تنفيذها عند فتح الصفحة أو إغلاقها.

```csharp
// إضافة JavaScript على مستوى الصفحة
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

في هذا البرنامج التعليمي ، نضيف عبارات JavaScript التي ستعرض رسالة تنبيه عند فتح الصفحة أو إغلاقها.

## الخطوة 4: احفظ ملف PDF

 بعد إضافة JavaScript إلى ملف PDF ، تحتاج إلى حفظ الملف المعدل. يمكنك القيام بذلك باستخدام ملف`Save` الطريقة التي يوفرها`Document` فصل.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

سيحفظ هذا الرمز ملف PDF المعدل في الدليل المحدد.

### مثال على الكود المصدري لإضافة Java Script To Page باستخدام Aspose.PDF for .NET

```csharp
            
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملفات PDF موجودة
Document doc = new Document(dataDir + "input.pdf");

// إضافة JavaScript على مستوى المستند
// قم بإنشاء JavascriptAction باستخدام عبارة JavaScript الموصوفة
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// قم بتعيين كائن JavascriptAction للإجراء المطلوب من المستند
doc.OpenAction = javaScript;

// إضافة JavaScript على مستوى الصفحة
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## خاتمة

في هذه المقالة ، شرحنا كيفية إضافة JavaScript إلى ملف PDF على كل من مستوى المستند ومستوى الصفحة باستخدام Aspose.PDF for .NET. لقد قدمنا إرشادات خطوة بخطوة وقمنا بتضمين شفرة المصدر الكاملة لكل مثال. باستخدام هذه المعرفة ، يمكنك إضافة JavaScript إلى ملفات PDF الخاصة بك وتخصيص سلوكها وفقًا لاحتياجاتك.


