---
title: تحويل تدفق الصور إلى ملف PDF
linktitle: تحويل تدفق الصور إلى ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة تحويل تدفق الصور إلى ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-images/convert-image-stream-to-pdf/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية تحويل تدفق الصور إلى ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من إعداد البيئة الخاصة بك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستندات

قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي توجد فيه صورتك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

 في هذه الخطوة، سنقوم بإنشاء مثيل لـ`Document` الكائن الذي يستخدم المنشئ الفارغ لـ`Aspose.Pdf.Document` فصل.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## الخطوة 3: إضافة صفحة إلى مستند PDF

أضف صفحة إلى مستند PDF باستخدام`Add` طريقة`Pages` غرض من`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## الخطوة 4: قراءة تدفق الصورة

 في هذه الخطوة سوف نقوم بإنشاء`FileStream` كائن لقراءة ملف الصورة من الدفق.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## الخطوة 5: قراءة الصورة في مصفوفة بايتات

 اقرأ الصورة من الدفق وقم بتخزينها في مصفوفة بايت باستخدام`Read` طريقة`fs` هدف.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## الخطوة 6: إنشاء كائن MemoryStream من مجموعة البايتات

 إنشاء`MemoryStream` الكائن من مجموعة البايتات التي تحتوي على الصورة.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## الخطوة 7: إنشاء كائن صورة

 في هذه الخطوة، سنقوم بإنشاء`Image` كائن باستخدام`Aspose.Pdf.Image` الفئة. حدد تدفق الصورة باستخدام`ImageStream` الملكية وتمرير`ms` الكائن الذي أنشأناه سابقًا.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## الخطوة 8: إضافة كائن الصورة إلى مجموعة الفقرات

 أضف`imageht` الاعتراض على`Paragraphs` مجموعة من`sec` قسم.

```csharp
sec.Paragraphs.Add(imageht);
```

## الخطوة 9: احفظ مستند PDF

 احفظ مستند PDF باستخدام`Save` طريقة`pdf1` الكائن. حدد مسار إخراج ملف PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## الخطوة 10: إغلاق كائن MemoryStream

 اغلق`ms` كائن باستخدام`Close` طريقة تحرير الموارد.

```csharp
ms. Close();
```

### عينة من كود المصدر لتحويل تدفق الصور إلى PDF باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل مستند عن طريق استدعاء المنشئ الفارغ الخاص به
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// إضافة صفحة إلى مستند pdf
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// إنشاء كائن FileStream لقراءة ملف imag
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// قراءة الصورة في مصفوفة البايت
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// إنشاء كائن MemoryStream من مجموعة بايتات الصورة
MemoryStream ms = new MemoryStream(data);
// إنشاء كائن صورة
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// حدد مصدر الصورة كـMemoryStream
imageht.ImageStream = ms;
// أضف كائن الصورة إلى مجموعة الفقرات في القسم
sec.Paragraphs.Add(imageht);
// احفظ ملف PDF
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// إغلاق كائن MemoryStream
ms.Close();
```

## خاتمة

تهانينا! لقد نجحت في تحويل تدفق صورة إلى ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ ملف PDF الناتج في الدليل المحدد. يمكنك الآن استخدام ملف PDF هذا في مشاريعك أو تطبيقاتك.

### الأسئلة الشائعة

#### س: ما هو الغرض من تحويل مجرى صورة إلى ملف PDF باستخدام Aspose.PDF لـ .NET؟

أ: يمكن أن يكون تحويل تدفق الصور إلى ملف PDF مفيدًا لدمج الصور في مستندات PDF، أو إنشاء ملفات PDF تعتمد على الصور، أو تضمين الصور داخل محتوى نصي.

#### س: كيف يساعد Aspose.PDF for .NET في تحويل تدفق الصور إلى ملف PDF؟

ج: يوفر Aspose.PDF لـ .NET عملية مريحة خطوة بخطوة لإنشاء مستند PDF، وقراءة مجرى الصور، وتضمين الصورة في ملف PDF.

#### س: لماذا يعد تحديد دليل المستند مهمًا في عملية تحويل تدفق الصورة إلى PDF؟

أ: تحديد دليل المستند يضمن أن مجرى الصورة وملف PDF الناتج يقعان بشكل صحيح في مسار الإخراج المطلوب.

#### س: كيف أقوم بإنشاء مستند PDF باستخدام Aspose.PDF لـ .NET في عملية تحويل تدفق الصورة إلى PDF؟

 أ: إنشاء مثيل`Document` كائن باستخدام`Aspose.Pdf.Document` منشئ فارغ للفئة لإنشاء مستند PDF.

####  س: ما هو دور`Pages` object in the image stream to PDF conversion process?

 أ: ال`Pages` يسمح لك الكائن بإضافة صفحات إلى مستند PDF وإدارة محتواه.

#### س: كيف تتم قراءة تدفق الصورة ومعالجتها في عملية تحويل تدفق الصورة إلى PDF؟

 أ: تتم قراءة تدفق الصورة باستخدام`FileStream` الكائن، ويتم تخزين محتوياته في مصفوفة بايتات. ثم يتم استخدام مصفوفة البايتات لإنشاء`MemoryStream` الكائن، والذي يتم استخدامه لاحقًا لإنشاء`Image` هدف.

#### س: كيف يتم تضمين الصورة في مستند PDF أثناء عملية التحويل؟

 أ: أ`Image` يتم إنشاء الكائن باستخدام`Aspose.Pdf.Image` الفئة، ويتم تعيين مجرى الصورة إلى`ImageStream` الممتلكات.`Image` ثم يتم إضافة الكائن إلى`Paragraphs` مجموعة من وثيقة PDF.

#### س: هل يمكنني تخصيص موضع الصورة أو حجمها أو السمات الأخرى في ملف PDF الناتج؟

 ج: نعم، يمكنك تعديل موضع الصورة وحجمها والسمات الأخرى عن طريق ضبط خصائص`Image` الكائن قبل إضافته إلى`Paragraphs` مجموعة.

#### س: ما هي الخطوة الأخيرة في عملية تحويل تدفق الصورة إلى PDF؟

 أ: يتم حفظ مستند PDF باستخدام`Save` طريقة`Document` الكائن، و`MemoryStream` تم إغلاق الكائن باستخدام`Close`طريقة لتحرير الموارد.