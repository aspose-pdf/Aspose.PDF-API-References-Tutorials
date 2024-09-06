---
title: استخراج الصور من ملف PDF
linktitle: استخراج الصور من ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك استخراج الصور بسهولة من ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-images/extract-images/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية استخراج الصور من ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من إعداد البيئة الخاصة بك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستندات

قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 في هذه الخطوة سوف نقوم بفتح مستند PDF باستخدام`Document` فئة Aspose.PDF. استخدم`Document` منشئ ومرر المسار إلى مستند PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## الخطوة 3: استخراج صورة محددة

في هذه الخطوة، سنقوم باستخراج صورة محددة من صفحة معينة. استخدم`Images` مجموعة الصفحات`s `استخدم كائن "الموارد" للوصول إلى الصورة المطلوبة. في المثال أدناه، نقوم باستخراج الصورة ذات الفهرس 1 من الصفحة الأولى.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## الخطوة 4: احفظ الصورة المستخرجة

 احفظ الصورة المستخرجة في ملف باستخدام`Save` طريقة`xImage` الكائن. حدد مسار الإخراج وتنسيق الصورة (في هذا المثال نستخدم تنسيق JPEG).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## الخطوة 5: احفظ ملف PDF المحدث

 احفظ ملف PDF المحدث باستخدام`Save` طريقة`pdfDocument` الكائن. حدد مسار الإخراج لملف PDF.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### عينة من كود المصدر لاستخراج الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// استخراج صورة معينة
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// حفظ الصورة الناتجة
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// حفظ ملف PDF المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهانينا! لقد نجحت في استخراج الصور من ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ الصورة المستخرجة في الدليل المحدد ويتم أيضًا حفظ ملف PDF المحدث. يمكنك الآن استخدام هذه الملفات لتلبية احتياجاتك المحددة.

### الأسئلة الشائعة حول استخراج الصور من ملف PDF

#### س: لماذا أرغب في استخراج الصور من ملف PDF باستخدام Aspose.PDF لـ .NET؟

أ: يمكن أن يكون استخراج الصور من ملف PDF مفيدًا لأغراض مختلفة مثل الأرشفة، أو إعادة استخدام الصور في مستندات أخرى، أو تحليل المحتوى، أو تنفيذ مهام معالجة الصور.

#### س: كيف يسهل Aspose.PDF for .NET استخراج الصور من مستند PDF؟

ج: يوفر Aspose.PDF لـ .NET عملية خطوة بخطوة لفتح مستند PDF والوصول إلى صور محددة وحفظها في ملفات الصور باستخدام تنسيقات مختلفة.

####  س: ما هو الدور الذي يلعبه`Document` class in Aspose.PDF for .NET play in image extraction?

 أ: ال`Document` تُستخدم الفئة لتحميل مستندات PDF ومعالجتها. وفي هذا السياق، تساعد في فتح مستند PDF الذي سيتم استخراج الصور منه.

#### س: كيف يمكنني تحديد الصورة المحددة التي أريد استخراجها من صفحة PDF؟

 أ: يمكنك استخدام`Images` مجموعة من الصفحات`Resources` كائن للوصول إلى الصورة المطلوبة من خلال فهرسها. على سبيل المثال،`pdfDocument.Pages[1].Resources.Images[1]` الوصول إلى الصورة الأولى في الصفحة الأولى.

#### س: هل يمكنني استخراج الصور من أي صفحة في مستند PDF؟

ج: نعم، يمكنك استخراج الصور من أي صفحة في مستند PDF عن طريق تحديد فهرس الصفحة المطلوبة وفهرس الصورة المراد استخراجها.

#### س: ما هي تنسيقات الصور التي يمكنني حفظ الصور المستخرجة بها؟

 أ: يمكنك حفظ الصور المستخرجة بتنسيقات مختلفة يدعمها`ImageFormat` مثل JPEG، PNG، BMP، والمزيد.

#### س: كيف يمكنني استخدام الصور المستخرجة بعد حفظها في الملفات؟

ج: يمكن استخدام الصور المستخرجة مثل أي ملفات صور أخرى. ويمكنك عرضها أو تحريرها أو مشاركتها أو دمجها في مستندات أو مشاريع أخرى.

#### س: هل يؤثر استخراج الصور من ملف PDF على تخطيط أو محتوى مستند PDF الأصلي؟

ج: لا، لا يؤثر استخراج الصور من ملف PDF على تخطيط أو محتوى مستند PDF الأصلي. فقط الصور المستخرجة هي التي تتأثر.

#### س: هل يمكنني استخراج صور متعددة من صفحات مختلفة في عملية واحدة؟

ج: نعم، يمكنك استخدام نفس العملية لاستخراج الصور من صفحات متعددة من خلال التكرار عبر مؤشرات الصفحات المختلفة.