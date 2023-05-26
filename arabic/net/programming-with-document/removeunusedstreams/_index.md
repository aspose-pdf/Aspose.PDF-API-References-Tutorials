---
title: إزالة التدفقات غير المستخدمة
linktitle: إزالة التدفقات غير المستخدمة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إزالة التدفقات غير المستخدمة من ملفات PDF باستخدام Aspose.PDF for .NET. دليلنا خطوة بخطوة.
type: docs
weight: 270
url: /ar/net/programming-with-document/removeunusedstreams/
---
في هذا المثال ، سنناقش كيفية إزالة التدفقات غير المستخدمة من مستندات PDF باستخدام Aspose.PDF لـ .NET. سنقدم دليلًا تفصيليًا حول كيفية القيام بذلك ، بما في ذلك كود المصدر الكامل مع التفسيرات.

## الخطوة 1: المسار إلى دليل المستندات

يحدد السطر الأول من الكود المسار إلى الدليل حيث يوجد مستند PDF الخاص بك. تأكد من استبدال "دليل المستند" بمسار الدليل الفعلي.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

يفتح السطر التالي من التعليمات البرمجية مستند PDF باستخدام Aspose.PDF لمكتبة .NET.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## الخطوة 3: قم بتعيين خيار RemoveUnusedStreams

الخطوة التالية هي ضبط خيار RemoveUnusedStreams على true. سيؤدي هذا إلى إزالة أي تدفقات غير مستخدمة من مستند PDF.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## الخطوة 4: تحسين مستند PDF باستخدام OptimizationOptions

الآن بعد أن قمنا بتعيين خيارات التحسين ، يمكننا تحسين مستند PDF باستخدام سطر التعليمات البرمجية التالي.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 5: احفظ المستند المحدث

أخيرًا ، يمكننا حفظ المستند المحدث باستخدام طريقة Save لفئة Document.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### مثال على التعليمات البرمجية المصدر لإزالة التدفقات غير المستخدمة باستخدام Aspose.PDF لـ .NET

يوجد أدناه مثال لشفرة المصدر لإزالة التدفقات غير المستخدمة باستخدام Aspose.PDF لـ .NET.

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// افتح المستند
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// قم بتعيين خيار RemoveUsedStreams
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedStreams = true
	};
	// تحسين مستند PDF باستخدام OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// احفظ المستند المحدث
	pdfDocument.Save(dataDir);

```
