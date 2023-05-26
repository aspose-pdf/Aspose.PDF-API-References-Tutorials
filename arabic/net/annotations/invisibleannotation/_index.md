---
title: تعليق توضيحي غير مرئي
linktitle: تعليق توضيحي غير مرئي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة تعليقات توضيحية إلى ملفات PDF بشكل غير مرئي باستخدام الكود المصدري C # مع Aspose.PDF for .NET. دليل خطوة بخطوة.
type: docs
weight: 100
url: /ar/net/annotations/invisibleannotation/
---
## فهم التعليقات التوضيحية في مستندات PDF

تعد التعليقات التوضيحية في مستندات PDF ميزة قوية تتيح لك إضافة معلومات أو ملاحظات إضافية إلى المستند دون تغيير المحتوى الفعلي. يمكن استخدامها لتمييز النص أو لفت الانتباه إلى مناطق معينة من المستند أو إضافة تعليقات أو ملاحظات.

هناك العديد من أنواع التعليقات التوضيحية المختلفة التي يمكنك استخدامها في مستندات PDF ، بما في ذلك:

- شروح نصية
- ربط التعليقات التوضيحية
- شروح الطوابع
- شروح صوتية
- شروح الملف المرفقات
- و أكثر من ذلك بكثير

## إنشاء تعليق غير مرئي في مستند PDF باستخدام Aspose.PDF لـ .NET

 لإنشاء تعليق توضيحي غير مرئي في مستند PDF باستخدام Aspose.PDF لـ .NET ، نحتاج أولاً إلى إنشاء`FreeTextAnnotation` الكائن وتحديد موقع وحجم التعليق التوضيحي.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 في الكود أعلاه ، نقوم بإنشاء ملف`FreeTextAnnotation`كائن وحدد مكان التعليق التوضيحي في الصفحة 2 من مستند PDF. نحدد أيضًا نوع الخط وحجمه ولونه للنص الذي سيتم عرضه في التعليق التوضيحي.

## إضافة خصائص إلى التعليق التوضيحي غير المرئي

بعد ذلك ، يمكننا إضافة بعض الخصائص إلى التعليق التوضيحي ، مثل لون الحد أو لون الخلفية أو التعتيم.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

في الكود أعلاه ، قمنا بتعيين لون حد التعليق التوضيحي إلى اللون الأحمر.

## تعيين إشارات التعليق التوضيحي

بعد إنشاء التعليق التوضيحي وتعيين خصائصه ، يمكننا تحديد علامات التعليق التوضيحي. في هذا البرنامج التعليمي ، نريد أن يكون التعليق التوضيحي قابلاً للطباعة ، ولكن غير قابل للعرض.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
```

## حفظ مستند PDF المعدل

أخيرًا ، يمكننا حفظ مستند PDF المعدل مع التعليق التوضيحي غير المرئي الجديد.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## مثال التعليمات البرمجية المصدر لكيفية التعليق التوضيحي غير المرئي باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1