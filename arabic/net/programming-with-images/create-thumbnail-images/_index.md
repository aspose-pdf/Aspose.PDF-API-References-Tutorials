---
title: إنشاء صور مصغرة في ملف PDF
linktitle: إنشاء صور مصغرة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: أنشئ صورة مصغرة بسهولة في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 100
url: /ar/net/programming-with-images/create-thumbnail-images/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية إنشاء صورة مصغرة في ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل الذي يحتوي على ملفات PDF الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: احصل على أسماء جميع ملفات PDF في دليل

 في هذه الخطوة ، سنقوم باسترداد أسماء جميع ملفات PDF الموجودة في الدليل المحدد باستخدام ملفات C #`Directory` فصل. سيتم تخزين الملفات في مجموعة من السلاسل.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## الخطوة 3: تصفح جميع ملفات PDF وصفحاتها

 في هذه الخطوة ، سنتصفح جميع ملفات PDF وصفحاتها لإنشاء صور مصغرة. سوف نستخدم ملف`for` حلقة للتكرار خلال جميع الملفات.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //افتح مستند PDF
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
//استرجع أسماء جميع ملفات PDF في دليل معين
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

### الأسئلة الشائعة حول إنشاء صور مصغرة في ملف PDF

#### س: ما هو الغرض من إنشاء صور مصغرة من ملفات PDF باستخدام Aspose.PDF لـ .NET؟

ج: يتيح لك إنشاء صور مصغرة من ملفات PDF إنشاء معاينات مرئية صغيرة لكل صفحة في ملف PDF ، والتي يمكن أن تكون مفيدة لمعاينة المحتوى والتنقل خلاله بسرعة.

#### س: كيف يسهل Aspose.PDF for .NET إنشاء صور مصغرة من ملفات PDF؟

ج: يوفر Aspose.PDF for .NET عملية خطوة بخطوة لفتح مستندات PDF ، والتكرار خلال صفحاتهم ، وإنشاء صور مصغرة ، وحفظها في دليل محدد باستخدام`JpegDevice` فصل.

#### س: ما سبب أهمية تحديد دليل المستند قبل البدء في إنشاء الصور المصغرة؟

ج: تحديد دليل المستند يضمن أن ملفات PDF موجودة بشكل صحيح ، ويتم حفظ الصور المصغرة الناتجة في مسار الإخراج المطلوب.

####  س: كيف يعمل ملف`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 ج: إن`Document` تسمح لك class بفتح مستندات PDF ومعالجتها. في هذه الحالة ، يتم استخدامه لتحميل ملفات PDF التي سيتم إنشاء الصور المصغرة منها.

####  س: ما هو الدور الذي يقوم به`JpegDevice` class play in the creation of thumbnail images?

 ج: إن`JpegDevice` class هي المسؤولة عن تحويل صفحات PDF إلى صور JPEG ، والتي تستخدم كصور مصغرة. يسمح لك بتحديد سمات مثل العرض والارتفاع والدقة والجودة.

#### س: كيف يتم تحويل كل صفحة من صفحات وثيقة PDF إلى صورة مصغرة فردية؟

 ج: متداخل`for`loop للتكرار خلال كل ملف PDF وصفحاته. لكل صفحة ، يتم إنشاء جهاز JPEG بسمات محددة ، ويتم إنشاء ملف`Process` يتم استخدام الطريقة لتحويل الصفحة إلى صورة مصغرة وحفظها في الدفق.

#### س: هل يمكنني ضبط دقة أو جودة الصور المصغرة الناتجة أثناء عملية الإنشاء؟

 ج: نعم ، يمكنك تعديل سمات مثل الدقة والعرض والارتفاع والجودة من خلال تكوين ملف`JpegDevice` قبل تحويل كل صفحة.

#### س: كيف يمكنني استخدام الصور المصغرة التي تم إنشاؤها في مشاريعي أو تطبيقاتي بعد عملية الإنشاء؟

ج: يمكن استخدام الصور المصغرة الناتجة لتوفير معاينة مرئية لملفات PDF ، مما يساعد المستخدمين على تحديد المحتوى والتنقل خلاله بسرعة.

#### : هل هناك حد لعدد الصور المصغرة التي يمكن إنشاؤها من ملفات PDF باستخدام عملية الإنشاء هذه؟

ج: يعتمد عدد الصور المصغرة التي يتم إنشاؤها على عدد الصفحات في كل مستند PDF. سيتم تحويل كل صفحة إلى صورة مصغرة منفصلة.