---
title: تحويل دفق الصور إلى ملف PDF
linktitle: تحويل دفق الصور إلى ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل تدفق الصور بسهولة إلى ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-images/convert-image-stream-to-pdf/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل دفق الصور إلى ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من أنك قمت بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي توجد به صورتك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

 في هذه الخطوة، سوف نقوم بإنشاء مثيل`Document` كائن باستخدام المُنشئ الفارغ لـ`Aspose.Pdf.Document` فصل.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## الخطوة 3: إضافة صفحة إلى مستند PDF

 أضف صفحة إلى مستند PDF باستخدام`Add` طريقة`Pages` موضوع`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## الخطوة 4: قراءة دفق الصور

 في هذه الخطوة سوف نقوم بإنشاء`FileStream` كائن لقراءة ملف الصورة من الدفق.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## الخطوة 5: قراءة الصورة في مصفوفة بايت

 اقرأ الصورة من الدفق وقم بتخزينها في مصفوفة بايت باستخدام الملف`Read` طريقة`fs` هدف.

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

 في هذه الخطوة سوف نقوم بإنشاء`Image` كائن باستخدام`Aspose.Pdf.Image` فصل. حدد دفق الصورة باستخدام`ImageStream` الممتلكات وتمرير`ms` الكائن الذي أنشأناه سابقًا.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## الخطوة 8: أضف كائن الصورة إلى مجموعة الفقرات

 أضف ال`imageht` يعترض على`Paragraphs` جمع من`sec` قسم.

```csharp
sec.Paragraphs.Add(imageht);
```

## الخطوة 9: احفظ مستند PDF

 احفظ مستند PDF باستخدام`Save` طريقة`pdf1` هدف. حدد مسار الإخراج لملف PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## الخطوة 10: أغلق كائن MemoryStream

 أقفل ال`ms` كائن باستخدام`Close` طريقة تحرير الموارد.

```csharp
ms. Close();
```

### نموذج التعليمات البرمجية المصدر لتحويل Image Stream إلى PDF باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//إنشاء مثيل للمستند عن طريق استدعاء منشئه الفارغ
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// أضف صفحة إلى مستند pdf
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// قم بإنشاء كائن FileStream لقراءة ملف الصورة
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// قراءة الصورة في مجموعة بايت
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// قم بإنشاء كائن MemoryStream من صفيف بايت الصورة
MemoryStream ms = new MemoryStream(data);
// إنشاء كائن الصورة
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// حدد مصدر الصورة كـ MemoryStream
imageht.ImageStream = ms;
// أضف كائن صورة إلى مجموعة الفقرات الخاصة بالقسم
sec.Paragraphs.Add(imageht);
// احفظ ملف PDF
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// أغلق كائن MemoryStream
ms.Close();
```

## خاتمة

تهنئة ! لقد نجحت في تحويل تدفق الصور إلى ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ ملف PDF الذي تم إنشاؤه في الدليل المحدد. يمكنك الآن استخدام ملف PDF هذا في مشاريعك أو تطبيقاتك.

### الأسئلة الشائعة

#### س: ما هو الغرض من تحويل دفق الصور إلى ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يكون تحويل دفق الصور إلى ملف PDF مفيدًا لدمج الصور في مستندات PDF، أو إنشاء ملفات PDF قائمة على الصور، أو تضمين الصور في محتوى نصي.

#### س: كيف يساعد Aspose.PDF for .NET في تحويل تدفق الصور إلى ملف PDF؟

ج: يوفر Aspose.PDF for .NET عملية مريحة وخطوة بخطوة لإنشاء مستند PDF وقراءة تدفق الصور وتضمين الصورة في ملف PDF.

#### س: ما سبب أهمية تحديد دليل المستند في عملية تحويل دفق الصور إلى PDF؟

ج: يضمن تحديد دليل المستند أن يكون تدفق الصورة وملف PDF الناتج موجودين بشكل صحيح في مسار الإخراج المطلوب.

#### س: كيف يمكنني إنشاء مستند PDF باستخدام Aspose.PDF لـ .NET في عملية تحويل دفق الصور إلى PDF؟

 ج: إنشاء مثيل أ`Document` كائن باستخدام`Aspose.Pdf.Document` منشئ الفصل الفارغ لإنشاء مستند PDF.

####  س: ما هو دور`Pages` object in the image stream to PDF conversion process?

 ج: ال`Pages` يتيح لك الكائن إضافة صفحات إلى مستند PDF وإدارة محتواه.

#### س: كيف تتم قراءة دفق الصور ومعالجته في عملية تحويل دفق الصور إلى PDF؟

 ج: تتم قراءة دفق الصور باستخدام ملف`FileStream` الكائن، ويتم تخزين محتوياته في مصفوفة بايت. يتم بعد ذلك استخدام مصفوفة البايت لإنشاء ملف`MemoryStream` كائن، والذي يتم استخدامه لاحقًا لإنشاء`Image` هدف.

#### س: كيف يتم تضمين الصورة في مستند PDF أثناء عملية التحويل؟

 ج: ان`Image` يتم إنشاء الكائن باستخدام`Aspose.Pdf.Image` فئة، ويتم تعيين دفق الصورة إلى`ImageStream` ملكية. ال`Image` ثم يتم إضافة الكائن إلى`Paragraphs` جمع وثيقة PDF.

#### س: هل يمكنني تخصيص موضع الصورة أو حجمها أو سماتها الأخرى في ملف PDF الناتج؟

 ج: نعم، يمكنك تعديل موضع الصورة وحجمها وسماتها الأخرى عن طريق ضبط خصائص الصورة`Image` الكائن قبل إضافته إلى`Paragraphs` مجموعة.

#### س: ما هي الخطوة الأخيرة في عملية تحويل دفق الصور إلى PDF؟

 ج: يتم حفظ مستند PDF باستخدام الملف`Save` طريقة`Document` الكائن، و`MemoryStream` تم إغلاق الكائن باستخدام`Close` طريقة تحرير الموارد.