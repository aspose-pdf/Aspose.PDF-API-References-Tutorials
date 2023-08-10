---
title: إنشاء مستطيل مع ألفا اللون
linktitle: إنشاء مستطيل مع ألفا اللون
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء مستطيل بلون شفاف باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة لتخصيص الشفافية.
type: docs
weight: 60
url: /ar/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة لإنشاء مستطيل بلون ألفا باستخدام Aspose.PDF for .NET.

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
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن رسم ومستطيل

نقوم بإنشاء كائن رسم بأبعاد محددة ومستطيل بأبعاد محددة.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## الخطوة 4: إعداد لون ألفا للمستطيل

يمكننا تحديد لون ألفا للمستطيل باستخدام طريقة FromArgb لفئة System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## الخطوة 5: إضافة المستطيل إلى كائن الرسم البياني

نضيف المستطيل إلى مجموعة الأشكال لكائن الرسم البياني.

```csharp
canvas.Shapes.Add(rect);
```

## الخطوة 6: إنشاء مستطيل آخر بلون ألفا مختلف

نقوم بإنشاء مستطيل ثان بأبعاد محددة ولون ألفا آخر.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## الخطوة 7: إضافة كائن الرسم البياني إلى الصفحة

نضيف كائن الرسم البياني إلى مجموعة فقرة كائن الصفحة.

```csharp
page.Paragraphs.Add(canvas);
```

## الخطوة 8: حفظ ملف PDF الناتج

أخيرًا ، نحفظ ملف PDF الناتج باسم "CreateRectangleWithAlphaColor_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Create Rectangle With Alpha Color باستخدام Aspose.PDF for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// مثيل المستند
Document doc = new Document();
// أضف صفحة إلى مجموعة صفحات من ملف PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// إنشاء مثيل الرسم البياني
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// إنشاء كائن مستطيل بأبعاد محددة
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//عيّن لون تعبئة الرسم البياني من بنية System.Drawing.Color من قيمة ARGB 32 بت
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// أضف كائن مستطيل إلى مجموعة الأشكال لمثيل الرسم البياني
canvas.Shapes.Add(rect);
// إنشاء كائن المستطيل الثاني
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// إضافة مثيل الرسم البياني إلى مجموعة فقرة من كائن الصفحة
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية إنشاء مستطيل بلون ألفا باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء أشكال هندسية بألوان شفافة في ملفات PDF الخاصة بك.

## التعليمات

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية إنشاء مستطيل بلون ألفا باستخدام Aspose.PDF for .NET. ستتعلم كيفية إضافة أشكال هندسية بألوان شفافة إلى ملفات PDF الخاصة بك.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. بالإضافة إلى ذلك ، يوصى بوجود فهم أساسي لبرمجة C #.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: في التعليمات البرمجية المصدر المتوفرة ، يمكنك تعديل متغير "dataDir" للإشارة إلى الدليل حيث تريد حفظ ملف PDF الناتج.

#### س: ما هو الغرض من كائن الرسم البياني والمستطيل؟

ج: يعمل كائن الرسم البياني كحاوية لعناصر الرسم ، بينما يمثل المستطيل الشكل الهندسي الذي ستضيفه إلى ملف PDF.

#### س: كيف يمكنني إعداد لون ألفا للمستطيل؟

ج: يمكنك تحديد لون ألفا للمستطيل باستخدام تنسيق`FillColor` ممتلكات`GraphInfo` الكائن و`Color.FromRgb` طريقة بقيمة ARGB.

#### س: هل يمكنني إنشاء مستطيلات متعددة بألوان ألفا مختلفة؟

ج: نعم ، يمكنك إنشاء مستطيلات متعددة بألوان ألفا مختلفة باتباع خطوات مماثلة كما هو موضح في البرنامج التعليمي.

#### س: كيف أحفظ ملف PDF الناتج بعد إنشاء مستطيلات بألوان ألفا؟

 ج: بعد إنشاء المستطيلات بألوان ألفا ، يمكنك حفظ ملف PDF الناتج باستخدام امتداد`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` سطر في شفرة المصدر المقدمة.