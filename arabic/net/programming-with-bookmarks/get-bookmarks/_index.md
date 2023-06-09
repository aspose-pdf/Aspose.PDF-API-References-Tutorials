---
title: احصل على الإشارات المرجعية
linktitle: احصل على الإشارات المرجعية
second_title: Aspose.PDF لمرجع .NET API
description: ضع إشارة مرجعية على ملفات PDF الخاصة بك بسهولة باستخدام Aspose.PDF for .NET.
type: docs
weight: 70
url: /ar/net/programming-with-bookmarks/get-bookmarks/
---

يمكن أن يكون استرداد الإشارات المرجعية من مستند PDF مفيدًا في تحليل بنية المستند ومعلومات التنقل. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة الحصول على الإشارات المرجعية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج الإشارات المرجعية منه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنقوم الآن بفتح مستند PDF الذي نريد استخراج الإشارات المرجعية منه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
```

## الخطوة 4: تصفح الإشارات المرجعية

في هذه الخطوة ، سنقوم بتكرار جميع الإشارات المرجعية في المستند باستخدام ملف`foreach` حلقة. لكل إشارة مرجعية ، سنعرض المعلومات مثل العنوان والنمط المائل والأسلوب الغامق واللون. هذا هو الكود المقابل:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
}
```

### نموذج التعليمات البرمجية المصدر للحصول على إشارات مرجعية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
// حلقة من خلال جميع الإشارات المرجعية
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
}
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة للحصول على إشارات مرجعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لتحليل الإشارات المرجعية واستخراج المعلومات المرتبطة بكل إشارة مرجعية في مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.