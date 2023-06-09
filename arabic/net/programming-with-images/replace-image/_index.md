---
title: استبدال الصورة
linktitle: استبدال الصورة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستبدال صورة في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 240
url: /ar/net/programming-with-images/replace-image/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية استبدال صورة في مستند PDF باستخدام Aspose.PDF لـ .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## الخطوة 1: المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة الثانية: تحميل مستند PDF

للبدء ، استخدم الكود التالي لتحميل مستند PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ReplaceImage.pdf");
```

تأكد من توفير المسار الصحيح لوثيقة PDF الخاصة بك.

## الخطوة 3: استبدال صورة معينة

لاستبدال صورة معينة في مستند PDF ، استخدم الكود التالي:

```csharp
// استبدال صورة معينة
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
```

في هذا المثال ، نقوم باستبدال الصورة الموجودة في الصفحة 1 من مستند PDF. تأكد من توفير المسار الصحيح للصورة الجديدة التي تريد استخدامها.

## الخطوة 4: حفظ ملف PDF المحدث

بعد إجراء استبدال الصورة ، احفظ ملف PDF المحدث باستخدام الكود التالي:

```csharp
dataDir = dataDir + "ReplaceImage_out.pdf";
// احفظ ملف PDF المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved as: " + dataDir);
```

تأكد من توفير المسار المطلوب واسم الملف لملف PDF المحدث.

### نموذج التعليمات البرمجية المصدر لاستبدال الصورة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir+ "ReplaceImage.pdf");
// استبدل صورة معينة
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
dataDir = dataDir + "ReplaceImage_out.pdf";
// احفظ ملف PDF المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهنئة ! لقد نجحت في استبدال صورة في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لتحرير الصور في ملفات PDF.