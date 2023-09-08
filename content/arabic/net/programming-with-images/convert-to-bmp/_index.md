---
title: تحويل إلى BMP
linktitle: تحويل إلى BMP
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل PDF بسهولة إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 90
url: /ar/net/programming-with-images/convert-to-bmp/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET. تأكد من أنك قمت بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود الذي يحتوي على المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

في هذه الخطوة، سنقوم بفتح مستند PDF باستخدام الملف`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ وتمرير المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: تحويل كل صفحة إلى BMP

في هذه الخطوة، سنراجع كل صفحة من مستند PDF ونقوم بتحويلها إلى صور BMP فردية. سوف نستخدم أ`for` حلقة للتكرار عبر جميع الصفحات.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // قم بإنشاء دفق لحفظ صورة BMP
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // إنشاء كائن القرار
         Resolution resolution = new Resolution(300);
        
         // قم بإنشاء جهاز BMP بالسمات المحددة
         // العرض، الارتفاع، الدقة، حجم الصفحة
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // تحويل صفحة معينة وحفظ الصورة في الدفق
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // أغلق الدفق
         imageStream.Close();
     }
}
```

### نموذج التعليمات البرمجية المصدر للتحويل إلى BMP باستخدام Aspose.PDF لـ .NET 
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
		// إنشاء جهاز BMP بالسمات المحددة
		// العرض، الارتفاع، الدقة، حجم الصفحة
		BmpDevice bmpDevice = new BmpDevice(resolution);
		//تحويل صفحة معينة وحفظ الصورة للبث
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// إغلاق الدفق
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## خاتمة

تهنئة ! لقد نجحت في تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET. يتم حفظ صور BMP في الدليل المحدد. يمكنك الآن استخدام هذه الصور في مشاريعك أو تطبيقاتك.

### الأسئلة الشائعة

#### س: ما هو الغرض من تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET؟

ج: يتيح لك تحويل ملف PDF إلى صور BMP فردية استخراج كل صفحة من ملف PDF كصورة منفصلة بتنسيق BMP، وهو ما يمكن أن يكون مفيدًا لمختلف أغراض التصور والمعالجة.

#### س: كيف يسهل Aspose.PDF for .NET تحويل ملف PDF إلى صور BMP؟

ج: يوفر Aspose.PDF for .NET عملية خطوة بخطوة لفتح مستند PDF، والتكرار خلال كل صفحة، وإنشاء جهاز BMP، وتحويل الصفحة إلى صورة BMP، وحفظها في دليل محدد.

#### س: لماذا من المهم تحديد دليل المستند قبل بدء عملية التحويل؟

ج: يضمن تحديد دليل المستند تحديد موقع مستند PDF بشكل صحيح وحفظ صور BMP الناتجة في مسار الإخراج المطلوب.

####  س: كيف`Document` class in Aspose.PDF for .NET help in the conversion process?

 ج: ال`Document` يتيح لك الفصل فتح مستندات PDF ومعالجتها وحفظها. في هذه الحالة، يتم استخدامه لتحميل مستند PDF الذي تريد تحويله إلى صور BMP.

####  س: ما هو الدور الذي يقوم به`BmpDevice` class play in the conversion process?

 ج: ال`BmpDevice` يساعد الفصل على تحويل صفحات PDF إلى صور BMP. يسمح لك بتحديد سمات مثل العرض والارتفاع والدقة وحجم الصفحة لصور BMP الناتجة.

#### س: كيف يتم تحويل كل صفحة من مستند PDF إلى صورة BMP فردية؟

 ج: أ`for` يتم استخدام الحلقة للتكرار خلال كل صفحة من مستند PDF. لكل صفحة، يتم إنشاء جهاز BMP مع سمات محددة، و`Process`يتم استخدام الطريقة لتحويل الصفحة إلى صورة BMP وحفظها في الدفق.

#### س: هل يمكنني ضبط الدقة أو السمات الأخرى لصور BMP الناتجة أثناء عملية التحويل؟

 ج: نعم، يمكنك تعديل سمات مثل الدقة والعرض والارتفاع وحجم الصفحة عن طريق تكوين`BmpDevice` كائن قبل تحويل كل صفحة.

#### س: كيف يمكنني الاستفادة من صور BMP التي تم إنشاؤها في مشاريعي أو تطبيقاتي بعد التحويل؟

ج: يمكن دمج صور BMP الناتجة في مشاريعك أو تطبيقاتك لأغراض مختلفة، مثل تضمينها في التقارير أو العروض التقديمية أو تطبيقات الويب.

#### س: هل هناك أي حد لعدد صور BMP التي يمكن إنشاؤها من ملف PDF باستخدام عملية التحويل هذه؟

ج: يعتمد عدد صور BMP التي تم إنشاؤها على عدد الصفحات في مستند PDF. سيتم تحويل كل صفحة إلى صورة BMP منفصلة.