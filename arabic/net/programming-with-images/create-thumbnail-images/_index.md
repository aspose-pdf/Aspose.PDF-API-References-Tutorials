---
title: إنشاء صور مصغرة
linktitle: إنشاء صور مصغرة
second_title: Aspose.PDF لمرجع .NET API
description: يمكنك إنشاء صور مصغرة بسهولة من ملفات PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 100
url: /ar/net/programming-with-images/create-thumbnail-images/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية إنشاء صور مصغرة من ملفات PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل الذي يحتوي على ملفات PDF الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: احصل على أسماء جميع ملفات PDF في دليل

 في هذه الخطوة ، سنقوم باسترداد أسماء جميع ملفات PDF الموجودة في الدليل المحدد باستخدام ملفات C #`Directory`فصل. سيتم تخزين الملفات في مجموعة من السلاسل.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## الخطوة 3: تصفح جميع ملفات PDF وصفحاتها

 في هذه الخطوة ، سنتصفح جميع ملفات PDF وصفحاتها لإنشاء صور مصغرة. سوف نستخدم ملف`for` حلقة للتكرار خلال جميع الملفات.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // افتح مستند PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // انتقل من خلال جميع صفحات المستند
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // إنشاء دفق لحفظ الصورة المصغرة
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // قم بإنشاء كائن حل
             Resolution resolution = new Resolution(300);
            
             // قم بإنشاء جهاز JPEG بالسمات المحددة
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // قم بتحويل صفحة معينة وحفظ الصورة في الدفق
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // أغلق الدفق
             imageStream.Close();
         }
     }
}
```

### نموذج التعليمات البرمجية المصدر لإنشاء صور مصغرة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// استرجع أسماء جميع ملفات PDF في دليل معين
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// كرر من خلال جميع إدخالات الملفات في مجموعة
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//افتح المستند
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//إنشاء كائن القرار
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = جديد JpegDevice (500 ، 700 ، القرار ، 100) ؛
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//قم بتحويل صفحة معينة وحفظ الصورة للدفق
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//إغلاق الدفق
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## خاتمة

تهنئة ! لقد نجحت في إنشاء صور مصغرة من ملفات PDF باستخدام Aspose.PDF for .NET. يتم حفظ الصور المصغرة في الدليل المحدد. يمكنك الآن استخدام هذه الصور المصغرة لعرض معاينة مرئية لملفات PDF الخاصة بك.