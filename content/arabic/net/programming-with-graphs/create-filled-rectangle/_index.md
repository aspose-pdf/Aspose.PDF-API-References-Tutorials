---
title: إنشاء مستطيل معبأ
linktitle: إنشاء مستطيل معبأ
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء مستطيل معبأ باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتخصيص لون التعبئة.
type: docs
weight: 50
url: /ar/net/programming-with-graphs/create-filled-rectangle/
---
في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# التالية خطوة بخطوة لإنشاء مستطيل معبأ باستخدام Aspose.PDF لـ .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل البدء. لديك أيضًا معرفة أساسية ببرمجة C#.

## الخطوة 1: إعداد دليل المستندات

في كود المصدر المقدم، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير المتغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مثيل مستند وإضافة صفحة

نقوم بإنشاء مثيل لفئة المستند وإضافة صفحة إلى هذا المستند.

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

## الخطوة 4: إنشاء كائن مستطيل وإضافته إلى المخطط

نقوم بإنشاء كائن مستطيل بالأبعاد المحددة ونضيفه إلى مجموعة أشكال المخطط.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## الخطوة 5: تحديد لون التعبئة

يمكننا تحديد لون التعبئة للمستطيل باستخدام خاصية fillColor لكائن GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## الخطوة 6: حفظ ملف PDF الناتج

أخيرًا، نقوم بحفظ ملف PDF الناتج بالاسم "CreateFilledRectangle_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لإنشاء مستطيل معبأ باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل المستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة الصفحات من ملف PDF
Page page = doc.Pages.Add();
// إنشاء مثيل الرسم البياني
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// إضافة كائن الرسم البياني إلى مجموعة الفقرات من مثيل الصفحة
page.Paragraphs.Add(graph);
// إنشاء مثيل مستطيل
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// تحديد لون التعبئة لكائن الرسم البياني
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// إضافة كائن مستطيل إلى مجموعة أشكال كائن الرسم البياني
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية إنشاء مستطيل معبأ باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء أشكال هندسية بألوان تعبئة مخصصة في ملفات PDF الخاصة بك.

## الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: الغرض من هذا البرنامج التعليمي هو إرشادك خلال عملية إنشاء مستطيل معبأ باستخدام Aspose.PDF لـ .NET، مما يتيح لك إضافة أشكال هندسية مخصصة بألوان التعبئة إلى ملفات PDF الخاصة بك.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. بالإضافة إلى ذلك، يوصى بالحصول على فهم أساسي لبرمجة C#.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: في الكود المصدري المقدم، يمكنك تعديل متغير "dataDir" للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: ما هو الغرض من كائن الرسم البياني؟

ج: يعمل كائن الرسم البياني كحاوية لعناصر الرسم. يتم إنشاؤه بأبعاد محددة وإضافته إلى مجموعة فقرات الصفحة.

#### س: كيف يمكنني إضافة مستطيل مملوء إلى مستند PDF؟

ج: لإضافة مستطيل معبأ، قم بإنشاء مثيل لفئة المستطيل بأبعاد ولون تعبئة محددين، ثم قم بإضافته إلى مجموعة أشكال الرسم البياني.

#### س: هل يمكنني تخصيص الأبعاد ولون تعبئة المستطيل؟

 ج: نعم، يمكنك تخصيص الأبعاد ولون تعبئة المستطيل عن طريق تعديل المعلمات التي تم تمريرها إلى`Aspose.Pdf.Drawing.Rectangle` منشئ وتعيين خاصية fillColor.

#### س: كيف يمكنني حفظ ملف PDF الناتج بعد إنشاء المستطيل المعبأ؟

 ج: بعد إنشاء المستطيل المملوء، يمكنك حفظ ملف PDF الناتج باستخدام الملف`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` سطر في كود المصدر المقدم.