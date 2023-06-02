---
title: احصل على عدد الصفحات
linktitle: احصل على عدد الصفحات
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة للحصول على عدد صفحات ملف PDF باستخدام Aspose.PDF for .NET. سهل التنفيذ ومثالي لمشاريعك.
type: docs
weight: 70
url: /ar/net/programming-with-pdf-pages/get-number-of-pages/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة للحصول على عدد الصفحات لملف PDF باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية الحصول على عدد الصفحات لملف PDF باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو موقع ملف PDF الخاص بك الذي تريد الحصول على عدد الصفحات الخاص به. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح مستند PDF
 ثم يمكنك فتح ملف PDF باستخدام امتداد`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لملف PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
```

## الخطوة 3: احصل على عدد الصفحات
 يمكنك الآن الحصول على عدد الصفحات في المستند باستخدام امتداد`Count`ملكية المستند`s `مجموعة الصفحات. سيعطيك هذا العدد الإجمالي للصفحات في ملف PDF.

```csharp
System.Console.WriteLine("Number of pages: {0}", pdfDocument.Pages.Count);
```

### نموذج التعليمات البرمجية المصدر للحصول على Numberof Pages باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
// احصل على عدد الصفحات
System.Console.WriteLine("Page Count : {0}", pdfDocument.Pages.Count);

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على عدد الصفحات لملف PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة أعلاه ، يمكنك بسهولة تنفيذ هذه الوظيفة في مشاريعك الخاصة. لا تتردد في استكشاف وثائق Aspose.PDF لاكتشاف الميزات المفيدة الأخرى للعمل مع ملفات PDF.
