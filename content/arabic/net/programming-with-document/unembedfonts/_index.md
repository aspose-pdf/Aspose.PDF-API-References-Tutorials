---
title: إلغاء تضمين الخطوط وتحسين ملفات PDF
linktitle: إلغاء تضمين الخطوط وتحسين ملفات PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET للحصول على خطوط غير مضمنة وتحسين ملفات PDF. دليل خطوة بخطوة.
type: docs
weight: 370
url: /ar/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET هي مكتبة قوية توفر مجموعة واسعة من الميزات للعمل مع مستندات PDF. إحدى ميزاتها هي الحصول على خطوط غير مضمنة من مستند PDF. يمكن أن يكون هذا مفيدًا إذا كنت بحاجة إلى استخراج الخطوط من مستند PDF واستخدامها في تطبيقات أخرى.

سنقدم لك دليلًا خطوة بخطوة لشرح الكود المصدر C# التالي لميزة الحصول على الخطوط غير المضمنة في Aspose.PDF لـ .NET.

## الخطوة 1: تعيين المسار إلى دليل المستند

قبل أن نبدأ، نحتاج إلى تحديد المسار إلى الدليل الذي يوجد به مستند PDF الخاص بنا. سنخزن هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

استبدل "دليل المستندات الخاص بك" بالمسار الفعلي إلى الدليل الذي يوجد فيه مستند PDF الخاص بك.

## الخطوة 2: افتح مستند PDF

 الخطوة الأولى هي تحميل مستند PDF الذي تريد القيام بذلك، استخدم`Document` فئة Aspose.PDF لـ .NET. يوضح مقتطف التعليمات البرمجية التالي كيفية تحميل مستند PDF:

```csharp
// فتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## الخطوة 3: تعيين خيار UnembedFonts

 للحصول على خطوط غير مضمنة من مستند PDF، تحتاج إلى ضبط`UnembedFonts` خيار ل`true` . هذا الخيار متاح في`OptimizationOptions` يوضح مقتطف التعليمات البرمجية التالي كيفية تعيين`UnembedFonts` خيار:

```csharp
// تعيين خيار UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## الخطوة 4: تحسين مستند PDF

 بعد ضبط`UnembedFonts` يمكنك تحسين مستند PDF باستخدام الخيار`OptimizeResources` طريقة`Document` يوضح مقتطف التعليمات البرمجية التالي كيفية تحسين مستند PDF:

```csharp
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 5: احفظ المستند المحدث

 بمجرد تحسين مستند PDF، يمكنك حفظ المستند المحدث باستخدام`Save` طريقة`Document`يوضح مقتطف التعليمات البرمجية التالي كيفية حفظ المستند المحدث:

```csharp
// حفظ المستند المحدث
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## الخطوة 6: الحصول على الحجم الأصلي والمخفض للملف

 أخيرًا، يمكنك الحصول على الحجم الأصلي والمصغر لملف PDF باستخدام`FileInfo` فئة System.IO. يوضح مقتطف التعليمات البرمجية التالي كيفية الحصول على حجم الملف الأصلي والمختصر:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### مثال على كود المصدر للحصول على الخطوط غير المضمنة باستخدام Aspose.PDF لـ .NET

فيما يلي مثال كامل لمصدر الكود للحصول على خطوط غير مضمنة من مستند PDF باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// تعيين خيار UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// حفظ المستند المحدث
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## خاتمة

في هذا البرنامج التعليمي، أوضحنا كيفية استخدام Aspose.PDF لـ .NET للحصول على خطوط غير مضمنة من مستند PDF. باتباع الدليل خطوة بخطوة، يمكنك بسهولة تنفيذ هذه الميزة في تطبيقات C# الخاصة بك. يمكن أن يكون إلغاء تضمين الخطوط مفيدًا عندما تحتاج إلى العمل مع الخطوط المستخرجة بشكل منفصل أو ضمان استخدام الخطوط بشكل متسق عبر منصات مختلفة.

## الأسئلة الشائعة

#### س: ما هو الغرض من إلغاء تضمين الخطوط من مستند PDF؟

ج: يتيح لك إلغاء تضمين الخطوط من مستند PDF استخراج الخطوط المضمنة واستخدامها في تطبيقات أخرى. ويمكن أن يكون هذا مفيدًا لضمان عرض الخطوط بشكل متسق والحفاظ على المظهر المرئي للمستند.

#### س: كيف يمكنني تحديد المسار إلى دليل المستند في كود C#؟

 أ: لتحديد المسار إلى دليل المستند، استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود الذي يحتوي على المسار الفعلي إلى الدليل الذي يوجد به مستند PDF الخاص بك.

####  س: ماذا يعني`UnembedFonts` option do, and where is it set?

 أ: ال`UnembedFonts` الخيار متاح في`OptimizationOptions` الفئة، تمكن أو تعطل إلغاء تضمين الخطوط من مستند PDF. لتعيين هذا الخيار على`true`استخدم الكود التالي:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### س: هل يمكنني التراجع عن التغييرات التي أجريتها أثناء عملية التحسين؟

ج: لا يقوم Aspose.PDF for .NET بإجراء تغييرات دائمة على مستند PDF الأصلي أثناء عملية التحسين. تتم عملية التحسين على نسخة من المستند، مع ترك الأصل سليمًا.

#### س: كيف يمكنني التحقق من حجم الملف الأصلي والمختصر بعد التحسين؟

 أ: يمكنك استخدام`FileInfo` فئة من`System.IO` للحصول على حجم الملف الأصلي والمختصر. فيما يلي مقتطف من التعليمات البرمجية لتحقيق ذلك:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```