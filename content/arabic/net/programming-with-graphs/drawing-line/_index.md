---
title: خط الرسم
linktitle: خط الرسم
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية رسم خط عبر صفحة باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لإنشاء خطوط مخصصة.
type: docs
weight: 80
url: /ar/net/programming-with-graphs/drawing-line/
---
في هذا البرنامج التعليمي، سوف نرشدك خلال التعليمات البرمجية المصدرية C# خطوة بخطوة لرسم خط باستخدام Aspose.PDF لـ .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل البدء. كما يجب أن يكون لديك معرفة أساسية ببرمجة C#.

## الخطوة 1: إعداد دليل المستندات

في الكود المصدر المقدم، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير المتغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مثيل مستند وإضافة صفحة

نقوم بإنشاء مثيل لفئة المستند ونضيف صفحة إلى هذا المستند.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## الخطوة 3: ضبط هوامش الصفحة

قمنا بضبط هوامش الصفحة على 0 على جميع الجوانب.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## الخطوة 4: إنشاء كائن الرسم البياني والسطر الأول

نقوم بإنشاء كائن رسم بياني بأبعاد مساوية لأبعاد الصفحة ونرسم الخط الأول الممتد من الزاوية السفلية اليسرى إلى الزاوية العلوية اليمنى للصفحة.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## الخطوة 5: رسم الخط الثاني

نرسم الخط الثاني من الزاوية العلوية اليسرى إلى الزاوية السفلية اليمنى للصفحة.

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

وأخيرًا، نحفظ ملف PDF الناتج باسم "DrawingLine_out.pdf" في الدليل المحدد.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### عينة من كود المصدر لرسم الخط باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل المستند
Document pDoc = new Document();
// إضافة صفحة إلى مجموعة الصفحات في مستند PDF
Page pg = pDoc.Pages.Add();
// تعيين هامش الصفحة على جميع الجوانب إلى 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// إنشاء كائن رسم بياني بعرض وارتفاع يساوي أبعاد الصفحة
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// إنشاء كائن السطر الأول بدءًا من الزاوية السفلية اليسرى إلى الزاوية العلوية اليمنى من الصفحة
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// إضافة خط إلى مجموعة الأشكال الخاصة بكائن الرسم البياني
graph.Shapes.Add(line);
// ارسم خطًا من الزاوية العلوية اليسرى للصفحة إلى الزاوية السفلية اليمنى للصفحة
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// إضافة خط إلى مجموعة الأشكال الخاصة بكائن الرسم البياني
graph.Shapes.Add(line2);
// إضافة كائن الرسم البياني إلى مجموعة فقرات الصفحة
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// حفظ ملف PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية رسم خط باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء أشكال هندسية بخطوط مخصصة في ملفات PDF الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: الغرض من هذا البرنامج التعليمي هو إرشادك خلال عملية رسم الخطوط باستخدام Aspose.PDF لـ .NET. ستتعلم كيفية إنشاء خطوط على صفحة PDF وتخصيص مظهرها.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. كما يُنصح أيضًا بمعرفة أساسية ببرمجة C#.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

أ: قم بتعديل المتغير "dataDir" في الكود المصدر المقدم للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: كيف أقوم بإنشاء خطوط على صفحة PDF؟

أ: يوضح البرنامج التعليمي كيفية إنشاء كائن رسم بياني بأبعاد الصفحة ثم إضافة كائنات خطية إليه. قم بتعديل إحداثيات وخصائص كائنات الخط لإنشاء الخطوط المطلوبة.

#### س: هل يمكنني تخصيص مظهر الخطوط؟

ج: نعم، يمكنك تخصيص مظهر الخطوط عن طريق تعديل خصائص كائنات الخطوط. ويتضمن ذلك تغيير إحداثياتها ولونها وسمكها وغير ذلك من السمات الرسومية.

#### س: كيف أحفظ مستند PDF بعد رسم الخطوط؟

 أ: بعد إضافة كائن الرسم البياني مع كائنات الخط إلى الصفحة، يمكنك حفظ مستند PDF الناتج باستخدام`pDoc.Save(dataDir + "DrawingLine_out.pdf");` السطر الموجود في الكود المصدر المقدم.

#### س: هل يمكنني رسم خطوط بزوايا واتجاهات مختلفة؟

ج: نعم، يمكنك رسم خطوط بزوايا واتجاهات مختلفة عن طريق ضبط إحداثيات وخصائص كائنات الخطوط داخل الرسم البياني.