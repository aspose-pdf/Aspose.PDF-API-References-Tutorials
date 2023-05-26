---
title: إنشاء نهج PDF متعدد الطبقات أولاً
linktitle: إنشاء نهج PDF متعدد الطبقات أولاً
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء مستندات PDF متعددة الطبقات باستخدام الأسلوب الأول مع Aspose.PDF for .NET. أضف نصًا وصورًا والمزيد لتحسين ملفات PDF الخاصة بك.
type: docs
weight: 70
url: /ar/net/programming-with-document/createmultilayerpdffirstapproach/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية إنشاء ملف PDF متعدد الطبقات باستخدام الطريقة الأولى مع Aspose.PDF for .NET. يتيح لك هذا الأسلوب إضافة طبقات متعددة إلى مستند PDF الخاص بك. اتبع الدليل المفصل أدناه:

## الخطوة 1: قم بتهيئة مستند PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## الخطوة 2: أضف صفحة جديدة إلى المستند

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## الخطوة 3: أضف جزء نصي إلى الصفحة

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## الخطوة 4: تخصيص جزء النص

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## الخطوة 5: أضف صورة إلى الصفحة

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## الخطوة 6: أضف مربعًا عائمًا إلى الصفحة

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## الخطوة 7: احفظ مستند PDF الناتج

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

تهانينا! لقد نجحت في إنشاء مستند PDF متعدد الطبقات باستخدام الطريقة الأولى مع Aspose.PDF for .NET.

مثال على الكود المصدري لـ Create Multilayer PDF First Approach باستخدام Aspose.PDF for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

يمكنك الآن إنشاء مستندات PDF متعددة الطبقات باستخدام الطريقة الأولى مع Aspose.PDF for .NET.
