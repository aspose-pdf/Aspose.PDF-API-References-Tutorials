---
title: إلغاء تضمين الخطوط وتحسين ملفات PDF
linktitle: إلغاء تضمين الخطوط وتحسين ملفات PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET للحصول على Unembed Fonts وتحسين ملفات PDF. دليل خطوة بخطوة.
type: docs
weight: 370
url: /ar/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET هي مكتبة قوية توفر مجموعة واسعة من الميزات للعمل مع مستندات PDF. إحدى ميزاته هي الحصول على خطوط غير مدمجة من مستند PDF. يمكن أن يكون هذا مفيدًا إذا كنت بحاجة إلى استخراج الخطوط من مستند PDF واستخدامها في تطبيقات أخرى.

سنقدم دليلًا خطوة بخطوة لشرح كود مصدر C# التالي لميزة الحصول على الخطوط غير المضمنة في Aspose.PDF لـ .NET.

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

قبل أن نبدأ، نحتاج إلى تعيين المسار إلى الدليل الذي يوجد به مستند PDF الخاص بنا. سنقوم بتخزين هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

استبدل "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 2: افتح مستند PDF

 الخطوة الأولى هي تحميل مستند PDF الذي تريد القيام بذلك، استخدم الملف`Document` فئة Aspose.PDF لـ .NET. يوضح مقتطف الكود التالي كيفية تحميل مستند PDF:

```csharp
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## الخطوة 3: قم بتعيين خيار UnembedFonts

 للحصول على خطوط غير مدمجة من مستند PDF، تحتاج إلى تعيين`UnembedFonts` خيار ل`true` . هذا الخيار متاح في`OptimizationOptions` فصل. يوضح مقتطف الكود التالي كيفية تعيين`UnembedFonts` خيار:

```csharp
// قم بتعيين خيار UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## الخطوة 4: تحسين مستند PDF

 بعد ضبط`UnembedFonts` الخيار، يمكنك تحسين مستند PDF باستخدام`OptimizeResources` طريقة`Document` فصل. يوضح مقتطف الكود التالي كيفية تحسين مستند PDF:

```csharp
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 5: احفظ المستند المحدث

 بمجرد تحسين مستند PDF، يمكنك حفظ المستند المحدث باستخدام الملف`Save` طريقة`Document`فصل. يوضح مقتطف التعليمات البرمجية التالي كيفية حفظ المستند المحدث:

```csharp
// حفظ المستند المحدث
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## الخطوة 6: احصل على حجم الملف الأصلي والمصغر

 وأخيرًا، يمكنك الحصول على حجم الملف الأصلي والمصغر لمستند PDF باستخدام الملف`FileInfo` فئة System.IO. يوضح مقتطف الكود التالي كيفية الحصول على حجم الملف الأصلي والمصغر:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### مثال على كود المصدر للحصول على خطوط غير مدمجة باستخدام Aspose.PDF لـ .NET

فيما يلي المثال الكامل للتعليمة البرمجية المصدر للحصول على خطوط غير مدمجة من مستند PDF باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// قم بتعيين خيار UnembedFonts
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

في هذا البرنامج التعليمي، أوضحنا كيفية استخدام Aspose.PDF لـ .NET للحصول على خطوط غير مدمجة من مستند PDF. باتباع الدليل الموضح خطوة بخطوة، يمكنك بسهولة تنفيذ هذه الميزة في تطبيقات C# الخاصة بك. يمكن أن يكون إلغاء تضمين الخطوط مفيدًا عندما تحتاج إلى العمل مع الخطوط المستخرجة بشكل منفصل أو التأكد من استخدام الخط بشكل متسق عبر الأنظمة الأساسية المختلفة.

## الأسئلة الشائعة

#### س: ما هو الغرض من إلغاء دمج الخطوط من مستند PDF؟

ج: يتيح لك إلغاء دمج الخطوط من مستند PDF استخراج الخطوط المضمنة واستخدامها في تطبيقات أخرى. يمكن أن يكون هذا مفيدًا لضمان عرض خط متناسق والحفاظ على المظهر المرئي للمستند.

#### س: كيف يمكنني تحديد المسار إلى دليل المستند في كود C#؟

 ج: لتحديد المسار إلى دليل المستندات، استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار الفعلي إلى الدليل الذي يوجد به مستند PDF الخاص بك.

####  س: ماذا يفعل`UnembedFonts` option do, and where is it set?

 ج: ال`UnembedFonts` الخيار متاح في`OptimizationOptions` فئة، تمكن أو تعطل إلغاء دمج الخطوط من مستند PDF. لتعيين هذا الخيار على`true`، استخدم الكود التالي:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### س: هل يمكنني التراجع عن التغييرات التي تم إجراؤها أثناء عملية التحسين؟

ج: لا يقوم Aspose.PDF for .NET بإجراء تغييرات دائمة على مستند PDF الأصلي أثناء التحسين. يتم تنفيذ عملية التحسين على نسخة من المستند، مع ترك النسخة الأصلية سليمة.

#### س: كيف يمكنني التحقق من حجم الملف الأصلي والمصغر بعد التحسين؟

ج: يمكنك استخدام`FileInfo` فئة من`System.IO` للحصول على حجم الملف الأصلي والمصغر. فيما يلي مثال لمقتطف التعليمات البرمجية لتحقيق ذلك:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```