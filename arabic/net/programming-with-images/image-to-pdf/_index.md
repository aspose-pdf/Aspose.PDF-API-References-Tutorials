---
title: صورة إلى PDF
linktitle: صورة إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل الصورة بسهولة إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 180
url: /ar/net/programming-with-images/image-to-pdf/
---

Aspose.PDF for .NET مكتبة قوية تتيح للمطورين إنشاء مستندات PDF ومعالجتها وتحويلها باستخدام C # أو أي لغة .NET. في هذا البرنامج التعليمي ، سنوجهك خلال عملية تحويل صورة إلى PDF باستخدام Aspose.PDF لـ .NET.

## الخطوة الأولى: تهيئة البيئة

قبل أن نبدأ ، تأكد من تثبيت Aspose.PDF for .NET على نظامك. يمكنك تنزيله وتثبيته من موقع Aspose الرسمي. بمجرد التثبيت ، قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.

## الخطوة 2: استيراد المكتبات المطلوبة

لاستخدام Aspose.PDF لـ .NET في مشروعك ، تحتاج إلى استيراد المكتبات الضرورية. أضف عبارات الاستخدام التالية في بداية ملف C # الخاص بك:

```csharp
using Aspose.Pdf;
using System.IO;
using System.Drawing;
```

## الخطوة 3: تهيئة كائن المستند

 في كود C # ، تتمثل الخطوة الأولى في تهيئة ملف`Document` هدف. يمثل هذا الكائن مستند PDF الذي سننشئه. أضف الكود التالي إلى مشروعك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي حيث تريد حفظ ملف PDF.

## الخطوة 4: إضافة صفحة إلى المستند

 بعد ذلك ، نحتاج إلى إضافة صفحة إلى المستند. يتم تمثيل الصفحة بواسطة`Page` فصل. استخدم الكود التالي لإضافة صفحة إلى المستند:

```csharp
Page page = doc.Pages.Add();
```

 يقوم هذا الرمز بإنشاء صفحة جديدة وإضافتها إلى ملف`Pages` جمع الوثيقة.

## الخطوة الخامسة: تحميل ملف الصورة

 لتحويل صورة إلى PDF ، نحتاج أولاً إلى تحميل ملف الصورة المصدر. في هذا المثال ، نفترض أن ملف الصورة قد تم تسميته`aspose-logo.jpg` وهو موجود في نفس الدليل مثل ملف C # الخاص بك. استخدم الكود التالي لتحميل ملف الصورة:

```csharp
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
```

 تأكد من استبداله`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي لملف الصورة.

## الخطوة 6: ضبط الهوامش ومربع الاقتصاص

قبل إضافة الصورة إلى صفحة PDF ، يمكننا تخصيص تخطيط الصفحة. على سبيل المثال ، يمكننا ضبط الهوامش ومربع الاقتصاص لملاءمة أبعاد الصورة. استخدم الكود التالي لضبط إعدادات الصفحة:

```csharp
Bitmap b = new Bitmap(mystream);
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page

.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
```

تضمن هذه الإعدادات أن الصورة ستلائم الصفحة بدون أي هوامش إضافية.

## الخطوة 7: إنشاء كائن صورة

 الآن ، لنقم بإنشاء ملف`Aspose.Pdf.Image` كائن لعقد بيانات الصورة. أضف الكود التالي إلى مشروعك:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

سيمثل هذا الكائن الصورة التي نريد إضافتها إلى صفحة PDF.

## الخطوة 8: إضافة الصورة إلى الصفحة

 لإضافة الصورة إلى صفحة PDF ، نحتاج إلى تعيين بيانات الصورة إلى ملف`ImageStream` ممتلكات`Aspose.Pdf.Image`هدف. استخدم الكود التالي لإضافة الصورة:

```csharp
image1.ImageStream = mystream;
page.Paragraphs.Add(image1);
```

 هنا ، نقوم بتعيين دفق الصورة إلى ملف`ImageStream` الخاصية ثم قم بإضافة كائن الصورة إلى ملف`Paragraphs` مجموعة من الصفحة.

## الخطوة 9: حفظ ملف PDF

بمجرد أن نضيف الصورة إلى صفحة PDF ، يمكننا حفظ ملف PDF الناتج. استخدم الكود التالي لحفظ الملف:

```csharp
dataDir = dataDir + "ImageToPDF_out.pdf";
doc.Save(dataDir);
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع دليل الإخراج المطلوب واسم الملف.

## الخطوة 10: إغلاق دفق الذاكرة

بعد حفظ ملف PDF ، من المهم إغلاق تدفق الذاكرة لتحرير موارد النظام. أضف الكود التالي لإغلاق تدفق الذاكرة:

```csharp
mystream. Close();
```

## تشغيل الكود والتحقق من المخرجات

لقد أكملت الآن تنفيذ التعليمات البرمجية. قم بتشغيل الكود وتحقق من أن الصورة قد تم تحويلها بنجاح إلى PDF. يجب حفظ ملف الإخراج في الدليل المحدد.


### نموذج التعليمات البرمجية المصدر لـ Image to PDF باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن المستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة الصفحات من الوثيقة
Page page = doc.Pages.Add();
//قم بتحميل ملف الصورة المصدر إلى كائن البث
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
// إنشاء كائن BitMap مع دفق الصور المحمّل
Bitmap b = new Bitmap(mystream);
// قم بتعيين الهوامش بحيث تناسب الصورة ، وما إلى ذلك.
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
// قم بإنشاء كائن صورة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// أضف الصورة إلى مجموعة فقرات القسم
page.Paragraphs.Add(image1);
// تعيين دفق ملف الصورة
image1.ImageStream = mystream;
dataDir = dataDir + "ImageToPDF_out.pdf";
// حفظ ملف PDF الناتج
doc.Save(dataDir);
// أغلق memoryStream الكائن
mystream.Close();
Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل صورة إلى PDF باستخدام Aspose.PDF لـ .NET. قمنا بتغطية العملية خطوة بخطوة ، بما في ذلك إعداد البيئة ، واستيراد المكتبات ، وتهيئة كائن المستند ، وتحميل ملف الصورة ، وتعيين الهوامش ومربع الاقتصاص ، وإضافة الصورة إلى الصفحة ، وحفظ ملف PDF ، وإغلاق تيار الذاكرة. باتباع هذه الخطوات ، يمكنك بسهولة تحويل الصور إلى PDF في تطبيقات .NET الخاصة بك.