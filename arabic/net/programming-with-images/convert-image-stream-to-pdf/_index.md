---
title: تحويل Image Stream إلى ملف PDF
linktitle: تحويل Image Stream إلى ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل تدفق الصور إلى ملف PDF بسهولة باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-images/convert-image-stream-to-pdf/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل تدفق الصور إلى ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث توجد صورتك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

 في هذه الخطوة ، سنقوم بإنشاء مثيل لـ`Document` كائن باستخدام مُنشئ فارغ لـ`Aspose.Pdf.Document` فصل.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## الخطوة 3: أضف صفحة إلى مستند PDF

 أضف صفحة إلى مستند PDF باستخدام امتداد`Add` طريقة`Pages` موضوع`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## الخطوة 4: اقرأ تدفق الصور

 في هذه الخطوة سنقوم بإنشاء ملف`FileStream` كائن لقراءة ملف الصورة من الدفق.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## الخطوة 5: اقرأ الصورة في مصفوفة بايت

 اقرأ الصورة من الدفق وقم بتخزينها في مصفوفة بايت باستخدام ملف`Read` طريقة`fs` هدف.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## الخطوة 6: إنشاء كائن MemoryStream من صفيف البايت

 إنشاء`MemoryStream` كائن من مجموعة البايت التي تحتوي على الصورة.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## الخطوة 7: إنشاء كائن صورة

 في هذه الخطوة ، سننشئ ملف`Image` كائن باستخدام`Aspose.Pdf.Image` فصل. حدد دفق الصورة باستخدام امتداد`ImageStream` الملكية وتمرير`ms` كائن أنشأناه سابقًا.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## الخطوة 8: أضف كائن الصورة إلى مجموعة الفقرات

 أضف ال`imageht` يعترض على`Paragraphs` جمع`sec` قسم.

```csharp
sec.Paragraphs.Add(imageht);
```

## الخطوة 9: احفظ مستند PDF

 احفظ مستند PDF باستخدام ملف`Save` طريقة`pdf1` هدف. حدد مسار الإخراج لملف PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## الخطوة 10: أغلق كائن MemoryStream

 أقفل ال`ms` كائن باستخدام`Close` طريقة للإفراج عن الموارد.

```csharp
ms. Close();
```

### عينة من التعليمات البرمجية المصدر لتحويل Image Stream إلى PDF باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//إنشاء مثيل المستند عن طريق استدعاء المُنشئ الفارغ الخاص به
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// أضف صفحة إلى مستند pdf
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// قم بإنشاء كائن FileStream لقراءة ملف الصورة
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// اقرأ الصورة في صفيف بايت
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// إنشاء كائن MemoryStream من مجموعة بايت الصورة
MemoryStream ms = new MemoryStream(data);
// قم بإنشاء كائن صورة
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// حدد مصدر الصورة كـ MemoryStream
imageht.ImageStream = ms;
// أضف كائن صورة إلى مجموعة الفقرات للقسم
sec.Paragraphs.Add(imageht);
// احفظ ملف PDF
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// أغلق كائن MemoryStream
ms.Close();
```

## خاتمة

تهنئة ! لقد نجحت في تحويل تدفق الصور إلى ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ ملف PDF الذي تم إنشاؤه في الدليل المحدد. يمكنك الآن استخدام ملف PDF هذا في مشاريعك أو تطبيقاتك.

### التعليمات

#### س: ما هو الغرض من تحويل تدفق الصور إلى ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يكون تحويل تدفق الصور إلى ملف PDF مفيدًا لدمج الصور في مستندات PDF أو إنشاء ملفات PDF قائمة على الصور أو تضمين الصور في المحتوى النصي.

#### س: كيف يساعد Aspose.PDF for .NET في تحويل تدفق الصور إلى ملف PDF؟

ج: يوفر Aspose.PDF for .NET عملية ملائمة وتدريجية لإنشاء مستند PDF وقراءة تدفق الصور وتضمين الصورة في ملف PDF.

#### س: لماذا يعد تحديد دليل المستند مهمًا في عملية تحويل دفق الصور إلى PDF؟

ج: تحديد دليل المستند يضمن أن تدفق الصورة وملف PDF الناتج يقعان بشكل صحيح في مسار الإخراج المطلوب.

#### س: كيف يمكنني إنشاء مستند PDF باستخدام Aspose.PDF for .NET في عملية تحويل دفق الصور إلى PDF؟

 ج: إنشاء أ`Document` كائن باستخدام`Aspose.Pdf.Document` مُنشئ الفصل الفارغ لإنشاء مستند PDF.

####  س: ما هو دور ال`Pages` object in the image stream to PDF conversion process?

 ج: إن`Pages` يتيح لك الكائن إضافة صفحات إلى مستند PDF وإدارة محتواه.

#### س: كيف تتم قراءة دفق الصور ومعالجته في عملية تحويل دفق الصور إلى PDF؟

 ج: تتم قراءة دفق الصورة باستخدام ملف`FileStream` الكائن ومحتوياته مخزنة في مصفوفة بايت. ثم يتم استخدام مصفوفة البايت لإنشاء ملف`MemoryStream` الكائن ، والذي يتم استخدامه لاحقًا لإنشاء ملف`Image` هدف.

#### س: كيف يتم تضمين الصورة في مستند PDF أثناء عملية التحويل؟

 ج: ان`Image` يتم إنشاء الكائن باستخدام`Aspose.Pdf.Image` class ، ويتم تعيين دفق الصورة إلى`ImageStream` ملكية. ال`Image` ثم يتم إضافة الكائن إلى`Paragraphs` مجموعة من وثيقة PDF.

#### س: هل يمكنني تخصيص موضع الصورة أو حجمها أو سمات أخرى في ملف PDF الناتج؟

 ج: نعم ، يمكنك تعديل موضع الصورة وحجمها والسمات الأخرى عن طريق ضبط خصائص ملف`Image` كائن قبل إضافته إلى`Paragraphs` مجموعة.

#### س: ما هي الخطوة الأخيرة في عملية تحويل دفق الصور إلى PDF؟

 ج: يتم حفظ مستند PDF باستخدام ملف`Save` طريقة`Document` الكائن و`MemoryStream` الكائن مغلق باستخدام`Close` طريقة للإفراج عن الموارد.