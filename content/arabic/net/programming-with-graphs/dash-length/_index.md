---
title: طول الشرطة
linktitle: طول الشرطة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تعيين طول الشرطات باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتخصيص أنماط الشرطات.
type: docs
weight: 70
url: /ar/net/programming-with-graphs/dash-length/
---
في هذا البرنامج التعليمي، سوف نرشدك خلال التعليمات البرمجية المصدرية C# التالية خطوة بخطوة لتعيين طول الشرطات باستخدام Aspose.PDF لـ .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل البدء. كما يجب أن يكون لديك معرفة أساسية ببرمجة C#.

## الخطوة 1: إعداد دليل المستندات

في الكود المصدر المقدم، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير المتغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند وإضافة صفحة

نقوم بإنشاء مثيل لفئة المستند ونضيف صفحة إلى هذا المستند.

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

## الخطوة 4: إنشاء كائن خطي وتكوينه

نقوم بإنشاء كائن خطي بالإحداثيات المحددة ونقوم بتكوين لون وطول الشرطات.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## الخطوة 5: إضافة الخط إلى كائن الرسم البياني

نضيف الخط إلى مجموعة الأشكال الخاصة بكائن الرسم البياني.

```csharp
canvas.Shapes.Add(line);
```

## الخطوة 6: حفظ ملف PDF الناتج

وأخيرًا، نحفظ ملف PDF الناتج باسم "DashLength_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### عينة من كود المصدر لـ Dash Length باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل مستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة الصفحات الخاصة بكائن المستند
Page page = doc.Pages.Add();
// إنشاء كائن رسم بأبعاد معينة
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// إضافة كائن رسومي إلى مجموعة فقرات مثيل الصفحة
page.Paragraphs.Add(canvas);
// إنشاء كائن خطي
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// تعيين اللون لكائن الخط
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// تحديد مجموعة شرطة لكائن الخط
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// تعيين مرحلة الشرطة لنموذج الخط
line.GraphInfo.DashPhase = 1;
// إضافة خط إلى مجموعة أشكال كائن الرسم
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// حفظ مستند PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية تعيين طول الشرطات باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء خطوط بأنماط شرطات مخصصة في ملفات PDF الخاصة بك.

## الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: الغرض من هذا البرنامج التعليمي هو إرشادك خلال عملية تحديد طول الشرطات للأسطر باستخدام Aspose.PDF لـ .NET. ستتعلم كيفية إنشاء خطوط بأنماط شرطات مخصصة في ملفات PDF الخاصة بك.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل البدء، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. كما يُنصح أيضًا بفهم أساسيات برمجة C#.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

أ: قم بتعديل المتغير "dataDir" في الكود المصدر المقدم للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: كيف أقوم بإنشاء خط باستخدام أنماط شرطة مخصصة؟

 أ: يوضح البرنامج التعليمي إنشاء كائن خط وتكوين لونه ومجموعة الشرطة ومرحلة الشرطة باستخدام`GraphInfo` الكائن. قم بتعديل هذه الإعدادات لتحقيق نمط الشرطة المطلوب.

#### س: هل يمكنني تخصيص لون الخط؟

 ج: نعم، يمكنك تخصيص لون الخط عن طريق ضبط`Color` ممتلكات`GraphInfo` الكائن المرتبط بالخط.

#### س: كيف يمكنني حفظ مستند PDF بعد تعيين طول الشرطة؟

 أ: بعد تكوين كائن الخط باستخدام نمط الشرطة المطلوب، يمكنك حفظ مستند PDF الناتج باستخدام`doc.Save(dataDir + "DashLength_out.pdf");` السطر الموجود في الكود المصدر المقدم.