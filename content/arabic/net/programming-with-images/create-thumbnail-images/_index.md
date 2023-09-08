---
title: إنشاء صور مصغرة في ملف PDF
linktitle: إنشاء صور مصغرة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بإنشاء صورة مصغرة بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 100
url: /ar/net/programming-with-images/create-thumbnail-images/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية إنشاء صورة مصغرة في ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من أنك قمت بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يحتوي على ملفات PDF الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: احصل على أسماء جميع ملفات PDF في الدليل

 في هذه الخطوة، سوف نقوم باسترداد أسماء جميع ملفات PDF الموجودة في الدليل المحدد باستخدام لغة C#`Directory` فصل. سيتم تخزين الملفات في مجموعة من السلاسل.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## الخطوة 3: تصفح جميع ملفات PDF وصفحاتها

 في هذه الخطوة، سنستعرض جميع ملفات PDF وصفحاتها لإنشاء صور مصغرة. سوف نستخدم أ`for` حلقة للتكرار من خلال كافة الملفات.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //افتح مستند بي دي إف
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // انتقل من خلال جميع صفحات الوثيقة
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // قم بإنشاء دفق لحفظ الصورة المصغرة
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // إنشاء كائن القرار
             Resolution resolution = new Resolution(300);
            
             // قم بإنشاء جهاز JPEG بالسمات المحددة
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // تحويل صفحة معينة وحفظ الصورة في الدفق
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
//استرداد أسماء كافة ملفات PDF في دليل معين
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// التكرار من خلال جميع إدخالات الملفات في الصفيف
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
			//JpegDevice jpegDevice = new JpegDevice(500, 700,solution, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//تحويل صفحة معينة وحفظ الصورة للبث
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//إغلاق الدفق
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## خاتمة

تهنئة ! لقد نجحت في إنشاء صور مصغرة للصور من ملفات PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ الصور المصغرة للصور في الدليل المحدد. يمكنك الآن استخدام هذه الصور المصغرة لعرض معاينة مرئية لملفات PDF الخاصة بك.

### الأسئلة الشائعة لإنشاء صور مصغرة في ملف PDF

#### س: ما هو الغرض من إنشاء صور مصغرة من ملفات PDF باستخدام Aspose.PDF لـ .NET؟

ج: يتيح لك إنشاء صور مصغرة من ملفات PDF إنشاء معاينات مرئية صغيرة لكل صفحة في ملف PDF، والتي يمكن أن تكون مفيدة لمعاينة المحتوى والتنقل خلاله بسرعة.

#### س: كيف يسهل Aspose.PDF for .NET إنشاء صور مصغرة من ملفات PDF؟

ج: يوفر Aspose.PDF for .NET عملية خطوة بخطوة لفتح مستندات PDF، والتكرار عبر صفحاتها، وإنشاء صور مصغرة، وحفظها في دليل محدد باستخدام`JpegDevice` فصل.

#### س: لماذا من المهم تحديد دليل المستند قبل البدء في إنشاء الصور المصغرة؟

ج: يضمن تحديد دليل المستند تحديد موقع ملفات PDF بشكل صحيح، ويتم حفظ الصور المصغرة الناتجة في مسار الإخراج المطلوب.

####  س: كيف`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 ج: ال`Document` يتيح لك الفصل فتح مستندات PDF ومعالجتها. في هذه الحالة، يتم استخدامه لتحميل ملفات PDF التي سيتم إنشاء الصور المصغرة منها.

####  س: ما هو الدور الذي يقوم به`JpegDevice` class play in the creation of thumbnail images?

 ج: ال`JpegDevice` class هو المسؤول عن تحويل صفحات PDF إلى صور JPEG، والتي تستخدم كصور مصغرة. يسمح لك بتحديد سمات مثل العرض والارتفاع والدقة والجودة.

#### س: كيف يتم تحويل كل صفحة من مستند PDF إلى صورة مصغرة فردية؟

 ج: متداخلة`for`يتم استخدام الحلقة للتكرار خلال كل ملف PDF وصفحاته. لكل صفحة، يتم إنشاء جهاز JPEG بسمات محددة، و`Process` يتم استخدام الطريقة لتحويل الصفحة إلى صورة مصغرة وحفظها في الدفق.

#### س: هل يمكنني ضبط دقة أو جودة الصور المصغرة الناتجة أثناء عملية الإنشاء؟

 ج: نعم، يمكنك تعديل سمات مثل الدقة والعرض والارتفاع والجودة عن طريق تكوين`JpegDevice` كائن قبل تحويل كل صفحة.

#### س: كيف يمكنني الاستفادة من الصور المصغرة التي تم إنشاؤها في مشاريعي أو تطبيقاتي بعد عملية الإنشاء؟

ج: يمكن استخدام الصور المصغرة الناتجة لتوفير معاينة مرئية لملفات PDF، مما يساعد المستخدمين على التعرف على المحتوى والتنقل خلاله بسرعة.

#### : هل هناك أي حد لعدد الصور المصغرة التي يمكن إنشاؤها من ملفات PDF باستخدام عملية الإنشاء هذه؟

ج: يعتمد عدد الصور المصغرة التي يتم إنشاؤها على عدد الصفحات في كل مستند PDF. سيتم تحويل كل صفحة إلى صورة مصغرة منفصلة.