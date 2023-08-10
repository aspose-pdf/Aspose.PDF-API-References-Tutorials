---
title: الخطوط غير المجمعة وتحسين ملفات PDF
linktitle: الخطوط غير المجمعة وتحسين ملفات PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET للحصول على Unembed Fonts وتحسين ملفات PDF. دليل خطوة بخطوة.
type: docs
weight: 370
url: /ar/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET مكتبة قوية توفر مجموعة واسعة من الميزات للعمل مع مستندات PDF. تتمثل إحدى ميزاته في الحصول على خطوط غير مجمعة من مستند PDF. يمكن أن يكون هذا مفيدًا إذا كنت بحاجة إلى استخراج الخطوط من مستند PDF واستخدامها في تطبيقات أخرى.

سنقدم دليلاً خطوة بخطوة لشرح الكود المصدري C # التالي لميزة الحصول على خطوط غير مجمعة في Aspose.PDF for .NET.

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

قبل أن نبدأ ، نحتاج إلى تعيين المسار إلى الدليل حيث يوجد مستند PDF الخاص بنا. سنخزن هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

استبدل "دليل المستند" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 2: افتح مستند PDF

 الخطوة الأولى هي تحميل مستند PDF الذي تريد القيام بذلك ، استخدم ملف`Document` فئة Aspose.PDF لـ .NET. يوضح مقتطف الشفرة التالي كيفية تحميل مستند PDF:

```csharp
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Step3: تعيين خيار UnembedFonts

 للحصول على خطوط غير مجمعة من مستند PDF ، تحتاج إلى ضبط تنسيق`UnembedFonts` الخيار ل`true` . هذا الخيار متاح في`OptimizationOptions` فصل. يوضح مقتطف الشفرة التالي كيفية تعيين ملف`UnembedFonts` خيار:

```csharp
// تعيين خيار UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## الخطوة 4: تحسين مستند PDF

 بعد ضبط ملف`UnembedFonts` الخيار ، يمكنك تحسين مستند PDF باستخدام ملف`OptimizeResources` طريقة`Document` فصل. يوضح مقتطف الشفرة التالي كيفية تحسين مستند PDF:

```csharp
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 5: احفظ المستند المحدث

 بمجرد تحسين مستند PDF ، يمكنك حفظ المستند المحدث باستخدام ملحق`Save` طريقة`Document`فصل. يوضح مقتطف الشفرة التالي كيفية حفظ المستند المحدث:

```csharp
// احفظ المستند المحدث
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## الخطوة 6: احصل على حجم الملف الأصلي والمخفض

 أخيرًا ، يمكنك الحصول على حجم الملف الأصلي والصغير لمستند PDF باستخدام تنسيق`FileInfo` فئة System.IO. يوضح مقتطف الشفرة التالي كيفية الحصول على حجم الملف الأصلي والصغير:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### مثال التعليمات البرمجية المصدر للحصول على خطوط غير مجمعة باستخدام Aspose.PDF لـ .NET

فيما يلي المثال الكامل لشفرة المصدر للحصول على خطوط غير مجمعة من مستند PDF باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// تعيين خيار UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// احفظ المستند المحدث
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## خاتمة

في هذا البرنامج التعليمي ، أوضحنا كيفية استخدام Aspose.PDF لـ .NET للحصول على خطوط غير مجمعة من مستند PDF. باتباع الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تنفيذ هذه الميزة في تطبيقات C #. يمكن أن يكون إلغاء دمج الخطوط مفيدًا عندما تحتاج إلى العمل مع الخطوط المستخرجة بشكل منفصل أو ضمان الاستخدام المتسق للخط عبر العديد من الأنظمة الأساسية.

## التعليمات

#### س: ما هو الغرض من إلغاء دمج الخطوط من مستند PDF؟

ج: يتيح لك إلغاء دمج الخطوط من مستند PDF استخراج الخطوط المضمنة واستخدامها في تطبيقات أخرى. يمكن أن يكون هذا مفيدًا لضمان تجسيد خط متناسق والحفاظ على المظهر المرئي للمستند.

#### س: كيف يمكنني تحديد المسار إلى دليل المستند في كود C #؟

 ج: لتحديد المسار إلى دليل المستند ، استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

####  س: ماذا`UnembedFonts` option do, and where is it set?

 ج: إن`UnembedFonts` الخيار المتاح في`OptimizationOptions` class أو تمكين أو تعطيل إلغاء دمج الخطوط من مستند PDF. لتعيين هذا الخيار على`true`، استخدم الكود التالي:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### س: هل يمكنني التراجع عن التغييرات التي تم إجراؤها أثناء عملية التحسين؟

ج: لا يقوم Aspose.PDF for .NET بإجراء تغييرات دائمة على مستند PDF الأصلي أثناء التحسين. يتم تنفيذ عملية التحسين على نسخة من الوثيقة ، مع ترك النسخة الأصلية سليمة.

#### س: كيف يمكنني التحقق من حجم الملف الأصلي والصغير بعد التحسين؟

ج: يمكنك استخدام ملف`FileInfo` فئة من`System.IO` للحصول على حجم الملف الأصلي والمقلص. إليك مثال على مقتطف الشفرة لتحقيق ذلك:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```