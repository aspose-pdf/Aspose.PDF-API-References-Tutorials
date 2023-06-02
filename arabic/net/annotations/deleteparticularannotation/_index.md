---
title: حذف تعليق توضيحي معين
linktitle: حذف تعليق توضيحي معين
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية حذف تعليق توضيحي معين من مستند PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 50
url: /ar/net/annotations/deleteparticularannotation/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية استخدام Aspose.PDF for .NET لحذف تعليق توضيحي معين من ملف PDF باستخدام C #.

اتبع الخطوات أدناه لتوضيح كيفية حذف تعليق توضيحي معين باستخدام Aspose.PDF for .NET

## الخطوة 1: حدد مسار الدليل

قم بتعريف متغير للاحتفاظ بالمسار إلى ملف PDF الذي يحتوي على التعليق التوضيحي المراد حذفه. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 افتح ملف PDF باستخدام ملف`Document` فئة في Aspose.PDF لـ .NET.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");
```

## الخطوة 3: احصل على الصفحة لحذف التعليق التوضيحي المحدد

احذف التعليق التوضيحي المعين بتحديد الفهرس الخاص به وفهرس الصفحة التي ينتمي إليها. في هذا البرنامج التعليمي ، نحذف التعليق التوضيحي الموجود في الفهرس 1 في الصفحة الثانية من ملف PDF.

```csharp
pdfDocument.Pages[1].Annotations.Delete(1);
```
## الخطوة 4: احفظ مستند PDF المحدث

احفظ ملف PDF المحدث في ملف جديد باسم مختلف.

```csharp
dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```

## الخطوة 5: إظهار رسالة لحذف تعليق توضيحي معين

اطبع رسالة تشير إلى حذف التعليق التوضيحي المعين وحفظ ملف PDF المحدث.

```csharp
Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);
```

### مثال التعليمات البرمجية المصدر لحذف تعليق توضيحي معين باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");

// حذف تعليق توضيحي معين
pdfDocument.Pages[1].Annotations.Delete(1);

dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);

Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);
```
