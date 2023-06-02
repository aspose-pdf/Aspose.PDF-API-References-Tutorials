---
title: طول اندفاعة
linktitle: طول اندفاعة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين طول الشرطات باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة لتخصيص أنماط اندفاعة.
type: docs
weight: 70
url: /ar/net/programming-with-graphs/dash-length/
---
في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة لتعيين طول الشرطات باستخدام Aspose.PDF for .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل أن تبدأ. لديك أيضًا معرفة أساسية ببرمجة C #.

## الخطوة 1: إعداد دليل المستند

في كود المصدر المقدم ، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير متغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند وإضافة صفحة

نقوم بإنشاء مثيل لفئة المستند وإضافة صفحة إلى هذا المستند.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن رسم وإضافته إلى الصفحة

نقوم بإنشاء كائن رسم بأبعاد محددة وإضافته إلى مجموعة فقرات الصفحة.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## الخطوة 4: إنشاء كائن الخط والتكوين

نقوم بإنشاء كائن Line بالإحداثيات المحددة وتكوين لون وطول الشرطات.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## الخطوة 5: إضافة السطر إلى كائن الرسم البياني

نضيف الخط إلى مجموعة الأشكال لكائن الرسم البياني.

```csharp
canvas.Shapes.Add(line);
```

## الخطوة 6: حفظ ملف PDF الناتج

أخيرًا ، نحفظ ملف PDF الناتج باسم "DashLength_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لطول داش باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// مثيل المستند
Document doc = new Document();
// أضف صفحة إلى مجموعة صفحات كائن المستند
Page page = doc.Pages.Add();
// إنشاء كائن رسومي بأبعاد معينة
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// إضافة كائن رسومي إلى مجموعة فقرات نسخة الصفحة
page.Paragraphs.Add(canvas);
// إنشاء كائن سطر
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// تعيين لون لكائن Line
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// حدد مصفوفة شرطة لكائن سطر
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// عيّن مرحلة الشرطة لمثيل Line
line.GraphInfo.DashPhase = 1;
// أضف خطًا إلى مجموعة أشكال الكائن الرسومي
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// احفظ مستند PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية تعيين طول الشرطات باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء خطوط ذات أنماط شرطة مخصصة في ملفات PDF الخاصة بك.
