---
title: تحويل إلى BMP
linktitle: تحويل إلى BMP
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل ملفات PDF بسهولة إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 90
url: /ar/net/programming-with-images/convert-to-bmp/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: تحويل كل صفحة إلى BMP

 في هذه الخطوة ، سنتصفح كل صفحة من صفحات مستند PDF ونحولها إلى صور BMP فردية. سوف نستخدم ملف`for`حلقة للتكرار خلال جميع الصفحات.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // قم بإنشاء دفق لحفظ صورة BMP
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // قم بإنشاء كائن حل
         Resolution resolution = new Resolution(300);
        
         // قم بإنشاء جهاز BMP بالسمات المحددة
         //العرض ، الارتفاع ، الدقة ، حجم الصفحة
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // قم بتحويل صفحة معينة وحفظ الصورة في الدفق
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // أغلق الدفق
         imageStream.Close();
     }
}
```

### عينة من التعليمات البرمجية المصدر للتحويل إلى BMP باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		// إنشاء كائن القرار
		Resolution resolution = new Resolution(300);
		// إنشاء جهاز BMP بسمات محددة
		// العرض ، الارتفاع ، الدقة ، حجم الصفحة
		BmpDevice bmpDevice = new BmpDevice(resolution);
		// قم بتحويل صفحة معينة وحفظ الصورة للدفق
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// إغلاق الدفق
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## خاتمة

تهنئة ! لقد نجحت في تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET. يتم حفظ صور BMP في الدليل المحدد. يمكنك الآن استخدام هذه الصور في مشاريعك أو تطبيقاتك.