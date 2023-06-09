---
title: نص في العنوان
linktitle: نص في العنوان
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة نص في رأس مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 190
url: /ar/net/programming-with-stamps-and-watermarks/text-in-header/
---
في هذا البرنامج التعليمي ، سوف نتعلم كيفية إضافة نص في رأس مستند PDF باستخدام Aspose.PDF لـ .NET. اتبع الخطوات التالية:

## الخطوة الأولى: إعداد المشروع

تأكد من تثبيت Aspose.PDF لـ .NET وإنشاء مشروع C #.

## الخطوة 2: استيراد مساحات الأسماء

أضف مساحات الأسماء التالية إلى ملف المصدر C #:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: فتح المستند

افتح مستند PDF الحالي باستخدام المسار المتوفر:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 4: إنشاء نص الرأس

قم بإنشاء طابع نصي جديد بالنص الذي تريد إضافته في الرأس:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

يمكنك تخصيص النص عن طريق تغيير خصائصه مثل الهامش العلوي والمحاذاة الأفقية والمحاذاة الرأسية.

## الخطوة 5: أضف نص الرأس إلى جميع الصفحات

انتقل من خلال جميع صفحات مستند PDF وأضف طابع النص في الرأس:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## الخطوة 6: حفظ مستند PDF

بمجرد إضافة نص الرأس في جميع الصفحات ، احفظ مستند PDF المحدث:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث تريد حفظ مستند PDF.

### نموذج التعليمات البرمجية المصدر لـ Textin Header باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// إنشاء رأس
TextStamp textStamp = new TextStamp("Header Text");

// تعيين خصائص الطابع
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// أضف العنوان في جميع الصفحات
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// احفظ المستند المحدث
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة نص في رأس مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تخصيص الرؤوس الخاصة بك عن طريق إضافة نص إضافي إلى مستندات PDF الخاصة بك.
