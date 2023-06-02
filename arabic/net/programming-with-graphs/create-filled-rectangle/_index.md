---
title: إنشاء مستطيل معبأ
linktitle: إنشاء مستطيل معبأ
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء مستطيل معبأ باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة لتخصيص لون التعبئة.
type: docs
weight: 50
url: /ar/net/programming-with-graphs/create-filled-rectangle/
---
في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة لإنشاء مستطيل مملوء باستخدام Aspose.PDF for .NET.

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

## الخطوة 4: إنشاء كائن مستطيل وإضافة إلى الرسم البياني

نقوم بإنشاء كائن مستطيل بأبعاد محددة وإضافته إلى مجموعة أشكال الرسم البياني.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## الخطوة 5: ضبط لون التعبئة

يمكننا تحديد لون التعبئة للمستطيل باستخدام خاصية FillColor للكائن GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## الخطوة 6: حفظ ملف PDF الناتج

أخيرًا ، نحفظ ملف PDF الناتج باسم "CreateFilledRectangle_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Create Filled Rectangle باستخدام Aspose.Words for .NET 

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
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// حدد لون التعبئة لكائن الرسم البياني
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// أضف كائن مستطيل إلى مجموعة أشكال لكائن الرسم البياني
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية إنشاء مستطيل ممتلئ باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء أشكال هندسية بألوان تعبئة مخصصة في ملفات PDF الخاصة بك.
