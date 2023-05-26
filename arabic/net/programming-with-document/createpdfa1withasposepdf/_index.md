---
title: إنشاء ملف PDF A1 باستخدام Aspose Pdf
linktitle: إنشاء ملف PDF A1 باستخدام Aspose Pdf
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء مستند PDF A1 باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة مع شفرة المصدر C #. تحسين كفاءة ملفات PDF.
type: docs
weight: 90
url: /ar/net/programming-with-document/createpdfa1withasposepdf/
---

في هذا الدليل المفصل خطوة بخطوة ، سنشرح كيفية استخدام Aspose.PDF for .NET لإنشاء مستند PDF A1. سنزودك بكود مصدر C # والإرشادات اللازمة لإنجاز هذه المهمة.

## الخطوة 1: تحديد المتغيرات واستيراد مساحات الأسماء

 أولاً ، حدد المتغير`dataDir` لتمثيل الدليل حيث يتم تخزين المستندات الخاصة بك. سيتم استخدام هذا لتحديد مسار ملف الإخراج.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 بعد ذلك ، قم بإنشاء مثيل جديد لملف`Document` فئة من Aspose.PDF.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## الخطوة الثانية: إضافة محتوى إلى ملف PDF

في هذه الخطوة ، سنقوم بإضافة صفحة إلى مستند PDF وإدراج جزء نصي يحتوي على النص "Hello World!".

```csharp
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
```

## الخطوة 3: احفظ ملف PDF في تدفق الذاكرة

لتحويل تنسيق PDF إلى PDF / A1 ، نحتاج إلى حفظه في تدفق الذاكرة.

```csharp
MemoryStream ms = new MemoryStream();
pdf1.Save(ms);
```

## الخطوة 4: تحويل ملف PDF إلى تنسيق PDF / A1

 الآن ، سنقوم بتحويل ملف PDF إلى تنسيق PDF / A1 باستخدام امتداد`Convert` طريقة`Document` فصل. نقوم بتمرير دفق ذاكرة جديد كتدفق الإخراج وتحديد`PdfFormat.PDF_A_1A` شكل.

```csharp
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
```

## الخطوة 5: احفظ ملف PDF المحول

أخيرًا ، احفظ ملف PDF المحول في الدليل المحدد.

```csharp
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

### مثال على الكود المصدري لإنشاء PDF A1 باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// أضف صفحة إلى مستند pdf
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
MemoryStream ms = new MemoryStream();
// احفظ المستند
pdf1.Save(ms);
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

باتباع هذه الخطوات واستخدام كود المصدر المقدم ، يمكنك إنشاء مستند PDF A1 باستخدام Aspose.PDF for .NET.

تذكر أن تقوم بضبط "دليل المستند الخاص بك" باستخدام مسار الدليل المناسب حيث تريد حفظ ملف الإخراج.


