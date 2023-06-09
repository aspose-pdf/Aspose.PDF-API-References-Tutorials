---
title: حذف كافة الإشارات المرجعية
linktitle: حذف كافة الإشارات المرجعية
second_title: Aspose.PDF لمرجع .NET API
description: احذف جميع الإشارات المرجعية بسهولة من ملفات PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-bookmarks/delete-all-bookmarks/
---

# احذف جميع الإشارات المرجعية باستخدام Aspose.PDF for .NET

قد يكون حذف الإشارات المرجعية من مستند PDF ضروريًا في بعض الحالات. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إزالة جميع الإشارات المرجعية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إزالة الإشارات المرجعية منه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنقوم الآن بفتح مستند PDF الذي نريد إزالة الإشارات المرجعية منه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## الخطوة 4: حذف كل الإشارات المرجعية

 في هذه الخطوة ، نحذف جميع الإشارات المرجعية من المستند باستخدام امتداد`Delete` طريقة`Outlines` ملكية. هذا هو الكود المقابل:

```csharp
pdfDocument.Outlines.Delete();
```

## الخطوة 5: احفظ الملف المحدث

 أخيرًا ، نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`pdfDocument` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Delete All Bookmarks باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// حذف كل الإشارات المرجعية
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// احفظ الملف المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة لإزالة جميع الإشارات المرجعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لتنظيف مستندات PDF الخاصة بك عن طريق حذف جميع الإشارات المرجعية الموجودة.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.