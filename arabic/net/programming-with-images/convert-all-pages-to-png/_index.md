---
title: تحويل كافة الصفحات إلى PNG
linktitle: تحويل كافة الصفحات إلى PNG
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل جميع صفحات مستند PDF بسهولة إلى ملفات PNG باستخدام Aspose.PDF for .NET.
type: docs
weight: 60
url: /ar/net/programming-with-images/convert-all-pages-to-png/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل جميع صفحات مستند PDF إلى ملفات PNG باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
```

## الخطوة 3: تحويل كل صفحة إلى PNG

 في هذه الخطوة ، سنتصفح كل صفحة من صفحات مستند PDF ونحولها إلى ملفات PNG فردية. سوف نستخدم ملف`for`حلقة للتكرار خلال جميع الصفحات.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     //قم بإنشاء دفق لحفظ صورة PNG
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // قم بإنشاء جهاز PNG بالسمات المحددة
         // العرض ، الارتفاع ، الدقة ، الجودة
         // الجودة [0-100] ، 100 هي الحد الأقصى
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
        
         // قم بتحويل صفحة معينة وحفظ الصورة في الدفق
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // أغلق الدفق
         imageStream.Close();
     }
}
```

### نموذج التعليمات البرمجية المصدر لتحويل كافة الصفحات إلى PNG باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
	{
		// قم بإنشاء جهاز PNG بسمات محددة
		// العرض ، الارتفاع ، الدقة ، الجودة
		// الجودة [0-100] ، 100 هي الحد الأقصى
		// إنشاء كائن القرار
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		// قم بتحويل صفحة معينة وحفظ الصورة للدفق
		pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// إغلاق الدفق
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to PNG successfully!");
```

## خاتمة

تهنئة ! لقد نجحت في تحويل جميع صفحات مستند PDF إلى ملفات PNG باستخدام Aspose.PDF لـ .NET. يتم حفظ ملفات PNG الفردية في الدليل المحدد. يمكنك الآن استخدام ملفات PNG هذه في مشاريعك أو تطبيقاتك.