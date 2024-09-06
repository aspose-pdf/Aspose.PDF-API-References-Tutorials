---
title: إنشاء مستطيل باستخدام اللون ألفا
linktitle: إنشاء مستطيل باستخدام اللون ألفا
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إنشاء مستطيل بلون شفاف باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتخصيص الشفافية.
type: docs
weight: 60
url: /ar/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
في هذا البرنامج التعليمي، سوف نرشدك خلال التعليمات البرمجية المصدرية C# خطوة بخطوة لإنشاء مستطيل بلون ألفا باستخدام Aspose.PDF لـ .NET.

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
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن رسم بياني ومستطيل

نقوم بإنشاء كائن رسم بياني بأبعاد محددة ومستطيل بأبعاد محددة.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## الخطوة 4: إعداد لون ألفا للمستطيل

يمكننا تحديد لون ألفا للمستطيل باستخدام طريقة FromArgb من فئة System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## الخطوة 5: إضافة المستطيل إلى كائن الرسم البياني

نضيف المستطيل إلى مجموعة الأشكال الخاصة بكائن الرسم البياني.

```csharp
canvas.Shapes.Add(rect);
```

## الخطوة 6: إنشاء مستطيل ثانٍ بلون ألفا مختلف

نقوم بإنشاء مستطيل ثاني بأبعاد محددة ولون ألفا آخر.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## الخطوة 7: إضافة كائن الرسم البياني إلى الصفحة

نضيف كائن الرسم البياني إلى مجموعة الفقرات الخاصة بكائن الصفحة.

```csharp
page.Paragraphs.Add(canvas);
```

## الخطوة 8: حفظ ملف PDF الناتج

وأخيرًا، نحفظ ملف PDF الناتج باسم "CreateRectangleWithAlphaColor_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### عينة من كود المصدر لإنشاء مستطيل بلون ألفا باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل مستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة صفحات ملف PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// إنشاء مثيل للرسم البياني
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// إنشاء كائن مستطيل بأبعاد محددة
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// تعيين لون تعبئة الرسم البياني من بنية System.Drawing.Color من قيمة ARGB 32 بت
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// إضافة كائن مستطيل إلى مجموعة الأشكال الخاصة بمثيل الرسم البياني
canvas.Shapes.Add(rect);
// إنشاء كائن مستطيل ثانٍ
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// إضافة مثيل الرسم البياني إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية إنشاء مستطيل بلون ألفا باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء أشكال هندسية بألوان شفافة في ملفات PDF الخاصة بك.

## الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية إنشاء مستطيل بلون ألفا باستخدام Aspose.PDF لـ .NET. ستتعلم كيفية إضافة أشكال هندسية بألوان شفافة إلى ملفات PDF الخاصة بك.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. بالإضافة إلى ذلك، يُنصح بالحصول على فهم أساسي لبرمجة C#.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: في الكود المصدر المقدم، يمكنك تعديل المتغير "dataDir" للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: ما هو الغرض من كائن الرسم البياني والمستطيل؟

أ: يعمل كائن الرسم البياني كحاوية لعناصر الرسم، بينما يمثل المستطيل الشكل الهندسي الذي ستضيفه إلى ملف PDF.

#### س: كيف يمكنني إعداد لون ألفا للمستطيل؟

 أ: يمكنك تحديد لون ألفا للمستطيل باستخدام`FillColor` ممتلكات`GraphInfo` الشيء و`Color.FromRgb` الطريقة مع قيمة ARGB.

#### س: هل يمكنني إنشاء مستطيلات متعددة بألوان ألفا مختلفة؟

ج: نعم، يمكنك إنشاء مستطيلات متعددة بألوان ألفا مختلفة باتباع الخطوات المماثلة الموضحة في البرنامج التعليمي.

#### س: كيف يمكنني حفظ ملف PDF الناتج بعد إنشاء مستطيلات بألوان ألفا؟

 أ: بعد إنشاء المستطيلات بألوان ألفا، يمكنك حفظ ملف PDF الناتج باستخدام`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` السطر الموجود في الكود المصدر المقدم.