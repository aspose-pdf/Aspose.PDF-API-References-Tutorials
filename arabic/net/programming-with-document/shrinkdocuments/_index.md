---
title: تقليص المستندات
linktitle: تقليص المستندات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET لتقليص مستندات PDF باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 350
url: /ar/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF for .NET مكتبة قوية تمكن المطورين من إنشاء مستندات PDF ومعالجتها وتحسينها باستخدام C #. في هذا البرنامج التعليمي ، سنتعرف على مثال على كيفية استخدام Aspose.PDF لتقليص مستند PDF.

## الخطوة 1: تحميل مستند PDF

 لتقليص مستند PDF ، نحتاج أولاً إلى تحميله في تطبيق C # الخاص بنا باستخدام Aspose.PDF. في الكود أدناه ، نحدد المسار إلى مستند PDF الخاص بنا وننشئ مثيلًا جديدًا لملف`Document` فصل.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## الخطوة الثانية: تقليص مستند PDF

 بمجرد تحميل مستند PDF ، يمكننا استخدام ملف`OptimizeResources` طريقة`Document` فئة لتحسين المستند واحتمالية تقليص حجمه. لاحظ أن هذه الطريقة لا يمكن أن تضمن تقلص المستند ، حيث قد تكون بعض مستندات PDF محسّنة بشكل كبير بالفعل.

```csharp
// تحسين مستند PDF. لاحظ ، مع ذلك ، أن هذه الطريقة لا تضمن تقلص المستند
pdfDocument.OptimizeResources();
```

## الخطوة 3: حفظ مستند PDF المحدث

بعد أن نقوم بتحسين مستند PDF ، يمكننا حفظ الإصدار المحدث في ملف جديد باستخدام امتداد`Save` طريقة`Document` فصل. في الكود أدناه ، نحدد مسار واسم ملف الإخراج.

```csharp
// حدد مسار ملف الإخراج
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(outputFilePath);
```

### مثال التعليمات البرمجية المصدر لتقليص المستندات باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
// تحسين مستند PDF. لاحظ ، مع ذلك ، أن هذه الطريقة لا تضمن تقلص المستند
pdfDocument.OptimizeResources();
dataDir = dataDir + "ShrinkDocument_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
```
