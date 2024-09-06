---
title: إنشاء مستطيل مملوء
linktitle: إنشاء مستطيل مملوء
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إنشاء مستطيل مملوء باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتخصيص لون التعبئة.
type: docs
weight: 50
url: /ar/net/programming-with-graphs/create-filled-rectangle/
---
في هذا البرنامج التعليمي، سوف نرشدك خلال التعليمات البرمجية المصدرية C# خطوة بخطوة لإنشاء مستطيل مملوء باستخدام Aspose.PDF لـ .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل البدء. كما يجب أن يكون لديك معرفة أساسية ببرمجة C#.

## الخطوة 1: إعداد دليل المستندات

في الكود المصدر المقدم، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير المتغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مثيل مستند وإضافة صفحة

نقوم بإنشاء مثيل لفئة المستند ونضيف صفحة إلى هذا المستند.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن رسم بياني وإضافته إلى الصفحة

نقوم بإنشاء كائن رسم بياني بأبعاد محددة ونضيفه إلى مجموعة فقرات الصفحة.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## الخطوة 4: إنشاء كائن مستطيل وإضافته إلى الرسم البياني

نقوم بإنشاء كائن مستطيل بالأبعاد المحددة ونضيفه إلى مجموعة أشكال الرسم البياني.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## الخطوة 5: ضبط لون التعبئة

يمكننا تحديد لون التعبئة للمستطيل باستخدام خاصية FillColor في كائن GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## الخطوة 6: حفظ ملف PDF الناتج

وأخيرًا، نحفظ ملف PDF الناتج باسم "CreateFilledRectangle_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### عينة من كود المصدر لإنشاء مستطيل مملوء باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل المستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة صفحات ملف PDF
Page page = doc.Pages.Add();
// إنشاء مثيل للرسم البياني
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// إضافة كائن الرسم البياني إلى مجموعة فقرات مثيل الصفحة
page.Paragraphs.Add(graph);
// إنشاء مثيل المستطيل
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// تحديد لون التعبئة لكائن الرسم البياني
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// إضافة كائن مستطيل إلى مجموعة الأشكال الخاصة بكائن الرسم البياني
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية إنشاء مستطيل مملوء باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء أشكال هندسية بألوان تعبئة مخصصة في ملفات PDF الخاصة بك.

## الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: الغرض من هذا البرنامج التعليمي هو إرشادك خلال عملية إنشاء مستطيل مملوء باستخدام Aspose.PDF لـ .NET، مما يتيح لك إضافة أشكال هندسية مخصصة بألوان تعبئة إلى ملفات PDF الخاصة بك.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. بالإضافة إلى ذلك، يُنصح بالحصول على فهم أساسي لبرمجة C#.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: في الكود المصدر المقدم، يمكنك تعديل المتغير "dataDir" للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: ما هو الغرض من كائن الرسم البياني؟

أ: يعمل كائن الرسم البياني كحاوية لعناصر الرسم. يتم إنشاؤه بأبعاد محددة وإضافته إلى مجموعة فقرات الصفحة.

#### س: كيف يمكنني إضافة مستطيل مملوء إلى مستند PDF؟

أ: لإضافة مستطيل مملوء، قم بإنشاء مثيل لفئة المستطيل بأبعاد ولون تعبئة محددين، وأضفه إلى مجموعة أشكال الرسم البياني.

#### س: هل يمكنني تخصيص أبعاد ولون تعبئة المستطيل؟

 ج: نعم، يمكنك تخصيص أبعاد ولون تعبئة المستطيل عن طريق تعديل المعلمات المرسلة إلى`Aspose.Pdf.Drawing.Rectangle` المنشئ وتعيين خاصية FillColor.

#### س: كيف يمكنني حفظ ملف PDF الناتج بعد إنشاء المستطيل المملوء؟

 أ: بعد إنشاء المستطيل المملوء، يمكنك حفظ ملف PDF الناتج باستخدام`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` السطر الموجود في الكود المصدر المقدم.