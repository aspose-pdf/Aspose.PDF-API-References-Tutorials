---
title: حذف كافة التعليقات التوضيحية من الصفحة
linktitle: حذف كافة التعليقات التوضيحية من الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية حذف جميع التعليقات التوضيحية من صفحة PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 40
url: /ar/net/annotations/deleteallannotationsfrompage/
---
Aspose.PDF for .NET مكتبة قوية تسمح للمطورين بإنشاء ملفات PDF ومعالجتها وتحويلها. في هذه المقالة ، سوف نستكشف كيفية استخدام Aspose.PDF for .NET لحذف جميع التعليقات التوضيحية من صفحة معينة من مستند PDF. سنقدم لك دليلًا تفصيليًا لمساعدتك على فهم العملية.

اتبع الخطوات التالية لحذف كافة التعليقات التوضيحية من الصفحة باستخدام Aspose.PDF for .NET

## الخطوة 1: قم بتثبيت Aspose.PDF for .NET

 لاستخدام Aspose.PDF لـ .NET ، تحتاج إلى تثبيت المكتبة أولاً. أنت تستطيع[تحميل](https://releases.aspose.com/pdf/net/)المكتبة من إصدارات Aspose وتثبيتها على جهاز الكمبيوتر الخاص بك. بعد التثبيت ، تحتاج إلى إضافة مرجع إلى المكتبة في مشروعك.

## الخطوة 2: إنشاء تطبيق جديد لوحدة التحكم

قم بإنشاء تطبيق وحدة تحكم جديد في Visual Studio وأضف مرجعًا إلى مكتبة Aspose.PDF. في هذا البرنامج التعليمي ، سوف نستخدم لغة C #.

## الخطوة 3: قم بتحميل مستند PDF

في الكود المصدري المقدم ، أول شيء نقوم به هو تحديد المسار إلى مستند PDF. تحتاج إلى استبدال "دليل المستندات الخاص بك" بالمسار الفعلي إلى مستند PDF على جهاز الكمبيوتر الخاص بك. بعد ذلك ، نقوم بإنشاء مثيل جديد لفئة Document وتحميل مستند PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "DeleteAllAnnotationsFromPage.pdf");
```

## الخطوة 4: حذف جميع التعليقات التوضيحية من الصفحة

لحذف جميع التعليقات التوضيحية من صفحة معينة من مستند PDF ، نحتاج إلى الوصول إلى مجموعة التعليقات التوضيحية لكائن الصفحة واستدعاء طريقة الحذف (). في الكود المصدري المقدم ، نحذف جميع التعليقات التوضيحية من الصفحة الثانية (الفهرس 1) من مستند PDF.

```csharp
pdfDocument.Pages[1].Annotations.Delete();
```

## الخطوة 5: احفظ مستند PDF المحدث

بعد حذف التعليقات التوضيحية ، نحتاج إلى حفظ مستند PDF المحدث. في الكود المصدري المقدم ، نحدد المسار إلى مستند PDF الناتج ونطلق على طريقة Save ().

```csharp
dataDir = dataDir + "DeleteAllAnnotationsFromPage_out.pdf";
pdfDocument.Save(dataDir);
```

### مثال التعليمات البرمجية المصدر لحذف كافة التعليقات التوضيحية من الصفحة باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "DeleteAllAnnotationsFromPage.pdf");

// حذف تعليق توضيحي معين
pdfDocument.Pages[1].Annotations.Delete();

dataDir = dataDir + "DeleteAllAnnotationsFromPage_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
``` 

## خاتمة

في هذه المقالة ، قدمنا دليلًا تفصيليًا لمساعدتك على فهم كيفية حذف جميع التعليقات التوضيحية من صفحة معينة من مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة في هذا الدليل ، يمكنك بسهولة تنفيذ هذه الميزة في مشروعك الخاص.