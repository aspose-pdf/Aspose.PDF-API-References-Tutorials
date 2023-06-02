---
title: ملفات Pdf المتسلسلة
linktitle: ملفات Pdf المتسلسلة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لسلسلة ملفات PDF باستخدام Aspose.PDF for .NET. سهولة المتابعة والتنفيذ في مشاريعك.
type: docs
weight: 20
url: /ar/net/programming-with-pdf-pages/concatenate-pdf-files/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لسلسلة ملفات PDF باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تجميع ملفات PDF باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي توجد فيه ملفات PDF المراد تجميعها. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح ملفات PDF
 ثم يمكنك فتح ملفات PDF للتسلسل باستخدام امتداد`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لكل ملف PDF.

```csharp
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
```

## الخطوة 3: ربط الصفحات
 يمكنك الآن إضافة الصفحات من المستند الثاني إلى المستند الأول باستخدام ملف`Add()` طريقة المستند`Pages` مجموعة. سيؤدي ذلك إلى تجميع صفحات كلا المستندين في مستند واحد.

```csharp
pdfDocument1.Pages.Add(pdfDocument2.Pages);
```

## الخطوة 4: احفظ ملف PDF المتسلسل
 أخيرًا ، يمكنك حفظ مستند PDF المتسلسل في ملف الإخراج باستخدام المستند`Save()` طريقة. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
pdfDocument1.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Concatenate Pdf Files باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند الأول
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
// افتح المستند الثاني
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
// أضف صفحات من المستند الثاني إلى الأول
pdfDocument1.Pages.Add(pdfDocument2.Pages);
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
//حفظ ملف الإخراج المتسلسل
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nPDFs are concatenated successfully.\nFile saved at " + dataDir);

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تجميع ملفات PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة أعلاه ، يمكنك بسهولة تنفيذ هذه الوظيفة في مشاريعك الخاصة. لا تتردد في استكشاف وثائق Aspose.PDF لاكتشاف الميزات المفيدة الأخرى للعمل مع ملفات PDF.
