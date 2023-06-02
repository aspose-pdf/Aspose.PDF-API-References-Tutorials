---
title: احصل على خصائص
linktitle: احصل على خصائص
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة للحصول على خصائص PDF مثل أبعاد الصندوق والدوران باستخدام Aspose.PDF for .NET.
type: docs
weight: 100
url: /ar/net/programming-with-pdf-pages/get-properties/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة للحصول على خصائص PDF باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية الوصول إلى الخصائص المختلفة لصفحة PDF مثل Art box ، و Crop box ، و Crop box ، وما إلى ذلك ، باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تعيين دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو موقع ملف PDF الذي تريد الحصول على خصائصه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح مستند PDF
 بعد ذلك ، تحتاج إلى فتح مستند PDF باستخدام ملف`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لملف PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## الخطوة 3: قم بالوصول إلى مجموعة الصفحات
 يمكنك الآن الوصول إلى مجموعة صفحات المستند باستخدام امتداد`Pages` ممتلكات`pdfDocument` هدف.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## الخطوة 4: اذهب إلى صفحة معينة
ثم يمكنك الانتقال إلى صفحة معينة باستخدام فهرس الصفحة في المجموعة. في المثال أدناه ، نصل إلى الصفحة الثانية (الفهرس 1).

```csharp
Page pdfPage = pageCollection[1];
```

## الخطوة 5: احصل على خصائص الصفحة
 يمكنك الآن الحصول على الخصائص المختلفة لصفحة PDF ، مثل المربع الفني ، ومربع الاقتصاص ، ومربع الاقتصاص ، وما إلى ذلك ، باستخدام الخصائص المقابلة لـ`pdfPage` هدف.

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

### نموذج التعليمات البرمجية المصدر للحصول على خصائص باستخدام Aspose.PDF for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// احصل على مجموعة الصفحات
PageCollection pageCollection = pdfDocument.Pages;
// احصل على صفحة معينة
Page pdfPage = pageCollection[1];
// احصل على خصائص الصفحة
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
تهنئة ! لقد نجحت في الحصول على خصائص ملف PDF باستخدام Aspose.PDF لـ .NET. لقد تعلمت كيفية فتح مستند PDF ، والتنقل إلى صفحة معينة ، والحصول على خصائص صفحة متنوعة ، مثل مربعات الأبعاد والدوران. يمكنك الآن استخدام هذه المعلومات لتخصيص معالجة ملفات PDF الخاصة بك بناءً على خصائصها.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لـ .NET لمزيد من المعلومات حول الميزات المتقدمة وإمكانيات التخصيص.
