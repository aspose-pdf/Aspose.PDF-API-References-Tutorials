---
title: حذف كافة المرفقات
linktitle: حذف كافة المرفقات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إزالة جميع المرفقات من ملف PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة لسهولة التعامل.
type: docs
weight: 20
url: /ar/net/programming-with-attachments/delete-all-attachments/
---
في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة لإزالة جميع المرفقات من ملف PDF باستخدام Aspose.PDF for .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل أن تبدأ. لديك أيضًا معرفة أساسية ببرمجة C #.

### الخطوة 1: إعداد دليل المستند

في كود المصدر المقدم ، تحتاج إلى تحديد الدليل الذي يوجد به ملف PDF والذي تريد إزالة المرفقات منه. قم بتغيير متغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### الخطوة 2: افتح مستند PDF الحالي

نفتح مستند PDF الحالي باستخدام المسار المحدد.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### الخطوة 3: قم بإزالة جميع المرفقات

نقوم بإزالة جميع المرفقات من المستند.

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### الخطوة 4: احفظ الملف المحدث

أخيرًا ، نحفظ ملف PDF المحدث باسم "DeleteAllAttachments_out.pdf" في الدليل المحدد.

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Delete All Attachments باستخدام Aspose.PDF for .NET 

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
// احذف كافة المرفقات
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
// احفظ الملف المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## خاتمة

في هذا البرنامج التعليمي ، أوضحنا كيفية إزالة جميع المرفقات من ملف PDF باستخدام Aspose.PDF for .NET. يمكنك الآن استخدام هذه المعرفة لتنظيف مستندات PDF الخاصة بك عن طريق إزالة جميع المرفقات غير المرغوب فيها.
