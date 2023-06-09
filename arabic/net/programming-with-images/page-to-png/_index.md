---
title: الصفحة إلى PNG
linktitle: الصفحة إلى PNG
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل صفحة إلى تنسيق PNG باستخدام Aspose.PDF for .NET.
type: docs
weight: 220
url: /ar/net/programming-with-images/page-to-png/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تحويل صفحة إلى تنسيق PNG باستخدام Aspose.PDF for .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تحميل مستند PDF

للبدء ، استخدم الكود التالي لتحميل مستند PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
```

تأكد من توفير المسار الصحيح لوثيقة PDF الخاصة بك.

## الخطوة 2: تحويل الصفحة إلى PNG

بعد ذلك ، سنقوم بتحويل صفحة معينة من مستند PDF إلى تنسيق PNG. استخدم الكود التالي:

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
// قم بإنشاء كائن حل
Resolution resolution = new Resolution(300);
// قم بإنشاء جهاز PNG بالسمات المحددة (العرض ، الارتفاع ، الدقة)
PngDevice pngDevice = new PngDevice(resolution);
// قم بتحويل صفحة معينة وحفظ الصورة في الدفق
pngDevice.Process(pdfDocument.Pages[1], imageStream);
// أغلق الدفق
imageStream.Close();
}
```

تأكد من توفير المسار واسم الملف المطلوبين لصورة PNG الناتجة.

### نموذج التعليمات البرمجية المصدر لـ Page To PNG باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
	// إنشاء كائن القرار
	Resolution resolution = new Resolution(300);
	// إنشاء جهاز PNG بسمات محددة (العرض ، الارتفاع ، الدقة)
	PngDevice pngDevice = new PngDevice(resolution);
	// قم بتحويل صفحة معينة وحفظ الصورة للدفق
	pngDevice.Process(pdfDocument.Pages[1], imageStream);
	// إغلاق الدفق
	imageStream.Close();
}
```

## خاتمة

تهنئة ! لقد نجحت في تحويل الصفحة إلى تنسيق PNG باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لاستخراج صفحات معينة من ملفات PDF وحفظها كصور PNG.