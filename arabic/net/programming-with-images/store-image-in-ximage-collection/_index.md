---
title: تخزين الصورة في مجموعة XImage
linktitle: تخزين الصورة في مجموعة XImage
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتخزين صورة في مجموعة XImage باستخدام Aspose.PDF for .NET.
type: docs
weight: 290
url: /ar/net/programming-with-images/store-image-in-ximage-collection/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تخزين صورة في مجموعة XImage باستخدام Aspose.PDF لـ .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تهيئة مستند PDF

للبدء ، استخدم الكود التالي لتهيئة مستند PDF جديد:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتهيئة المستند
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## الخطوة 2: إضافة الصورة إلى مجموعة XImage

بعد ذلك ، سنضيف الصورة إلى مجموعة XImage لمستند PDF. استخدم الكود التالي:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

تأكد من توفير المسار الصحيح لملف الصورة المصدر.

## الخطوة 3: وضع الصورة على الصفحة

الآن دعنا نضع الصورة على صفحة وثيقة PDF. استخدم الكود التالي:

```csharp
page. Contents. Add(new GSave());

// ضبط الإحداثيات
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//باستخدام عامل التشغيل ConcatenateMatrix: حدد كيفية وضع الصورة
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

سيؤدي هذا إلى وضع الصورة في الإحداثيات المحددة على الصفحة.

## الخطوة 4: حفظ مستند PDF

أخيرًا ، سنقوم بحفظ مستند PDF المحدث. استخدم الكود التالي:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

تأكد من توفير المسار المطلوب واسم الملف لمستند PDF النهائي.

### نموذج التعليمات البرمجية المصدر لـ Store Image In XImage Collection باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة المستند
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// ضبط الإحداثيات
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//باستخدام عامل ConcatenateMatrix (مصفوفة متسلسلة): يحدد كيفية وضع الصورة
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## خاتمة

تهنئة ! لقد نجحت في تخزين صورة في مجموعة XImage باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لمعالجة الصور وتخصيصها في ملفات PDF.