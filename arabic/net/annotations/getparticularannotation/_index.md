---
title: احصل على تعليق توضيحي خاص
linktitle: احصل على تعليق توضيحي خاص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET للحصول على تعليق توضيحي معين في مستند PDF باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 80
url: /ar/net/annotations/getparticularannotation/
---
إذا كنت تعمل باستخدام ملفات PDF في .NET ، فقد تواجه حاجة للحصول على تعليق توضيحي معين من مستند PDF. في هذا الدليل ، سنوضح لك كيفية استخدام Aspose.PDF for .NET للحصول على تعليق توضيحي معين من مستند PDF باستخدام C #.

اتبع هذه الخطوات البسيطة للحصول على تعليق توضيحي معين من مستند PDF:

## الخطوة 1: احصل على تعليق توضيحي معين من مستند PDF

أولاً ، تأكد من تثبيت Aspose.PDF لمكتبة .NET والإشارة إليها في مشروعك.

بعد ذلك ، قم بإنشاء مثيل جديد من فئة Document وقم بتحميل مستند PDF الخاص بك باستخدام المسار إلى دليل المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");
```

## الخطوة 2: يمكنك الحصول على تعليق توضيحي معين باستخدام الكود التالي:

```csharp
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];
```

يسترد هذا الرمز التعليق التوضيحي الثاني على الصفحة الثانية من مستند PDF.

## الخطوة 3: أخيرًا ، يمكنك الحصول على خصائص التعليق التوضيحي باستخدام الكود التالي:

```csharp
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

يعرض هذا الرمز العنوان والموضوع ومحتويات التعليق التوضيحي في وحدة التحكم.


### مثال على التعليمات البرمجية المصدر للحصول على تعليق توضيحي معين باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");

// احصل على تعليق توضيحي معين
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];

// احصل على خصائص التعليقات التوضيحية
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

