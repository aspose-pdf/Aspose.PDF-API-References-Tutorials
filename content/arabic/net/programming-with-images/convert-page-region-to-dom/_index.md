---
title: تحويل منطقة الصفحة إلى DOM
linktitle: تحويل منطقة الصفحة إلى DOM
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة تحويل منطقة معينة من صفحة PDF إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 80
url: /ar/net/programming-with-images/convert-page-region-to-dom/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية تحويل منطقة معينة من الصفحة إلى نموذج كائن مستند (DOM) باستخدام Aspose.PDF لـ .NET. تأكد من إعداد البيئة الخاصة بك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستندات

قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

 في هذه الخطوة سوف نقوم بفتح مستند PDF باستخدام`Document` فئة Aspose.PDF. استخدم`Document` منشئ ومرر المسار إلى مستند PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: الحصول على مستطيل منطقة الصفحة

 في هذه الخطوة، سنقوم بتحديد مستطيل يمثل المنطقة المحددة من الصفحة التي نريد تحويلها إلى DOM. استخدم`Aspose.Pdf.Rectangle` الفئة لتحديد إحداثيات المستطيل.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## الخطوة 4: تحديد منطقة الاقتصاص للصفحة

 استخدم`CropBox` ممتلكات`Page` كائن لتعيين مربع اقتصاص الصفحة إلى مستطيل المنطقة المطلوبة.

```csharp
document.Pages[1].CropBox = pageRect;
```

## الخطوة 5: احفظ مستند PDF المقصوص في تيار

 في هذه الخطوة، سنقوم بحفظ مستند PDF المقصوص في مجرى باستخدام`MemoryStream` فصل.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## الخطوة 6: افتح مستند PDF المقصوص وقم بتحويله إلى صورة

 افتح مستند PDF المقصوص باستخدام`Document`سنقوم بتحويلها إلى صورة. سنستخدم دقة 300 نقطة في البوصة.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## الخطوة 7: تحويل الصفحة المحددة إلى صورة

 تحويل الصفحة المحددة إلى صورة باستخدام`Process` طريقة`pngDevice` الكائن. حدد مسار إخراج الصورة.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### عينة من كود المصدر لتحويل منطقة الصفحة إلى DOM باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document document = new Document( dataDir + "AddImage.pdf");
// الحصول على مستطيل لمنطقة صفحة معينة
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// تعيين قيمة CropBox حسب مستطيل منطقة الصفحة المطلوبة
document.Pages[1].CropBox = pageRect;
// حفظ المستند المقصوص في التدفق
MemoryStream ms = new MemoryStream();
document.Save(ms);
// افتح مستند PDF المقصوص وحوله إلى صورة
document = new Document(ms);
// إنشاء كائن الدقة
Resolution resolution = new Resolution(300);
// إنشاء جهاز PNG بالسمات المحددة
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// تحويل صفحة معينة وحفظ الصورة للبث
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهانينا! لقد نجحت في تحويل منطقة معينة من الصفحة إلى نموذج كائن مستند (DOM) باستخدام Aspose.PDF لـ .NET. يتم حفظ الصورة الناتجة في الدليل المحدد. يمكنك الآن استخدام هذه الصورة في مشاريعك أو تطبيقاتك.

## الأسئلة الشائعة

#### س: ما هو الغرض من تحويل منطقة معينة من الصفحة إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF لـ .NET؟

أ: قد يكون تحويل منطقة معينة من صفحة PDF إلى نموذج كائن المستند (DOM) مفيدًا لاستخراج قسم معين من المحتوى ومعالجته داخل مستند PDF.

#### س: كيف يسهل Aspose.PDF لـ .NET تحويل منطقة صفحة معينة إلى DOM؟

ج: يوفر Aspose.PDF لـ .NET عملية خطوة بخطوة لتحديد منطقة الصفحة المطلوبة، وتعيين منطقة الاقتصاص، وحفظ مستند PDF المقتطع في مجرى، وتحويل منطقة الصفحة المحددة إلى صورة.

#### س: لماذا من المهم تحديد دليل المستند قبل البدء في عملية التحويل؟

أ: تحديد دليل المستند يضمن أن مستند PDF والصورة الناتجة موجودان بشكل صحيح في مسار الإخراج المطلوب.

####  س: كيف يتم ذلك؟`Document` class in Aspose.PDF for .NET help in the conversion process?

 أ: ال`Document` تتيح لك الفئة فتح مستندات PDF ومعالجتها وحفظها. في هذه الحالة، يتم استخدامها لتحميل مستند PDF وإنشاء نسخة مقتطعة منه.

####  س: ما هو الغرض من`Rectangle` class in the page region conversion process?

 أ: ال`Rectangle`تحدد الفئة إحداثيات المنطقة المحددة على صفحة PDF التي تريد تحويلها إلى DOM. وهي تساعد في تحديد منطقة القطع بدقة.

#### س: كيف يتم ضبط مساحة القطع في الصفحة إلى المنطقة المطلوبة في عملية التحويل؟

 أ: ال`CropBox` ممتلكات`Page` يتم استخدام الكائن لتعيين مساحة الاقتصاص في الصفحة إلى المستطيل المحدد الذي يمثل المنطقة المحددة.

#### س: كيف يتم حفظ مستند PDF المقصوص في مجرى أثناء عملية التحويل؟

 أ: يتم حفظ مستند PDF المقصوص في`MemoryStream` الكائن الذي يسمح بالتعامل الفعال مع محتوى PDF.

####  س: ما هو الدور الذي يلعبه`PngDevice` class play in the page region to DOM conversion process?

 أ: ال`PngDevice` تساعد الفئة على تحويل مستند PDF المقصوص إلى تنسيق صورة، مثل PNG، مما يسمح لك بتصور منطقة الصفحة المحددة.

#### س: هل يمكنني تعديل الدقة أو السمات الأخرى للصورة الناتجة أثناء عملية التحويل؟

 ج: نعم، يمكنك تعديل الدقة والسمات الأخرى للصورة الناتجة عن طريق تكوين`PngDevice` الكائن قبل تحويل الصفحة.