---
title: تحويل كافة الصفحات إلى EMF
linktitle: تحويل كافة الصفحات إلى EMF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل جميع صفحات مستند PDF بسهولة إلى ملفات EMF باستخدام Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/programming-with-images/convert-all-pages-to-emf/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل جميع صفحات مستند PDF إلى ملفات EMF (Enhanced Metafile) باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToEMF.pdf");
```

## الخطوة 3: تحويل كل صفحة إلى EMF

 في هذه الخطوة ، سنتصفح كل صفحة من صفحات مستند PDF ونحولها إلى ملفات EMF فردية. سوف نستخدم ملف`for`حلقة للتكرار خلال جميع الصفحات.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // قم بإنشاء دفق لحفظ صورة EMF
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
     {
         // قم بإنشاء كائن حل
         Resolution resolution = new Resolution(300);
        
         // قم بإنشاء جهاز EMF بالسمات المحددة
         // العرض والارتفاع والدقة
         EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
        
         // قم بتحويل صفحة معينة وحفظ الصورة في الدفق
         emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // أغلق الدفق
         imageStream.Close();
     }
}
```

### نموذج التعليمات البرمجية المصدر لتحويل كافة الصفحات إلى EMF باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir+ "ConvertAllPagesToEMF.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
	{
		// إنشاء كائن القرار
		Resolution resolution = new Resolution(300);
		// قم بإنشاء جهاز PNG بسمات محددة
		// العرض والارتفاع والدقة
		EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
		// قم بتحويل صفحة معينة وحفظ الصورة للدفق
		emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// إغلاق الدفق
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to EMF successfully!");
```

## خاتمة

تهنئة ! لقد نجحت في تحويل جميع صفحات مستند PDF إلى ملفات EMF باستخدام Aspose.PDF لـ .NET. يتم حفظ ملفات EMF الفردية في الدليل المحدد. يمكنك الآن استخدام ملفات EMF هذه في مشاريعك أو تطبيقاتك.