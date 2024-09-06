---
title: إنشاء صور مصغرة في ملف PDF
linktitle: إنشاء صور مصغرة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: قم بإنشاء صورة مصغرة بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 100
url: /ar/net/programming-with-images/create-thumbnail-images/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية إنشاء صورة مصغرة في ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من إعداد البيئة الخاصة بك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستندات

قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يحتوي على ملفات PDF الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: الحصول على أسماء جميع ملفات PDF الموجودة في الدليل

 في هذه الخطوة، سنقوم باسترجاع أسماء جميع ملفات PDF الموجودة في الدليل المحدد باستخدام لغة C#`Directory`سيتم تخزين الملفات في مجموعة من السلاسل.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## الخطوة 3: تصفح جميع ملفات PDF وصفحاتها

 في هذه الخطوة، سنراجع جميع ملفات PDF وصفحاتها لإنشاء صور مصغرة. سنستخدم`for` حلقة لتكرار كافة الملفات.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // افتح مستند PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // قم بمراجعة كافة صفحات المستند
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // إنشاء تدفق لحفظ الصورة المصغرة
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //إنشاء كائن الدقة
             Resolution resolution = new Resolution(300);
            
             // إنشاء جهاز JPEG بالسمات المحددة
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // تحويل صفحة معينة وحفظ الصورة في الدفق
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // اغلاق الدفق
             imageStream.Close();
         }
     }
}
```

### عينة من كود المصدر لإنشاء صور مصغرة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// استرداد أسماء جميع ملفات PDF الموجودة في دليل معين
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// قم بالتكرار خلال جميع إدخالات الملفات الموجودة في المصفوفة
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//فتح المستند
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//إنشاء كائن الدقة
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = جديد JpegDevice(500، 700، الدقة، 100)؛
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

تهانينا! لقد نجحت في إنشاء صور مصغرة من ملفات PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ الصور المصغرة في الدليل المحدد. يمكنك الآن استخدام هذه الصور المصغرة لعرض معاينة مرئية لملفات PDF الخاصة بك.

### الأسئلة الشائعة حول إنشاء صور مصغرة في ملف PDF

#### س: ما هو الغرض من إنشاء صور مصغرة من ملفات PDF باستخدام Aspose.PDF لـ .NET؟

أ: إن إنشاء صور مصغرة من ملفات PDF يسمح لك بإنشاء معاينات بصرية صغيرة لكل صفحة في ملف PDF، وهو ما قد يكون مفيدًا لمعاينة المحتوى والتنقل عبره بسرعة.

#### س: كيف يسهل Aspose.PDF for .NET إنشاء الصور المصغرة من ملفات PDF؟

 أ: يوفر Aspose.PDF لـ .NET عملية خطوة بخطوة لفتح مستندات PDF، والتنقل عبر صفحاتها، وإنشاء صور مصغرة، وحفظها في دليل محدد باستخدام`JpegDevice` فصل.

#### س: لماذا من المهم تحديد دليل المستند قبل البدء في إنشاء الصور المصغرة؟

أ: تحديد دليل المستند يضمن تحديد موقع ملفات PDF بشكل صحيح، كما يضمن حفظ الصور المصغرة الناتجة في مسار الإخراج المطلوب.

####  س: كيف يتم ذلك؟`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 أ: ال`Document` تتيح لك الفئة فتح مستندات PDF ومعالجتها. في هذه الحالة، يتم استخدامها لتحميل ملفات PDF التي سيتم إنشاء الصور المصغرة منها.

####  س: ما هو الدور الذي يلعبه`JpegDevice` class play in the creation of thumbnail images?

 أ: ال`JpegDevice` تتولى الفئة تحويل صفحات PDF إلى صور JPEG، والتي تُستخدم كصور مصغرة. وهي تسمح لك بتحديد سمات مثل العرض والارتفاع والدقة والجودة.

#### س: كيف يتم تحويل كل صفحة من مستند PDF إلى صورة مصغرة فردية؟

 أ: متداخلة`for` يتم استخدام الحلقة للتكرار خلال كل ملف PDF وصفحاته. لكل صفحة، يتم إنشاء جهاز JPEG بسمات محددة، ويتم`Process` يتم استخدام الطريقة لتحويل الصفحة إلى صورة مصغرة وحفظها في التدفق.

#### س: هل يمكنني تعديل دقة أو جودة الصور المصغرة الناتجة أثناء عملية الإنشاء؟

ج: نعم، يمكنك تعديل السمات مثل الدقة والعرض والارتفاع والجودة من خلال تكوين`JpegDevice` الكائن قبل تحويل كل صفحة.

#### س: كيف يمكنني الاستفادة من الصور المصغرة التي تم إنشاؤها في مشاريعي أو تطبيقاتي بعد عملية الإنشاء؟

أ: يمكن استخدام الصور المصغرة الناتجة لتوفير معاينة بصرية لملفات PDF، مما يساعد المستخدمين على تحديد المحتوى والتنقل عبره بسرعة.

#### :هل هناك حد لعدد الصور المصغرة التي يمكن إنشاؤها من ملفات PDF باستخدام عملية الإنشاء هذه؟

ج: يعتمد عدد الصور المصغرة التي يتم إنشاؤها على عدد الصفحات في كل مستند PDF. سيتم تحويل كل صفحة إلى صورة مصغرة منفصلة.