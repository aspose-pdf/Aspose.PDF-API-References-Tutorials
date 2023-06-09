---
title: تحسين حجم الملف
linktitle: تحسين حجم الملف
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحسين حجم ملف مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 250
url: /ar/net/programming-with-document/optimizefilesize/
---
Aspose.PDF for .NET هي مكتبة تتيح للمطورين إنشاء ملفات PDF وتحريرها ومعالجتها في تطبيقات .NET الخاصة بهم. واحدة من أكثر الميزات المفيدة لهذه المكتبة هي القدرة على تحسين حجم ملف مستند PDF. في هذه المقالة ، سنقدم دليلاً خطوة بخطوة لتحسين حجم ملف مستند PDF باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: قم بتحميل مستند PDF

 تتمثل الخطوة الأولى في تحسين حجم ملف مستند PDF في تحميل المستند في التطبيق الخاص بك. يمكنك القيام بذلك باستخدام ملف`Document` فئة مقدمة من Aspose.PDF لمكتبة .NET. فيما يلي مثال على كيفية تحميل مستند PDF:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 تأكد من استبداله`YOUR DOCUMENT DIRECTORY` مع المسار إلى الدليل الذي يحتوي على مستند PDF الخاص بك.

## الخطوة 2: تعيين خيارات التحسين

بمجرد تحميل مستند PDF ، يمكنك تعيين خيارات التحسين لتحديد أجزاء المستند التي تريد تحسينها. ال`OptimizationOptions` تتيح لك الفئة التي توفرها Aspose.PDF لمكتبة .NET تحديد مجموعة متنوعة من الخيارات لتحسين حجم ملف مستند PDF. فيما يلي مثال على كيفية تعيين بعض خيارات التحسين:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

في هذا المثال ، نقوم بتعيين الخيارات التالية:
- `LinkDuplcateStreams`: يتيح هذا الخيار إزالة التدفقات المكررة في مستند PDF ، مما قد يساعد في تقليل حجم الملف.
- `RemoveUnusedObjects`: يتيح هذا الخيار إزالة أي كائنات غير مستخدمة في مستند PDF ، والتي يمكن أن تساعد أيضًا في تقليل حجم الملف.
- `RemoveUnusedStreams`: يتيح هذا الخيار إزالة أي تدفقات غير مستخدمة في مستند PDF ، مما قد يؤدي إلى تقليل حجم الملف بشكل أكبر.
- `CompressImages`: يتيح هذا الخيار ضغط الصور في مستند PDF ، مما قد يؤدي إلى تقليل حجم الملف بشكل كبير.
- `ImageQuality`يضبط هذا الخيار جودة الصور المضغوطة. سينتج عن إعداد الجودة الأقل حجم ملف أصغر ، ولكن قد يؤدي أيضًا إلى انخفاض جودة الصورة.

## الخطوة 4: تحسين مستند PDF

 الآن بعد أن قمت بتعيين خيارات التحسين ، يمكنك تحسين مستند PDF باستخدام امتداد`OptimizeResources` الطريقة التي يوفرها`Document` فصل. فيما يلي مثال على كيفية تحسين مستند PDF:

```csharp
// قم بتحسين حجم الملف عن طريق إزالة الكائنات غير المستخدمة
pdfDocument.OptimizeResources(optimizationOptions);
```

## الخطوة 5: احفظ مستند PDF المحسن

بمجرد قيامك بتحسين مستند PDF ، يمكنك حفظ الإصدار المحسن في ملف جديد. فيما يلي مثال على كيفية حفظ مستند PDF المحسن:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);
```

### مثال التعليمات البرمجية المصدر لتحسين حجم الملف باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
// قم بتحسين حجم الملف عن طريق إزالة الكائنات غير المستخدمة
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);
```
