---
title: إضافة كائن خطي
linktitle: إضافة كائن خطي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة كائن سطر مخصص في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-graphs/add-line-object/
---
في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة لإضافة كائن سطر باستخدام Aspose.PDF for .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل أن تبدأ. لديك أيضًا معرفة أساسية ببرمجة C #.

## الخطوة 1: إعداد دليل المستند

في كود المصدر المقدم ، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير متغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مثيل مستند وإضافة صفحة

نقوم بإنشاء مثيل لفئة المستند وإضافة صفحة إلى هذا المستند.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن رسم وإضافته إلى الصفحة

نقوم بإنشاء كائن رسم بأبعاد محددة وإضافته إلى مجموعة فقرات الصفحة.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## الخطوة 4: إنشاء عنصر خط وإضافة إلى الرسم البياني

نقوم بإنشاء كائن Line بالإحداثيات المحددة وإضافته إلى مجموعة أشكال الرسم البياني.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## الخطوة 5: إعداد الخط

يمكننا تحديد خصائص الخط ، مثل نوع الشرطة ومرحلة الشرطة.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## الخطوة السادسة: حفظ ملف PDF

أخيرًا ، نحفظ ملف PDF الناتج باسم "AddLineObject_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Add Line Object باستخدام Aspose.PDF for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل المستند
Document doc = new Document();
// أضف صفحة إلى مجموعة صفحات من ملف PDF
Page page = doc.Pages.Add();
// إنشاء مثيل الرسم البياني
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// أضف كائن الرسم البياني إلى مجموعة فقرات نسخة الصفحة
page.Paragraphs.Add(graph);
// إنشاء مثيل المستطيل
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// حدد لون التعبئة لكائن الرسم البياني
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// أضف كائن مستطيل إلى مجموعة أشكال لكائن الرسم البياني
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي ، أوضحنا خطوة بخطوة كيفية إضافة كائن سطر باستخدام Aspose.PDF for .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء مستندات PDF بخطوط مخصصة في تطبيقاتك.
