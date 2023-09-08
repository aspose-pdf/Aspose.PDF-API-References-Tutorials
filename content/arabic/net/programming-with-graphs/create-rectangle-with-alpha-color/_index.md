---
title: إنشاء مستطيل مع لون ألفا
linktitle: إنشاء مستطيل مع لون ألفا
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء مستطيل بلون شفاف باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتخصيص الشفافية.
type: docs
weight: 60
url: /ar/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# التالية خطوة بخطوة لإنشاء مستطيل بلون ألفا باستخدام Aspose.PDF لـ .NET.

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
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن رسم بياني ومستطيل

نقوم بإنشاء كائن رسم بياني بأبعاد محددة ومستطيل بأبعاد محددة.

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

نضيف المستطيل إلى مجموعة أشكال كائن الرسم البياني.

```csharp
canvas.Shapes.Add(rect);
```

## الخطوة 6: إنشاء مستطيل ثانٍ بلون ألفا مختلف

نقوم بإنشاء مستطيل ثانٍ بأبعاد محددة ولون ألفا آخر.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## الخطوة 7: إضافة كائن الرسم البياني إلى الصفحة

نضيف كائن الرسم البياني إلى مجموعة الفقرة الخاصة بكائن الصفحة.

```csharp
page.Paragraphs.Add(canvas);
```

## الخطوة 8: حفظ ملف PDF الناتج

أخيرًا، نقوم بحفظ ملف PDF الناتج بالاسم "CreateRectangleWithAlphaColor_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لإنشاء مستطيل باستخدام Alpha Color باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل للمستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة الصفحات من ملف PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// إنشاء مثيل الرسم البياني
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// إنشاء كائن مستطيل بأبعاد محددة
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//قم بتعيين لون تعبئة الرسم البياني من بنية System.Drawing.Color من قيمة ARGB 32 بت
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// إضافة كائن مستطيل إلى مجموعة الأشكال لمثيل الرسم البياني
canvas.Shapes.Add(rect);
// إنشاء كائن المستطيل الثاني
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// إضافة مثيل الرسم البياني إلى مجموعة الفقرة من كائن الصفحة
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

ج: قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. بالإضافة إلى ذلك، يوصى بالحصول على فهم أساسي لبرمجة C#.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: في الكود المصدري المقدم، يمكنك تعديل متغير "dataDir" للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: ما هو الغرض من كائن الرسم البياني والمستطيل؟

ج: يعمل كائن Graph كحاوية لعناصر الرسم، بينما يمثل المستطيل الشكل الهندسي الذي ستضيفه إلى ملف PDF.

#### س: كيف يمكنني إعداد لون ألفا للمستطيل؟

ج: يمكنك تحديد لون ألفا للمستطيل باستخدام`FillColor` ملكية`GraphInfo` الكائن و`Color.FromRgb` الطريقة بقيمة ARGB.

#### س: هل يمكنني إنشاء مستطيلات متعددة بألوان ألفا مختلفة؟

ج: نعم، يمكنك إنشاء مستطيلات متعددة بألوان ألفا مختلفة عن طريق اتباع خطوات مماثلة كما هو موضح في البرنامج التعليمي.

#### س: كيف يمكنني حفظ ملف PDF الناتج بعد إنشاء مستطيلات بألوان ألفا؟

 ج: بعد إنشاء المستطيلات بألوان ألفا، يمكنك حفظ ملف PDF الناتج باستخدام الملف`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` سطر في كود المصدر المقدم.