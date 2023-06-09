---
title: ضبط حجم الصورة
linktitle: ضبط حجم الصورة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتعيين حجم الصورة في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 270
url: /ar/net/programming-with-images/set-image-size/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تعيين حجم الصورة في مستند PDF باستخدام Aspose.PDF لـ .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: إنشاء وثيقة PDF

للبدء ، استخدم الكود التالي لإنشاء مستند PDF جديد:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// إنشاء كائن مستند
Document doc = new Document();

// أضف صفحة إلى مجموعة صفحات ملف PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 2: الصورة المضافة

بعد ذلك ، سنضيف صورة إلى صفحة مستند PDF. استخدم الكود التالي:

```csharp
// قم بإنشاء مثيل صورة
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// اضبط عرض الصورة وارتفاعها بالنقاط
img. FixWidth = 100;
img. FixHeight = 100;

// ضبط نوع الصورة على غير معروف (غير معروف)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// المسار إلى ملف مصدر الصورة
img.File = dataDir + "aspose-logo.jpg";

// أضف الصورة إلى مجموعة فقرات الصفحة
page.Paragraphs.Add(img);
```

تأكد من توفير المسار الصحيح لملف الصورة المصدر.

## الخطوة 3: ضبط خصائص الصفحة

أخيرًا ، سنقوم بتعيين خصائص الصفحة ، بما في ذلك عرضها وارتفاعها. استخدم الكود التالي:

```csharp
// تعيين خصائص الصفحة
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### نموذج التعليمات البرمجية المصدر لـ Set Image Size باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن المستند
Document doc = new Document();
//إضافة صفحة إلى مجموعة صفحات من ملف PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// قم بإنشاء مثيل صورة
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// تعيين عرض الصورة وارتفاعها بالنقاط
img.FixWidth = 100;
img.FixHeight = 100;
// تعيين نوع الصورة كـ SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// مسار الملف المصدر
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//تعيين خصائص الصفحة
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// حفظ ملف PDF الناتج
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد نجحت في تعيين حجم الصورة في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لضبط حجم الصور في ملفات PDF.