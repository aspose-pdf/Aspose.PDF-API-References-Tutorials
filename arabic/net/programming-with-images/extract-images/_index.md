---
title: استخراج الصور
linktitle: استخراج الصور
second_title: Aspose.PDF لمرجع .NET API
description: استخرج الصور بسهولة من ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 120
url: /ar/net/programming-with-images/extract-images/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية استخراج الصور من ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## الخطوة 3: استخراج صورة معينة

 في هذه الخطوة ، سنقوم باستخراج صورة معينة من صفحة معينة. استخدم ال`Images` مجموعة من الصفحة`s `الموارد` للوصول إلى الصورة المطلوبة. في المثال أدناه ، نستخرج الصورة بالفهرس 1 من الصفحة الأولى.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## الخطوة 4: احفظ الصورة المستخرجة

 احفظ الصورة المستخرجة في ملف باستخدام امتداد`Save` طريقة`xImage`هدف. حدد مسار الإخراج وتنسيق الصورة (في هذا المثال نستخدم تنسيق JPEG).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## الخطوة 5: احفظ ملف PDF المحدث

 احفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`pdfDocument` هدف. حدد مسار الإخراج لملف PDF.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### عينة من التعليمات البرمجية المصدر لاستخراج الصور باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// استخراج صورة معينة
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// حفظ الصورة الناتجة
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// احفظ ملف PDF المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهنئة ! لقد نجحت في استخراج الصور من ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ الصورة المستخرجة في الدليل المحدد ويتم أيضًا حفظ ملف PDF المحدث. يمكنك الآن استخدام هذه الملفات لتلبية احتياجاتك الخاصة.