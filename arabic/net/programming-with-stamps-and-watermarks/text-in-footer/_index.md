---
title: نص في التذييل
linktitle: نص في التذييل
second_title: Aspose.PDF لمرجع .NET API
description: تعلم كيفية إضافة نص في تذييل مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 180
url: /ar/net/programming-with-stamps-and-watermarks/text-in-footer/
---
في هذا البرنامج التعليمي ، سنتعلم كيفية إضافة نص في تذييل مستند PDF باستخدام Aspose.PDF لـ .NET. اتبع الخطوات التالية:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 4: إنشاء نص التذييل

قم بإنشاء طابع نصي جديد بالنص الذي تريد إضافته في التذييل:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

يمكنك تخصيص النص عن طريق تغيير خصائصه مثل الهامش السفلي والمحاذاة الأفقية والمحاذاة الرأسية.

## الخطوة 5: إضافة نص تذييل لجميع الصفحات

انتقل إلى جميع صفحات مستند PDF وأضف طابع النص في التذييل:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## الخطوة 6: حفظ مستند PDF

بمجرد إضافة نص التذييل في جميع الصفحات ، احفظ مستند PDF المحدث:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث تريد حفظ مستند PDF.

### نموذج التعليمات البرمجية المصدر لـ Textin Footer باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// إنشاء تذييل
TextStamp textStamp = new TextStamp("Footer Text");

// تعيين خصائص الطابع
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// إضافة تذييل في جميع الصفحات
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// احفظ ملف PDF المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة نص في تذييل مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تخصيص تذييلاتك عن طريق إضافة نص إضافي إلى مستندات PDF الخاصة بك.
