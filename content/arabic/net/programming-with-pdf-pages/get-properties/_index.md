---
title: الحصول على خصائص PDF
linktitle: الحصول على خصائص PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة للحصول على خصائص PDF مثل أبعاد الصندوق والتدوير باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 100
url: /ar/net/programming-with-pdf-pages/get-properties/
---
في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة للحصول على خصائص ملف PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية الوصول إلى خصائص مختلفة لصفحة PDF مثل المربع الفني، ومربع الاقتصاص، ومربع الاقتصاص، وما إلى ذلك، باستخدام Aspose.PDF لـ .NET.

## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C#
- تم تثبيت Aspose.PDF لـ .NET في بيئة التطوير الخاصة بك

## الخطوة 1: قم بتعيين دليل المستندات
أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو موقع ملف PDF الذي تريد الحصول على خصائصه. استبدل "دليل المستندات الخاصة بك" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح مستند PDF
 بعد ذلك، تحتاج إلى فتح مستند PDF باستخدام الملف`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لملف PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## الخطوة 3: الوصول إلى مجموعة الصفحات
 يمكنك الآن الوصول إلى مجموعة صفحات المستند باستخدام الملف`Pages` ملكية`pdfDocument` هدف.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## الخطوة 4: انتقل إلى صفحة محددة
ثم يمكنك الانتقال إلى صفحة معينة باستخدام فهرس الصفحة الموجودة في المجموعة. في المثال أدناه، نصل إلى الصفحة الثانية (الفهرس 1).

```csharp
Page pdfPage = pageCollection[1];
```

## الخطوة 5: الحصول على خصائص الصفحة
 يمكنك الآن الحصول على الخصائص المختلفة لصفحة PDF، مثل المربع الفني، ومربع الاقتصاص، ومربع الاقتصاص، وما إلى ذلك، باستخدام الخصائص المقابلة لـ`pdfPage` هدف.

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

### نموذج التعليمات البرمجية المصدر لـ Get Properties باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
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
تهنئة ! لقد نجحت في الحصول على خصائص ملف PDF باستخدام Aspose.PDF لـ .NET. لقد تعلمت كيفية فتح مستند PDF، والانتقال إلى صفحة معينة، والحصول على خصائص الصفحة المختلفة، مثل مربعات الأبعاد والتدوير. يمكنك الآن استخدام هذه المعلومات لتخصيص التعامل مع ملفات PDF الخاصة بك بناءً على خصائصها.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لـ .NET لمزيد من المعلومات حول الميزات المتقدمة وإمكانيات التخصيص.

### الأسئلة الشائعة

#### س: كيف يمكنني الحصول على خصائص ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: للحصول على خصائص ملف PDF باستخدام Aspose.PDF لـ .NET، يمكنك اتباع الخطوات التالية:

1. قم بتعيين دليل المستند عن طريق تحديد المسار إلى ملف PDF الذي تريد استرداد خصائصه.
2.  افتح مستند PDF باستخدام`Document` فئة Aspose.PDF، مما يوفر المسار الصحيح لملف PDF.
3.  قم بالوصول إلى مجموعة صفحات المستند باستخدام`Pages` ملكية`pdfDocument` هدف.
4. انتقل إلى صفحة محددة باستخدام فهرس الصفحة الموجودة في المجموعة (تبدأ الفهرسة من 1).
5.  احصل على الخصائص المختلفة لصفحة PDF، مثل ArtBox وBleedBox وCropBox وMediaBox وTrimBox وRect وPage Number وRotation، وذلك باستخدام الخصائص المقابلة لصفحة PDF.`pdfPage` هدف.

#### س: ما هي الخصائص المختلفة لصفحة PDF التي يمكنني استردادها باستخدام Aspose.PDF لـ .NET؟

ج: يمكنك استرداد خصائص مختلفة لصفحة PDF باستخدام Aspose.PDF لـ .NET، مثل:

- ArtBox: يمثل أبعاد العمل الفني للصفحة.
- BleedBox: يمثل أبعاد نزيف الصفحة.
- CropBox: يمثل أبعاد المحتوى المرئي للصفحة بعد الاقتصاص.
- MediaBox: يمثل أبعاد الوسائط الفعلية للصفحة.
- TrimBox: يمثل أبعاد محتوى الصفحة المقطوع.
- المستطيل: يمثل أبعاد المربع المحيط بالصفحة.
- رقم الصفحة: يمثل رقم الصفحة في المستند.
- التدوير: يمثل زاوية دوران الصفحة.

#### س: كيف يمكنني الوصول إلى صفحة معينة في وثيقة PDF لاستعادة خصائصها؟

 ج: للوصول إلى صفحة معينة في مستند PDF واسترداد خصائصها، يمكنك استخدام`Pages` ملكية`pdfDocument` كائن للوصول إلى مجموعة صفحات المستند. وبعد ذلك، يمكنك استخدام فهرس الصفحة الموجودة في المجموعة للانتقال إلى الصفحة المطلوبة. على سبيل المثال، للوصول إلى الصفحة الثانية، يمكنك استخدام`pdfDocument.Pages[1]` (الفهرسة تبدأ من 1).

#### س: هل يمكنني إجراء عمليات على الخصائص المستردة، مثل تعديل أو تغيير حجم مربعات الصفحة؟

ج: نعم، بمجرد استرداد خصائص صفحة PDF باستخدام Aspose.PDF لـ .NET، يمكنك إجراء عمليات مختلفة عليها. على سبيل المثال، يمكنك تعديل أبعاد مربعات الصفحة، أو تدوير الصفحة، أو استخدام المعلومات المستردة للمعالجة المخصصة ومعالجة مستند PDF.

#### س: هل يدعم Aspose.PDF for .NET استخراج الخصائص من ملفات PDF المشفرة أو المحمية بكلمة مرور؟

ج: نعم، يدعم Aspose.PDF for .NET استخراج الخصائص من ملفات PDF المشفرة أو المحمية بكلمة مرور. طالما قمت بتوفير كلمة المرور الصحيحة لفتح مستند PDF، يمكنك الوصول إلى خصائصه واستردادها باستخدام نفس الطريقة الموضحة في البرنامج التعليمي.