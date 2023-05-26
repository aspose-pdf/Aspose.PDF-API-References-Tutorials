---
title: السماح بإعادة استخدام محتوى الصفحة
linktitle: السماح بإعادة استخدام محتوى الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحسين ملفات PDF عن طريق تمكين ميزة "السماح بإعادة استخدام محتوى الصفحة" باستخدام Aspose.PDF لـ .NET. تقليل حجم الملف وتحسين الأداء.
type: docs
weight: 50
url: /ar/net/programming-with-document/allowresusepagecontent/
---

في هذا البرنامج التعليمي ، سنشرح كيفية تمكين ميزة "السماح بإعادة استخدام محتوى الصفحة" باستخدام Aspose.PDF لـ .NET. تعمل هذه الميزة على تحسين مستند PDF عن طريق إعادة استخدام محتوى الصفحة وتقليل حجم الملف وتحسين الأداء. اتبع الدليل المفصل أدناه:

## الخطوة 1: قم بتحميل مستند PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## الخطوة 2: قم بتعيين خيار AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## الخطوة 3: تحسين مستند PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 4: احفظ المستند المحدث

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## الخطوة الخامسة: التحقق من تصغير حجم الملف

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

تهانينا! لقد نجحت في السماح بإعادة استخدام محتوى الصفحة في مستند PDF الخاص بك.

### مثال على شفرة المصدر للسماح بإعادة استخدام محتوى الصفحة باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// قم بتعيين خيار AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
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

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

يمكنك الآن تحسين مستندات PDF الخاصة بك بشكل فعال من خلال السماح بإعادة استخدام محتوى الصفحة.
