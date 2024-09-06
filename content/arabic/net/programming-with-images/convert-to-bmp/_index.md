---
title: تحويل إلى BMP
linktitle: تحويل إلى BMP
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك تحويل PDF إلى صور BMP فردية بسهولة باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 90
url: /ar/net/programming-with-images/convert-to-bmp/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET. تأكد من إعداد البيئة الخاصة بك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستندات

قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

 في هذه الخطوة سوف نقوم بفتح مستند PDF باستخدام`Document` فئة Aspose.PDF. استخدم`Document` منشئ ومرر المسار إلى مستند PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: تحويل كل صفحة إلى BMP

 في هذه الخطوة، سننتقل إلى كل صفحة من مستند PDF ونحولها إلى صور BMP فردية. سنستخدم`for` حلقة لتكرار جميع الصفحات.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // إنشاء دفق لحفظ صورة BMP
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         //إنشاء كائن الدقة
         Resolution resolution = new Resolution(300);
        
         // إنشاء جهاز BMP بالسمات المحددة
         // العرض، الارتفاع، الدقة، حجم الصفحة
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // تحويل صفحة معينة وحفظ الصورة في الدفق
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // اغلاق الدفق
         imageStream.Close();
     }
}
```

### عينة من كود المصدر لتحويل إلى BMP باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		// إنشاء كائن الدقة
		Resolution resolution = new Resolution(300);
		// إنشاء جهاز BMP بالسمات المحددة
		// العرض، الارتفاع، الدقة، حجم الصفحة
		BmpDevice bmpDevice = new BmpDevice(resolution);
		// تحويل صفحة معينة وحفظ الصورة للبث
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// إغلاق الدفق
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## خاتمة

تهانينا! لقد نجحت في تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET. يتم حفظ صور BMP في الدليل المحدد. يمكنك الآن استخدام هذه الصور في مشاريعك أو تطبيقاتك.

### الأسئلة الشائعة

#### س: ما هو الغرض من تحويل ملف PDF إلى صور BMP فردية باستخدام Aspose.PDF لـ .NET؟

أ: تحويل ملف PDF إلى صور BMP فردية يسمح لك باستخراج كل صفحة من ملف PDF كصورة منفصلة بتنسيق BMP، وهو ما قد يكون مفيدًا لأغراض التصور والمعالجة المختلفة.

#### س: كيف يسهل Aspose.PDF for .NET تحويل ملف PDF إلى صور BMP؟

ج: يوفر Aspose.PDF لـ .NET عملية خطوة بخطوة لفتح مستند PDF، والتنقل عبر كل صفحة، وإنشاء جهاز BMP، وتحويل الصفحة إلى صورة BMP، وحفظها في دليل محدد.

#### س: لماذا من المهم تحديد دليل المستند قبل البدء في عملية التحويل؟

أ: تحديد دليل المستند يضمن أن مستند PDF موجود في مكانه الصحيح وأن صور BMP الناتجة يتم حفظها في مسار الإخراج المطلوب.

####  س: كيف يتم ذلك؟`Document` class in Aspose.PDF for .NET help in the conversion process?

 أ: ال`Document` تتيح لك الفئة فتح مستندات PDF ومعالجتها وحفظها. في هذه الحالة، يتم استخدامها لتحميل مستند PDF الذي تريد تحويله إلى صور BMP.

####  س: ما هو الدور الذي يلعبه`BmpDevice` class play in the conversion process?

 أ: ال`BmpDevice`تساعد الفئة في تحويل صفحات PDF إلى صور BMP. فهي تسمح لك بتحديد سمات مثل العرض والارتفاع والدقة وحجم الصفحة لصور BMP الناتجة.

#### س: كيف يتم تحويل كل صفحة من مستند PDF إلى صورة BMP فردية؟

 أ: أ`for` يتم استخدام الحلقة للتكرار عبر كل صفحة من مستند PDF. لكل صفحة، يتم إنشاء جهاز BMP بخصائص محددة، ويتم`Process` يتم استخدام الطريقة لتحويل الصفحة إلى صورة BMP وحفظها في التدفق.

#### س: هل يمكنني تعديل الدقة أو السمات الأخرى لصور BMP الناتجة أثناء عملية التحويل؟

 ج: نعم، يمكنك تعديل السمات مثل الدقة والعرض والارتفاع وحجم الصفحة من خلال تكوين`BmpDevice` الكائن قبل تحويل كل صفحة.

#### س: كيف يمكنني الاستفادة من صور BMP الناتجة في مشاريعي أو تطبيقاتي بعد التحويل؟

أ: يمكن دمج صور BMP الناتجة في مشاريعك أو تطبيقاتك لأغراض مختلفة، مثل تضمينها في التقارير أو العروض التقديمية أو تطبيقات الويب.

#### س: هل هناك حد لعدد صور BMP التي يمكن إنشاؤها من ملف PDF باستخدام عملية التحويل هذه؟

ج: يعتمد عدد صور BMP التي يتم إنشاؤها على عدد الصفحات في مستند PDF. سيتم تحويل كل صفحة إلى صورة BMP منفصلة.