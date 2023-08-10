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

في هذه الخطوة ، سنتصفح كل صفحة من صفحات مستند PDF ونحولها إلى صور BMP فردية. سوف نستخدم ملف`for` حلقة للتكرار خلال جميع الصفحات.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // قم بإنشاء دفق لحفظ صورة BMP
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // قم بإنشاء كائن حل
         Resolution resolution = new Resolution(300);
        
         // قم بإنشاء جهاز BMP بالسمات المحددة
         // العرض ، الارتفاع ، الدقة ، حجم الصفحة
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
		//قم بتحويل صفحة معينة وحفظ الصورة للدفق
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// إغلاق الدفق
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## خاتمة

تهنئة ! لقد نجحت في تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET. يتم حفظ صور BMP في الدليل المحدد. يمكنك الآن استخدام هذه الصور في مشاريعك أو تطبيقاتك.

### التعليمات

#### س: ما هو الغرض من تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET؟

ج: يتيح لك تحويل ملف PDF إلى صور BMP فردية استخراج كل صفحة من ملف PDF كصورة منفصلة بتنسيق BMP ، والتي يمكن أن تكون مفيدة لأغراض التصور والمعالجة المختلفة.

#### س: كيف يسهل Aspose.PDF for .NET تحويل ملف PDF إلى صور BMP؟

ج: يوفر Aspose.PDF for .NET عملية خطوة بخطوة لفتح مستند PDF ، والتكرار خلال كل صفحة ، وإنشاء جهاز BMP ، وتحويل الصفحة إلى صورة BMP ، وحفظها في دليل محدد.

#### س: ما سبب أهمية تحديد دليل المستند قبل بدء عملية التحويل؟

ج: تحديد دليل المستند يضمن أن مستند PDF موجود بشكل صحيح وأن صور BMP الناتجة يتم حفظها في مسار الإخراج المطلوب.

####  س: كيف يعمل ملف`Document` class in Aspose.PDF for .NET help in the conversion process?

 ج: إن`Document` تسمح لك class بفتح مستندات PDF ومعالجتها وحفظها. في هذه الحالة ، يتم استخدامه لتحميل مستند PDF الذي تريد تحويله إلى صور BMP.

####  س: ما هو الدور الذي يقوم به`BmpDevice` class play in the conversion process?

 ج: إن`BmpDevice` تساعد الفئة على تحويل صفحات PDF إلى صور BMP. يسمح لك بتحديد سمات مثل العرض والارتفاع والدقة وحجم الصفحة لصور BMP الناتجة.

#### س: كيف يتم تحويل كل صفحة من صفحات مستند PDF إلى صورة BMP فردية؟

 ج: أ`for` حلقة تستخدم للتكرار خلال كل صفحة من وثيقة PDF. لكل صفحة ، يتم إنشاء جهاز BMP بسمات محددة ، ويتم إنشاء ملف`Process`يتم استخدام طريقة لتحويل الصفحة إلى صورة BMP وحفظها في الدفق.

#### س: هل يمكنني ضبط الدقة أو السمات الأخرى لصور BMP الناتجة أثناء عملية التحويل؟

 ج: نعم ، يمكنك تعديل سمات مثل الدقة والعرض والارتفاع وحجم الصفحة من خلال تكوين ملف`BmpDevice` قبل تحويل كل صفحة.

#### س: كيف يمكنني استخدام صور BMP التي تم إنشاؤها في مشاريعي أو تطبيقاتي بعد التحويل؟

ج: يمكن دمج صور BMP الناتجة في مشروعاتك أو تطبيقاتك لأغراض مختلفة ، مثل تضمينها في التقارير أو العروض التقديمية أو تطبيقات الويب.

#### س: هل هناك حد لعدد صور BMP التي يمكن إنشاؤها من ملف PDF باستخدام عملية التحويل هذه؟

ج: يعتمد عدد صور BMP التي تم إنشاؤها على عدد الصفحات في مستند PDF. سيتم تحويل كل صفحة إلى صورة BMP منفصلة.