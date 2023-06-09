---
title: اضافة للمفضلة
linktitle: اضافة للمفضلة
second_title: Aspose.PDF لمرجع .NET API
description: قم بإضافة إشارات مرجعية بسهولة إلى ملفات PDF الخاصة بك لتحسين التنقل باستخدام Aspose.PDF for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/add-bookmark/
---

تتيح إضافة إشارات مرجعية في مستند PDF التنقل السهل والسريع. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إضافة إشارة مرجعية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة إشارة مرجعية إليه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد إضافة إشارة مرجعية إليه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## الخطوة 4: إنشاء كائن إشارة مرجعية

 في هذه الخطوة ، سننشئ كائن إشارة مرجعية باستخدام`OutlineItemCollection` class وتعيين خصائصها مثل العنوان والسمة المائلة والسمة الغامقة والإجراء المطلوب تنفيذه عند النقر فوقه. هذا هو الكود المقابل:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## الخطوة 5: أضف إشارة مرجعية إلى المستند

 أخيرًا ، نضيف الإشارة المرجعية التي تم إنشاؤها إلى مجموعة الإشارات المرجعية للمستند باستخدام امتداد`Add` طريقة`Outlines` ملكية. هذا هو الكود المقابل:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### نموذج التعليمات البرمجية المصدر لإضافة إشارة مرجعية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// قم بإنشاء كائن إشارة مرجعية
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// قم بتعيين رقم الصفحة الوجهة
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// أضف إشارة مرجعية في مجموعة مخطط المستند.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// حفظ الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة لإضافة إشارة مرجعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لتحسين التنقل في مستندات PDF الخاصة بك عن طريق إضافة إشارات مرجعية مخصصة.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.