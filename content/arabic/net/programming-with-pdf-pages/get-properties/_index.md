---
title: الحصول على خصائص PDF
linktitle: الحصول على خصائص PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة للحصول على خصائص PDF مثل أبعاد المربع والدوران باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 100
url: /ar/net/programming-with-pdf-pages/get-properties/
---
في هذا البرنامج التعليمي، سنوضح لك عملية الحصول على خصائص ملف PDF خطوة بخطوة باستخدام Aspose.PDF لـ .NET. وسنشرح لك الكود المصدري المضمن بلغة C# وسنقدم لك دليلاً شاملاً لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. وفي نهاية هذا البرنامج التعليمي، ستعرف كيفية الوصول إلى خصائص مختلفة لصفحة PDF مثل مربع الرسم ومربع القص ومربع القص وما إلى ذلك، باستخدام Aspose.PDF لـ .NET.

## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#
- تم تثبيت Aspose.PDF لـ .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تعيين دليل المستندات
أولاً، عليك تحديد المسار إلى دليل المستندات الخاص بك. هذا هو موقع ملف PDF الذي تريد الحصول على خصائصه. استبدل "دليل المستندات الخاص بك" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح مستند PDF
 بعد ذلك، تحتاج إلى فتح مستند PDF باستخدام`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لملف PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## الخطوة 3: الوصول إلى مجموعة الصفحات
 الآن يمكنك الوصول إلى مجموعة صفحات المستند باستخدام`Pages` ممتلكات`pdfDocument` هدف.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## الخطوة 4: انتقل إلى صفحة معينة
يمكنك بعد ذلك الانتقال إلى صفحة معينة باستخدام فهرس الصفحة في المجموعة. في المثال أدناه، نصل إلى الصفحة الثانية (الفهرس 1).

```csharp
Page pdfPage = pageCollection[1];
```

## الخطوة 5: الحصول على خصائص الصفحة
 الآن يمكنك الحصول على الخصائص المختلفة لصفحة PDF، مثل مربع الفن، ومربع الاقتصاص، ومربع الاقتصاص، وما إلى ذلك، باستخدام الخصائص المقابلة لـ`pdfPage` هدف.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### عينة من كود المصدر للحصول على الخصائص باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// الحصول على مجموعة الصفحات
PageCollection pageCollection = pdfDocument.Pages;
// الحصول على صفحة معينة
Page pdfPage = pageCollection[1];
// الحصول على خصائص الصفحة
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## خاتمة
تهانينا! لقد نجحت في الحصول على خصائص ملف PDF باستخدام Aspose.PDF لـ .NET. لقد تعلمت كيفية فتح مستند PDF، والانتقال إلى صفحة معينة، والحصول على خصائص مختلفة للصفحة، مثل مربعات الأبعاد والتدوير. يمكنك الآن استخدام هذه المعلومات لتخصيص التعامل مع ملفات PDF الخاصة بك بناءً على خصائصها.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لـ .NET للحصول على مزيد من المعلومات حول الميزات المتقدمة وإمكانيات التخصيص.

### الأسئلة الشائعة

#### س: كيف يمكنني الحصول على خصائص ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: للحصول على خصائص ملف PDF باستخدام Aspose.PDF لـ .NET، يمكنك اتباع الخطوات التالية:

1. قم بتعيين دليل المستند عن طريق تحديد المسار إلى ملف PDF الذي تريد استرداد خصائصه.
2.  افتح مستند PDF باستخدام`Document` فئة Aspose.PDF، التي توفر المسار الصحيح لملف PDF.
3.  الوصول إلى مجموعة صفحات المستند باستخدام`Pages` ممتلكات`pdfDocument` هدف.
4. انتقل إلى صفحة محددة باستخدام فهرس الصفحة في المجموعة (تبدأ الفهرسة من 1).
5.  احصل على الخصائص المختلفة لصفحة PDF، مثل ArtBox وBleedBox وCropBox وMediaBox وTrimBox وRect وPage Number وRotation، باستخدام الخصائص المقابلة لـ`pdfPage` هدف.

#### س: ما هي الخصائص المختلفة لصفحة PDF التي يمكنني استردادها باستخدام Aspose.PDF لـ .NET؟

ج: يمكنك استرداد خصائص مختلفة لصفحة PDF باستخدام Aspose.PDF لـ .NET، مثل:

- ArtBox: يمثل أبعاد العمل الفني للصفحة.
- BleedBox: يمثل أبعاد نزيف الصفحة.
- CropBox: يمثل أبعاد المحتوى المرئي للصفحة بعد القص.
- MediaBox: يمثل أبعاد الوسائط المادية للصفحة.
- TrimBox: يمثل أبعاد المحتوى المقصوص على الصفحة.
- مستطيل: يمثل أبعاد المربع المحيط بالصفحة.
- رقم الصفحة: يمثل رقم الصفحة في المستند.
- تدوير: يمثل زاوية دوران الصفحة.

#### س: كيف يمكنني الوصول إلى صفحة معينة في مستند PDF لاسترجاع خصائصها؟

 أ: للوصول إلى صفحة معينة في مستند PDF واسترجاع خصائصها، يمكنك استخدام`Pages` ممتلكات`pdfDocument` كائن للوصول إلى مجموعة صفحات المستند. بعد ذلك، يمكنك استخدام فهرس الصفحة في المجموعة للانتقال إلى الصفحة المطلوبة. على سبيل المثال، للوصول إلى الصفحة الثانية، يمكنك استخدام`pdfDocument.Pages[1]` (يبدأ الفهرس من 1).

#### س: هل يمكنني إجراء عمليات على الخصائص المسترجعة، مثل تعديل أو تغيير حجم مربعات الصفحة؟

ج: نعم، بمجرد استرداد خصائص صفحة PDF باستخدام Aspose.PDF for .NET، يمكنك إجراء عمليات مختلفة عليها. على سبيل المثال، يمكنك تعديل أبعاد مربعات الصفحة، أو تدوير الصفحة، أو استخدام المعلومات المستردة للمعالجة والتلاعب المخصصين بمستند PDF.

#### س: هل يدعم Aspose.PDF لـ .NET استخراج الخصائص من ملفات PDF المشفرة أو المحمية بكلمة مرور؟

ج: نعم، يدعم برنامج Aspose.PDF for .NET استخراج الخصائص من ملفات PDF المشفرة أو المحمية بكلمة مرور. طالما أنك توفر كلمة المرور الصحيحة لفتح مستند PDF، فيمكنك الوصول إلى خصائصه واسترجاعها باستخدام نفس النهج الموضح في البرنامج التعليمي.