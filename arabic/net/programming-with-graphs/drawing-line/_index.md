---
title: خط الرسم
linktitle: خط الرسم
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية رسم خط عبر صفحة باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة لإنشاء خطوط مخصصة.
type: docs
weight: 80
url: /ar/net/programming-with-graphs/drawing-line/
---

في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة لرسم خط باستخدام Aspose.PDF for .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل أن تبدأ. لديك أيضًا معرفة أساسية ببرمجة C #.

## الخطوة 1: إعداد دليل المستند

في كود المصدر المقدم ، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير متغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مثيل مستند وإضافة صفحة

نقوم بإنشاء مثيل لفئة المستند وإضافة صفحة إلى هذا المستند.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## الخطوة 3: ضبط هوامش الصفحة

قمنا بتعيين هوامش الصفحة على 0 من جميع الجوانب.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## الخطوة 4: إنشاء كائن الرسم البياني والسطر الأول

نقوم بإنشاء كائن رسم بياني بأبعاد مساوية لأبعاد الصفحة ونرسم السطر الأول من الزاوية اليسرى السفلية إلى الزاوية اليمنى العليا من الصفحة.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## الخطوة 5: رسم السطر الثاني

نرسم السطر الثاني من الزاوية اليسرى العليا إلى الزاوية اليمنى السفلية من الصفحة.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## الخطوة 6: إضافة كائن الرسم البياني إلى الصفحة

نضيف كائن الرسم البياني إلى مجموعة فقرات الصفحة.

```csharp
pg.Paragraphs.Add(graph);
```

## الخطوة 7: حفظ ملف PDF الناتج

أخيرًا ، نحفظ ملف PDF الناتج باسم "DrawingLine_out.pdf" في الدليل المحدد.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Drawing Line باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل المستند
Document pDoc = new Document();
// أضف صفحة إلى مجموعة صفحات وثيقة PDF
Page pg = pDoc.Pages.Add();
// اضبط هامش الصفحة من جميع الجوانب على 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// قم بإنشاء كائن رسم بياني مع تساوي العرض والارتفاع أبعاد الصفحة
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// قم بإنشاء كائن سطر أول بدءًا من الزاوية السفلية اليسرى إلى الزاوية العلوية اليمنى من الصفحة
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// أضف خطًا إلى مجموعة أشكال كائن الرسم البياني
graph.Shapes.Add(line);
// ارسم خطًا من الزاوية العلوية اليسرى من الصفحة إلى الزاوية اليمنى السفلية من الصفحة
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// أضف خطًا إلى مجموعة أشكال كائن الرسم البياني
graph.Shapes.Add(line2);
// إضافة كائن رسم إلى مجموعة فقرات الصفحة
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// احفظ ملف PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية رسم خط باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء أشكال هندسية بخطوط مخصصة في ملفات PDF الخاصة بك.
