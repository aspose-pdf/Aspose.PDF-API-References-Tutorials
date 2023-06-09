---
title: حذف إشارة مرجعية معينة
linktitle: حذف إشارة مرجعية معينة
second_title: Aspose.PDF لمرجع .NET API
description: احذف بسهولة إشارة مرجعية معينة من ملفات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-bookmarks/delete-particular-bookmark/
---

قد يكون من الضروري حذف إشارة مرجعية معينة من وثيقة PDF. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة حذف إشارة مرجعية معينة باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إزالة إشارة مرجعية معينة منه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنقوم الآن بفتح مستند PDF الذي نريد إزالة إشارة مرجعية منه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
```

## الخطوة 4: حذف إشارة مرجعية معينة

 في هذه الخطوة ، نحذف إشارة مرجعية معينة باستخدام امتداد`Delete` طريقة`Outlines` ملكية. نحدد عنوان الإشارة المرجعية المطلوب حذفها. هذا هو الكود المقابل:

```csharp
pdfDocument.Outlines.Delete("Child Outline");
```

## الخطوة 5: احفظ الملف المحدث

 أخيرًا ، نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`pdfDocument` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لحذف إشارة مرجعية معينة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
// حذف مخطط تفصيلي خاص بالعنوان
pdfDocument.Outlines.Delete("Child Outline");
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
// احفظ الملف المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular bookmark deleted successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة لحذف إشارة مرجعية معينة باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لاستهداف وإزالة إشارات مرجعية معينة من مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.