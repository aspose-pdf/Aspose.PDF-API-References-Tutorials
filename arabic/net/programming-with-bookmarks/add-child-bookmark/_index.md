---
title: إضافة إشارة مرجعية تابعة
linktitle: إضافة إشارة مرجعية تابعة
second_title: Aspose.PDF لمرجع .NET API
description: أضف بسهولة إشارة مرجعية فرعية إلى ملفات PDF الخاصة بك لتصفح أكثر تنظيمًا باستخدام Aspose.PDF for .NET.
type: docs
weight: 20
url: /ar/net/programming-with-bookmarks/add-child-bookmark/
---

تسمح إضافة إشارات مرجعية فرعية إلى مستند PDF بمزيد من التنظيم المنظم والتنقل. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إضافة إشارة مرجعية فرعية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة إشارة مرجعية فرعية إليه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد إضافة إشارة مرجعية فرعية إليه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## الخطوة 4: إنشاء كائن إشارة مرجعية أصل

 في هذه الخطوة ، سننشئ كائن إشارة مرجعية أصليًا باستخدام الامتداد`OutlineItemCollection` class وتعيين خصائصها مثل العنوان والسمة المائلة والسمة الغامقة. هذا هو الكود المقابل:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## الخطوة 5: إنشاء كائن إشارة مرجعية فرعية

في هذه الخطوة ، سننشئ كائن إشارة مرجعية فرعية مرة أخرى باستخدام امتداد`OutlineItemCollection` فئة وتعيين خصائصها. هذا هو الكود المقابل:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## الخطوة 6: أضف الإشارة المرجعية الفرعية إلى الإشارة المرجعية الأصلية

 أخيرًا ، نضيف الإشارة المرجعية التي تم إنشاؤها إلى مجموعة الإشارات المرجعية الفرعية الخاصة بالإشارة المرجعية الأصلية باستخدام امتداد`Add` طريقة الكائن الأصل. هذا هو الكود المقابل:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## الخطوة 7: أضف الإشارة المرجعية الأصلية إلى مجموعة الإشارات المرجعية للمستند

 أخيرًا ، نضيف الإشارة المرجعية الأصلية إلى مجموعة الإشارات المرجعية للمستند باستخدام امتداد`Add` طريقة`Outlines` ملكية. هذا هو الكود المقابل:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### نموذج التعليمات البرمجية المصدر لإضافة إشارة مرجعية تابعة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// إنشاء كائن إشارة مرجعية أصل
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// قم بإنشاء كائن إشارة مرجعية فرعي
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// إضافة إشارة مرجعية فرعية في مجموعة الإشارات المرجعية الأصل
pdfOutline.Add(pdfChildOutline);
// إضافة إشارة مرجعية الأصل في مجموعة مخطط المستند.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// حفظ الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة لإضافة إشارة مرجعية فرعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لتنظيم إشاراتك المرجعية وهيكلها في مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.