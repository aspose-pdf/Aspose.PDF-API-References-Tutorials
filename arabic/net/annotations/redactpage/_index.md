---
title: الصفحة المنقحة
linktitle: الصفحة المنقحة
second_title: Aspose.PDF لمرجع .NET API
description: تشرح هذه المقالة كيفية تنقيح صفحة PDF باستخدام Aspose.PDF لـ .NET ، بما في ذلك تعليمات خطوة بخطوة ومثال على الكود المصدري.
type: docs
weight: 120
url: /ar/net/annotations/redactpage/
---
إذا كنت تبحث عن تنقيح معلومات حساسة من مستند PDF باستخدام Aspose.PDF for .NET ، فأنت محظوظ! إليك دليل تفصيلي للبدء:

## الخطوة 1: في الكود ، قم بتعيين المسار إلى الدليل حيث يوجد مستند PDF الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 3: إنشاء مثيل RedactionAnnotation لمنطقة صفحة معينة:

```csharp
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
```

## الخطوة 4: عيّن لون التعبئة ولون الحد ولون النص لتعليق التنقيح التوضيحي:

```csharp
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
```

## الخطوة 5: قم بتعيين النص المراد طباعته على التعليق التوضيحي للتنقيح ومحاذاة النص:

```csharp
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## الخطوة 6: كرر نص التراكب فوق التعليق التوضيحي للتنقيح:

```csharp
annot.Repeat = true;
```

## الخطوة 7: أضف التعليق التوضيحي إلى مجموعة التعليقات التوضيحية في الصفحة الأولى:

```csharp
doc.Pages[1].Annotations.Add(annot);
```

## الخطوة 8: قم بتسوية التعليق التوضيحي وتنقيح محتويات الصفحة ، أي إزالة النص والصور الموجودة أسفل التعليق التوضيحي المنقح:

```csharp
annot.Redact();
```

## الخطوة 9: حدد مسار واسم ملف PDF الناتج:

```csharp
dataDir = dataDir + "RedactPage_out.pdf";
```

## الخطوة 10: احفظ مستند PDF بالصفحة المنقحة:

```csharp
doc.Save(dataDir);
```

هذا كل شيء! لقد نجحت في تنقيح صفحة من مستند PDF الخاص بك باستخدام Aspose.PDF for .NET.

### مثال على شفرة المصدر لـ Redact Page باستخدام Aspose.PDF for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document doc = new Document(dataDir + "input.pdf");

// قم بإنشاء مثيل RedactionAnnotation لمنطقة صفحة معينة
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
// النص المراد طباعته على الشرح المنقح
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
// Repat نص التراكب فوق التعليق التوضيحي المنقح
annot.Repeat = true;
// أضف تعليقًا توضيحيًا إلى مجموعة التعليقات التوضيحية في الصفحة الأولى
doc.Pages[1].Annotations.Add(annot);
//يسوي التعليقات التوضيحية وينقح محتويات الصفحة (على سبيل المثال ، يزيل النص والصورة
// تحت تعليق توضيحي منقح)
annot.Redact();
dataDir = dataDir + "RedactPage_out.pdf";
doc.Save(dataDir);
```