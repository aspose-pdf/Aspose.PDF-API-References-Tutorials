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

### نموذج التعليمات البرمجية المصدر لطول داش باستخدام Aspose.PDF لـ .NET 

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

## أسئلة وأجوبة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: الغرض من هذا البرنامج التعليمي هو إرشادك خلال عملية تعيين طول الشرطات للخطوط باستخدام Aspose.PDF لـ .NET. ستتعلم كيفية إنشاء خطوط بأنماط شرطة مخصصة في ملفات PDF الخاصة بك.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. يوصى أيضًا بفهم أساسي لبرمجة C #.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: قم بتعديل متغير "dataDir" في كود المصدر المقدم للإشارة إلى الدليل حيث تريد حفظ ملف PDF الناتج.

#### س: كيف أقوم بإنشاء خط به أنماط شرطة مخصصة؟

 ج: يوضح البرنامج التعليمي إنشاء كائن Line وتكوين لونه وصفيف شرطة ومرحلة شرطة باستخدام`GraphInfo` هدف. قم بتعديل هذه الإعدادات لتحقيق نمط الشرطة المطلوب.

#### س: هل يمكنني تخصيص لون الخط؟

 ج: نعم ، يمكنك تخصيص لون الخط عن طريق ضبط`Color` ممتلكات`GraphInfo` كائن مرتبط بالخط.

#### س: كيف أحفظ مستند PDF بعد تعيين طول الشرطة؟

 ج: بعد تكوين كائن Line بنمط الشرطة المطلوب ، يمكنك حفظ مستند PDF الناتج باستخدام ملف`doc.Save(dataDir + "DashLength_out.pdf");` سطر في شفرة المصدر المقدمة.