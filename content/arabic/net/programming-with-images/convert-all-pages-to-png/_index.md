---
title: تحويل كافة الصفحات إلى PNG
linktitle: تحويل كافة الصفحات إلى PNG
second_title: Aspose.PDF لمرجع .NET API
description: يمكنك بسهولة تحويل جميع صفحات مستند PDF إلى ملفات PNG باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 60
url: /ar/net/programming-with-images/convert-all-pages-to-png/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل جميع صفحات مستند PDF إلى ملفات PNG باستخدام Aspose.PDF لـ .NET. تأكد من أنك قمت بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود الذي يحتوي على المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

في هذه الخطوة، سنقوم بفتح مستند PDF باستخدام الملف`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ وتمرير المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
```

## الخطوة 3: تحويل كل صفحة إلى PNG

 في هذه الخطوة، سنراجع كل صفحة من مستند PDF ونقوم بتحويلها إلى ملفات PNG فردية. سوف نستخدم أ`for` حلقة للتكرار عبر جميع الصفحات.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // قم بإنشاء دفق لحفظ صورة PNG
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // قم بإنشاء جهاز PNG بالسمات المحددة
         // العرض، الارتفاع، الدقة، الجودة
         // الجودة [0-100]، 100 هو الحد الأقصى
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
        
         // تحويل صفحة معينة وحفظ الصورة في الدفق
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
		// قم بإنشاء جهاز PNG بالسمات المحددة
		// العرض، الارتفاع، الدقة، الجودة
		// الجودة [0-100]، 100 هو الحد الأقصى
		// إنشاء كائن القرار
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		//تحويل صفحة معينة وحفظ الصورة للبث
		pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// إغلاق الدفق
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to PNG successfully!");
```

## خاتمة

تهنئة ! لقد نجحت في تحويل كافة صفحات مستند PDF إلى ملفات PNG باستخدام Aspose.PDF لـ .NET. يتم حفظ ملفات PNG الفردية في الدليل المحدد. يمكنك الآن استخدام ملفات PNG هذه في مشاريعك أو تطبيقاتك.

### الأسئلة الشائعة

#### س: ما هو PNG، ولماذا أحتاج إلى تحويل صفحات PDF إلى ملفات PNG؟

ج: PNG (رسومات الشبكة المحمولة) هو تنسيق صور مستخدم على نطاق واسع ومعروف بضغطه بدون فقدان البيانات ودعمه للخلفيات الشفافة. يمكن أن يكون تحويل صفحات PDF إلى تنسيق PNG مفيدًا للحفاظ على جودة الصورة وتسهيل معالجة الصور.

#### س: كيف يساعد Aspose.PDF for .NET في تحويل صفحات PDF إلى ملفات PNG؟

ج: يوفر Aspose.PDF for .NET عملية مبسطة لتحويل كل صفحة من مستند PDF إلى ملفات PNG فردية، مما يجعل عملية التحويل فعالة وسهلة الاستخدام.

#### س: لماذا يعد تحديد دليل المستند أمرًا بالغ الأهمية في عملية تحويل PDF إلى PNG؟

ج: يضمن تحديد دليل المستند تحديد موقع مستند PDF بشكل صحيح، ويتم حفظ ملفات PNG الناتجة في مسار الإخراج المطلوب.

#### س: كيف يمكنني فتح مستند PDF باستخدام Aspose.PDF لـ .NET في عملية التحويل من PDF إلى PNG؟

 ج: استخدم`Document` فئة لفتح مستند PDF، الذي يعمل كمدخل لعملية التحويل.

#### س: كيف يتم تحويل كل صفحة PDF إلى ملفات PNG فردية؟

 ج: أ`for` تتكرر التكرارات خلال كل صفحة من مستند PDF. لكل صفحة، يتم إنشاء صورة PNG باستخدام`PngDevice`، ويتم حفظ الصورة الناتجة في دليل الإخراج المحدد.

#### س: هل يمكنني تخصيص سمات ملفات PNG أثناء عملية التحويل؟

ج: نعم، يمكنك تخصيص سمات مثل العرض والارتفاع والدقة وجودة الصورة لملفات PNG لتناسب احتياجاتك الخاصة.

#### س: هل يتم دعم المعالجة المجمعة لتحويل مستندات PDF متعددة إلى ملفات PNG؟

ج: على الرغم من أن مقتطف التعليمات البرمجية المقدم مصمم لمستندات PDF الفردية، إلا أنه يمكنك تنفيذ المعالجة المجمعة للتعامل مع ملفات PDF متعددة.

#### س: كيف يمكنني الاستفادة من ملفات PNG التي تم إنشاؤها في مشاريعي أو تطبيقاتي؟

ج: يمكن دمج ملفات PNG التي تم إنشاؤها من خلال هذه العملية بسلاسة في مشاريعك أو تطبيقاتك، مما يوفر أصول صور متعددة الاستخدامات لأغراض مختلفة.

#### س: ما هي المزايا التي يقدمها تنسيق PNG مقارنة بتنسيقات الصور الأخرى؟

ج: يدعم تنسيق PNG الضغط بدون فقدان البيانات والشفافية وجودة الصورة العالية، مما يجعله مناسبًا للصور ذات الحواف الحادة والنصوص والمناطق ذات الألوان الموحدة.