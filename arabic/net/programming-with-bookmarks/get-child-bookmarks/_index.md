---
title: احصل على إشارات مرجعية للأطفال
linktitle: احصل على إشارات مرجعية للأطفال
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على إشارات مرجعية فرعية لملفات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/programming-with-bookmarks/get-child-bookmarks/
---

يمكن أن يكون استرداد الإشارات المرجعية الفرعية من مستند PDF مفيدًا في استكشاف الهيكل الهرمي للإشارات المرجعية. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة الحصول على الإشارات المرجعية الفرعية باتباع التعليمات البرمجية المصدر التالية:

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
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## الخطوة 4: تصفح الإشارات المرجعية والإشارات المرجعية الفرعية

في هذه الخطوة ، سنقوم بتكرار جميع الإشارات المرجعية في المستند باستخدام ملف`foreach`حلقة. لكل إشارة مرجعية ، سنعرض المعلومات مثل العنوان والنمط المائل والأسلوب الغامق واللون. إذا كانت الإشارة المرجعية تحتوي على إشارات مرجعية فرعية ، فسنعرضها أيضًا. هذا هو الكود المقابل:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // تصفح المواقع الفرعية كذلك
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### عينة من التعليمات البرمجية المصدر للحصول على إشارات مرجعية تابعة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// حلقة من خلال جميع الإشارات المرجعية
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// هناك إشارات مرجعية فرعية ثم حلقة من خلال ذلك أيضًا
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة للحصول على إشارات مرجعية فرعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لاستكشاف الهيكل الهرمي للإشارات المرجعية والحصول على معلومات مفصلة حول كل إشارة مرجعية والإشارات المرجعية الفرعية الخاصة بها في مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.