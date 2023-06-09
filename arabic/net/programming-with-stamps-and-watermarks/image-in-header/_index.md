---
title: الصورة في العنوان
linktitle: الصورة في العنوان
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة صورة في قسم رأس مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 140
url: /ar/net/programming-with-stamps-and-watermarks/image-in-header/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية إضافة صورة في قسم رأس مستند PDF باستخدام Aspose.PDF for .NET. سنستخدم الكود المصدري C # المقدم لفتح مستند PDF موجود وإنشاء مخزن مؤقت للصور وتعيين خصائصه وإضافته إلى جميع صفحات مستند PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF الحالي

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند PDF الموجود
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: إنشاء وإضافة الصورة في قسم الرأس

الآن بعد أن تم تحميل مستند PDF ، يمكننا إنشاء مخزن مؤقت للصور وإضافته إلى جميع صفحات المستند كقسم رأس. إليك الطريقة:

```csharp
// إنشاء المخزن المؤقت للإطار
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// تعيين خصائص المخزن المؤقت للصورة
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

//إضافة صورة عازلة لجميع الصفحات
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

يقوم الكود أعلاه بإنشاء مخزن مؤقت للصور من ملف "aspose-logo.jpg" ويضبط خصائصه ، مثل الهامش العلوي والمحاذاة الأفقية والعمودية. ثم يتم إضافة ختم الصورة إلى جميع صفحات مستند PDF كقسم رأس.

## الخطوة 4: حفظ مستند PDF المعدل

بمجرد إضافة الصورة في قسم الرأس ، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Imagein Header باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// إنشاء رأس
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// تعيين خصائص الطابع
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// أضف العنوان في جميع الصفحات
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة صورة في قسم رأس مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تخصيص رؤوس مستندات PDF الخاصة بك عن طريق إضافة الصور.
