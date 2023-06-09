---
title: أبعاد التحديث
linktitle: أبعاد التحديث
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحديث أبعاد صفحة PDF باستخدام Aspose.PDF for .NET. تحقق من الأبعاد وفقًا لاحتياجاتك.
type: docs
weight: 150
url: /ar/net/programming-with-pdf-pages/update-dimensions/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتحديث أبعاد الصفحة في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تغيير أبعاد الصفحة في مستند PDF باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ مستند PDF الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح مستند PDF
 ثم يمكنك فتح مستند PDF الحالي باستخدام ملف`Document` فئة Aspose.PDF. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## الخطوة 3: احصل على مجموعة الصفحات
 يمكنك الآن الوصول إلى مجموعة الصفحات الخاصة بمستند PDF باستخدام امتداد`Pages` ممتلكات`Document` فصل.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## الخطوة 4: احصل على صفحة محددة
ثم يمكنك تحديد صفحة معينة من المستند باستخدام فهرس الصفحة في المجموعة. في هذا المثال ، نستخدم الصفحة الثانية (الفهرس 1).

```csharp
Page pdfPage = pageCollection[1];
```

## الخطوة 5: تحديد أبعاد الصفحة الجديدة
 الآن يمكنك ضبط حجم الصفحة الجديد باستخدام ملف`SetPageSize()` طريقة`Page` هدف. في هذا المثال ، نقوم بتعيين أبعاد الصفحة على A4 (11.7 × 8.3 بوصة) ، وتحويلها إلى نقاط (1 بوصة = 72 نقطة).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## الخطوة 6: احفظ المستند المحدث
أخيرًا ، يمكنك حفظ مستند PDF المحدث في ملف باستخدام امتداد`Save()` طريقة`Document`فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لتحديث الأبعاد باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// احصل على مجموعة الصفحات
PageCollection pageCollection = pdfDocument.Pages;
// احصل على صفحة معينة
Page pdfPage = pageCollection[1];
// اضبط حجم الصفحة على A4 (11.7 × 8.3 بوصة) وفي Aspose.Pdf ، 1 بوصة = 72 نقطة
// لذلك ستكون أبعاد A4 بالنقاط (842.4 ، 597.6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحديث أبعاد الصفحة في مستند PDF باستخدام Aspose.PDF for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تغيير أبعاد الصفحة في مستند PDF حسب الحاجة. يقدم Aspose.PDF واجهة برمجة تطبيقات قوية ومرنة للعمل مع ملفات PDF وأداء العديد من المعالجات ، بما في ذلك تغيير أبعاد الصفحة. من خلال هذه المعرفة ، يمكنك التحكم في أبعاد صفحات PDF الخاصة بك وتخصيصها لتلبية احتياجاتك الخاصة.
