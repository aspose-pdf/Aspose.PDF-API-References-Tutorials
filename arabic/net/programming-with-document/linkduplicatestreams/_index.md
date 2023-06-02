---
title: ربط تيارات مكررة
linktitle: ربط تيارات مكررة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF لميزة .NET Link Duplicate Streams لتحسين مستندات PDF باستخدام هذا الدليل التفصيلي.
type: docs
weight: 230
url: /ar/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF for .NET مكتبة شاملة وقوية توفر مجموعة متنوعة من الميزات للعمل مع ملفات PDF. تتمثل إحدى ميزاته الرئيسية في القدرة على تحسين ملفات PDF. في هذه المقالة ، سنشرح كيفية استخدام ميزة Link Duplicate Streams في Aspose.PDF لـ .NET لتحسين ملفات PDF. سنقدم إرشادات خطوة بخطوة ونضمّن مثالاً كاملاً لشفرة المصدر لتسهيل متابعة المطورين.

## الخطوة 1: فتح مستند PDF

لفتح مستند PDF باستخدام Aspose.PDF for .NET ، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

في الكود أعلاه ، استبدل "دليل المستندات الخاص بك" بالمسار إلى دليل مشروعك.

## الخطوة 2: ضبط خيار LinkDuplicateStreams

لتعيين خيار LinkDuplicateStreams ، اتبع الخطوات التالية:

```csharp
// قم بتعيين خيار LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

في الكود أعلاه ، أنشأنا مثيلًا جديدًا من OptimizationOptions وقمنا بتعيين خيار LinkDuplicateStreams على true.

## الخطوة 3: تحسين مستند PDF

لتحسين مستند PDF ، اتبع الخطوات التالية:

```csharp
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

في الكود أعلاه ، استخدمنا طريقة OptimizeResources لكائن pdfDocument لتحسين مستند PDF باستخدام OptimizationOptions التي أنشأناها سابقًا.

## الخطوة 4: حفظ المستند المحدث

لحفظ المستند المحدث ، اتبع الخطوات التالية:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
```

في الكود أعلاه ، استخدمنا طريقة Save للكائن pdfDocument لحفظ المستند المحدث في ملف جديد باسم "OptimizeDocument_out.pdf" في دليل المشروع.

### مثال على رمز المصدر للارتباط المكرر للدفقات باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// قم بتعيين خيار LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
```
