---
title: الصورة في التذييل
linktitle: الصورة في التذييل
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة صورة في قسم التذييل لمستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 130
url: /ar/net/programming-with-stamps-and-watermarks/image-in-footer/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية إضافة صورة في قسم التذييل في مستند PDF باستخدام Aspose.PDF for .NET. سنستخدم الكود المصدري C # المقدم لفتح مستند PDF موجود وإنشاء مخزن مؤقت للصور وتعيين خصائصه وإضافته إلى جميع صفحات مستند PDF.

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
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: إنشاء وإضافة الصورة في قسم التذييل

الآن بعد أن تم تحميل مستند PDF ، يمكننا إنشاء ختم صورة وإضافته إلى جميع صفحات المستند. إليك الطريقة:

```csharp
// إنشاء المخزن المؤقت للإطار
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// تعيين خصائص المخزن المؤقت للصورة
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//إضافة صورة عازلة لجميع الصفحات
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

يُنشئ الكود أعلاه مخزنًا مؤقتًا للصور من ملف "aspose-logo.jpg" ويضبط خصائصه ، مثل الهامش السفلي والمحاذاة الأفقية والعمودية. ثم يتم إضافة المخزن المؤقت للصور إلى جميع صفحات مستند PDF.

## الخطوة 4: حفظ مستند PDF المعدل

بمجرد إضافة الصورة إلى قسم التذييل ، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Image In Footer باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// إنشاء تذييل
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// تعيين خصائص الطابع
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// إضافة تذييل في جميع الصفحات
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// احفظ ملف PDF المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة صورة في قسم التذييل لمستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تخصيص تذييلات مستندات PDF الخاصة بك عن طريق إضافة الصور.
