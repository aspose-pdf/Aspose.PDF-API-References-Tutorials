---
title: طول الشرطة
linktitle: طول الشرطة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية ضبط طول الشرطات باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتخصيص أنماط الشرطة.
type: docs
weight: 70
url: /ar/net/programming-with-graphs/dash-length/
---
في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# التالية خطوة بخطوة لتعيين طول الشرطات باستخدام Aspose.PDF لـ .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل البدء. لديك أيضًا معرفة أساسية ببرمجة C#.

## الخطوة 1: إعداد دليل المستندات

في كود المصدر المقدم، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير المتغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند وإضافة صفحة

نقوم بإنشاء مثيل لفئة المستند وإضافة صفحة إلى هذا المستند.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن رسم بياني وإضافته إلى الصفحة

نقوم بإنشاء كائن رسم بياني بأبعاد محددة ونضيفه إلى مجموعة فقرات الصفحة.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## الخطوة 4: إنشاء كائن خط وتكوينه

نقوم بإنشاء كائن خطي بالإحداثيات المحددة ونقوم بتكوين لون الشرطات وطولها.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## الخطوة 5: إضافة الخط إلى كائن الرسم البياني

نضيف السطر إلى مجموعة أشكال كائن الرسم البياني.

```csharp
canvas.Shapes.Add(line);
```

## الخطوة 6: حفظ ملف PDF الناتج

أخيرًا، نقوم بحفظ ملف PDF الناتج بالاسم "DashLength_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Dash Length باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل للمستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة صفحات كائن المستند
Page page = doc.Pages.Add();
// إنشاء كائن رسومي بأبعاد معينة
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// إضافة كائن رسومي إلى مجموعة الفقرات من مثيل الصفحة
page.Paragraphs.Add(canvas);
// إنشاء كائن الخط
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// تعيين اللون لكائن الخط
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// تحديد صفيف الشرطة لكائن الخط
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// قم بتعيين مرحلة الشرطة لمثيل الخط
line.GraphInfo.DashPhase = 1;
// إضافة خط إلى مجموعة أشكال الكائن الرسومي
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية ضبط طول الشرطات باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء خطوط بأنماط الشرطة المخصصة في ملفات PDF الخاصة بك.

## الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: الغرض من هذا البرنامج التعليمي هو إرشادك خلال عملية تعيين طول الشرطات للأسطر باستخدام Aspose.PDF لـ .NET. ستتعلم كيفية إنشاء خطوط بأنماط متقطعة مخصصة في ملفات PDF الخاصة بك.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل البدء، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. يوصى أيضًا بالفهم الأساسي لبرمجة C#.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: قم بتعديل متغير "dataDir" في كود المصدر المقدم للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: كيف يمكنني إنشاء خط بأنماط متقطعة مخصصة؟

 ج: يوضح البرنامج التعليمي إنشاء كائن خطي وتكوين لونه ومصفوفة الشرطة ومرحلة الشرطة باستخدام`GraphInfo` هدف. قم بتعديل هذه الإعدادات لتحقيق نمط الشرطة المطلوب.

#### س: هل يمكنني تخصيص لون الخط؟

 ج: نعم، يمكنك تخصيص لون الخط عن طريق ضبط اللون`Color` ملكية`GraphInfo` الكائن المرتبط بالخط.

#### س: كيف يمكنني حفظ مستند PDF بعد ضبط طول الشرطة؟

 ج: بعد تكوين كائن الخط بنمط الشرطة المرغوب فيه، يمكنك حفظ مستند PDF الناتج باستخدام الملف`doc.Save(dataDir + "DashLength_out.pdf");` سطر في كود المصدر المقدم.