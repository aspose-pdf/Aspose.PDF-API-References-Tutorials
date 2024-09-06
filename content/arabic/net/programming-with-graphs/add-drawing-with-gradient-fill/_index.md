---
title: إضافة رسم باستخدام التعبئة المتدرجة
linktitle: إضافة رسم باستخدام التعبئة المتدرجة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة رسم بتعبئة متدرجة باستخدام Aspose.PDF لـ .NET. برنامج تعليمي خطوة بخطوة لإنشاء مستندات PDF جذابة.
type: docs
weight: 20
url: /ar/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
في هذا البرنامج التعليمي، سوف نرشدك خلال التعليمات البرمجية المصدرية C# التالية خطوة بخطوة لإضافة رسم مع تعبئة متدرجة إلى البرمجة بالرسومات باستخدام Aspose.PDF لـ .NET.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## الخطوة 4: إنشاء كائن مستطيل وإضافته إلى الرسم البياني

نقوم بإنشاء كائن مستطيل بأبعاد محددة ونضيفه إلى مجموعة أشكال الرسم البياني.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## الخطوة 5: تكوين التعبئة المتدرجة

نقوم بإعداد تعبئة التدرج للمستطيل باستخدام فئة GradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

يؤدي هذا إلى إنشاء تعبئة متدرجة من الأحمر إلى الأزرق، من النقطة (0، 0) إلى النقطة (300، 300).

## الخطوة 6: حفظ ملف PDF

وأخيرًا، نقوم بحفظ ملف PDF الناتج باسم "AddDrawingWithGradientFill_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### عينة من كود المصدر لإضافة رسم مع تعبئة متدرجة باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## خاتمة

في هذا البرنامج التعليمي، شرحنا خطوة بخطوة كيفية إضافة رسم بتعبئة متدرجة إلى البرمجة بالرسومات باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء مستندات PDF جذابة بتصميمات مخصصة وتعبئة متدرجة.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

أ: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية إضافة رسم باستخدام التعبئة المتدرجة إلى البرمجة بالرسومات باستخدام Aspose.PDF لـ .NET.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. بالإضافة إلى ذلك، يُنصح بالحصول على فهم أساسي لبرمجة C#.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: في الكود المصدر المقدم، يمكنك تغيير قيمة المتغير "dataDir" للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: ما هو الغرض من كائن الرسم البياني؟

أ: يعمل كائن الرسم البياني كحاوية لعناصر الرسم. يتم إنشاؤه بأبعاد محددة وإضافته إلى مجموعة فقرات الصفحة.

#### س: كيف يمكنني تكوين التعبئة المتدرجة لشكل ما؟

ج: لتكوين التعبئة المتدرجة، يمكنك تعيين خاصية FillColor لـ GraphInfo الخاص بالشكل باستخدام فئة GradientAxialShading. يتيح لك هذا تحديد نقاط البداية والنهاية للتدرج والألوان التي سيتم الانتقال بينها.

#### س: هل يمكنني تخصيص الألوان واتجاه التعبئة المتدرجة؟

ج: نعم، يمكنك تخصيص الألوان واتجاه التعبئة المتدرجة عن طريق ضبط كائنات اللون وتحديد نقاط البداية والنهاية لـ GradientAxialShading.

#### س: ما هي الخطوة النهائية من البرنامج التعليمي؟

ج: تتضمن الخطوة الأخيرة حفظ ملف PDF الناتج باسم "AddDrawingWithGradientFill_out.pdf" في الدليل المحدد.

#### س: هل هناك نموذج لرمز المصدر متاح؟

ج: نعم، يوفر البرنامج التعليمي نموذجًا لرمز المصدر الذي يمكنك استخدامه كمرجع لتنفيذ الخطوات الموضحة.

#### س: هل يمكنني تطبيق التعبئة المتدرجة على أشكال أخرى غير المستطيلات؟

ج: نعم، يمكنك أيضًا تطبيق التعبئة المتدرجة على أشكال أخرى. تتضمن العملية تكوين خاصية FillColor في GraphInfo الخاص بالشكل باستخدام فئة GradientAxialShading.