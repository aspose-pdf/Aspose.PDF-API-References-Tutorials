---
title: استخراج الصور من ملف PDF
linktitle: استخراج الصور من ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم باستخراج الصور بسهولة من ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-images/extract-images/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية استخراج الصور من ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من أنك قمت بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود الذي يحتوي على المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

في هذه الخطوة، سنقوم بفتح مستند PDF باستخدام الملف`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ وتمرير المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## الخطوة 3: استخراج صورة محددة

 في هذه الخطوة، سنقوم باستخراج صورة معينة من صفحة معينة. استخدم ال`Images` مجموعة من الصفحة`s `كائن الموارد للوصول إلى الصورة المطلوبة. في المثال أدناه، نقوم باستخراج الصورة ذات الفهرس 1 من الصفحة الأولى.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## الخطوة 4: احفظ الصورة المستخرجة

 احفظ الصورة المستخرجة في ملف باستخدام ملف`Save` طريقة`xImage` هدف. حدد مسار الإخراج وتنسيق الصورة (في هذا المثال نستخدم تنسيق JPEG).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## الخطوة 5: احفظ ملف PDF المحدث

 احفظ ملف PDF المحدث باستخدام ملف`Save` طريقة`pdfDocument` هدف. حدد مسار الإخراج لملف PDF.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لاستخراج الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// استخراج صورة معينة
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// حفظ صورة الإخراج
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// حفظ ملف PDF المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهنئة ! لقد نجحت في استخراج الصور من ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ الصورة المستخرجة في الدليل المحدد ويتم أيضًا حفظ ملف PDF المحدث. يمكنك الآن استخدام هذه الملفات لتلبية احتياجاتك المحددة.

### الأسئلة الشائعة حول استخراج الصور من ملف PDF

#### س: لماذا أرغب في استخراج الصور من ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يكون استخراج الصور من ملف PDF مفيدًا لأغراض متعددة مثل الأرشفة أو إعادة استخدام الصور في مستندات أخرى أو تحليل المحتوى أو تنفيذ مهام معالجة الصور.

#### س: كيف يسهل Aspose.PDF for .NET استخراج الصور من مستند PDF؟

ج: يوفر Aspose.PDF for .NET عملية خطوة بخطوة لفتح مستند PDF والوصول إلى صور معينة وحفظها في ملفات صور باستخدام تنسيقات مختلفة.

####  س: ما هو الدور الذي يقوم به`Document` class in Aspose.PDF for .NET play in image extraction?

 ج: ال`Document` يتم استخدام الفئة لتحميل ومعالجة مستندات PDF. وفي هذا السياق، يساعد في فتح مستند PDF الذي سيتم استخراج الصور منه.

#### س: كيف أحدد الصورة المحددة التي أريد استخراجها من صفحة PDF؟

ج: يمكنك استخدام`Images` مجموعة من الصفحة`Resources` كائن للوصول إلى الصورة المطلوبة من خلال فهرسها. على سبيل المثال،`pdfDocument.Pages[1].Resources.Images[1]` يصل إلى الصورة الأولى في الصفحة الأولى.

#### س: هل يمكنني استخراج الصور من أي صفحة في وثيقة PDF؟

ج: نعم، يمكنك استخراج الصور من أي صفحة في مستند PDF عن طريق تحديد فهرس الصفحة المطلوب وفهرس الصورة المراد استخراجها.

#### س: ما هي تنسيقات الصور التي يمكنني حفظ الصور المستخرجة بها؟

 ج: يمكنك حفظ الصور المستخرجة بتنسيقات مختلفة يدعمها ملف`ImageFormat` التعداد، مثل JPEG، PNG، BMP، والمزيد.

#### س: كيف يمكنني استخدام الصور المستخرجة بعد حفظها في الملفات؟

ج: يمكن استخدام الصور المستخرجة مثل أي ملفات صور أخرى. يمكنك عرضها أو تحريرها أو مشاركتها أو دمجها في مستندات أو مشاريع أخرى.

#### س: هل يؤثر استخراج الصور من ملف PDF على تخطيط أو محتوى مستند PDF الأصلي؟

ج: لا، لا يؤثر استخراج الصور من ملف PDF على تخطيط أو محتوى مستند PDF الأصلي. تتأثر الصور المستخرجة فقط.

#### س: هل يمكنني استخراج صور متعددة من صفحات مختلفة في عملية واحدة؟

ج: نعم، يمكنك استخدام نفس العملية لاستخراج الصور من صفحات متعددة عن طريق التكرار عبر فهارس صفحات مختلفة.