---
title: إزالة الكائنات غير المستخدمة
linktitle: إزالة الكائنات غير المستخدمة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET لإزالة الكائنات غير المستخدمة من مستندات PDF باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 260
url: /ar/net/programming-with-document/removeunusedobjects/
---
إذا كنت تبحث عن طريقة لإزالة الكائنات غير المستخدمة في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET ، فأنت في المكان الصحيح. سيوضح لك هذا الدليل التفصيلي كيفية استخدام شفرة المصدر C # المتوفرة لإنجاز هذه المهمة.

## الخطوة 1: حدد مسار الدليل

أولاً ، تحتاج إلى تعيين المسار إلى دليل المستند عن طريق استبدال "دليل المستند" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

بعد ذلك ، تحتاج إلى فتح مستند PDF الذي تريد تحسينه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## الخطوة 3: قم بتعيين خيار RemoveUnusedObjects

لإزالة الكائنات غير المستخدمة في مستند PDF الخاص بك ، تحتاج إلى تعيين خيار RemoveUnusedObjects على "true" على النحو التالي:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## الخطوة 4: تحسين مستند PDF باستخدام OptimizationOptions

الآن ، يمكنك تحسين مستند PDF الخاص بك باستخدام طريقة OptimizeResources مع خيارات التحسين التي قمت بتعيينها للتو:

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 5: احفظ المستند المحدث

أخيرًا ، يمكنك حفظ المستند المحدث بالرمز التالي:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

هذا كل شيء! لقد نجحت في إزالة الكائنات غير المستخدمة من مستند PDF الخاص بك باستخدام Aspose.PDF for .NET.

### مثال على التعليمات البرمجية المصدر لإزالة الكائنات غير المستخدمة باستخدام Aspose.PDF لـ .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// افتح المستند
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// قم بتعيين خيار RemoveUsedObject
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedObjects = true
	};
	// تحسين مستند PDF باستخدام OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// احفظ المستند المحدث
	pdfDocument.Save(dataDir);

```
