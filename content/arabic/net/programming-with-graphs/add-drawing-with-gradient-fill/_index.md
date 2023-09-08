---
title: إضافة رسم مع تعبئة متدرجة
linktitle: إضافة رسم مع تعبئة متدرجة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة رسم بتعبئة متدرجة باستخدام Aspose.PDF لـ .NET. برنامج تعليمي خطوة بخطوة لإنشاء مستندات PDF جذابة.
type: docs
weight: 20
url: /ar/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# التالية خطوة بخطوة لإضافة رسم بتعبئة متدرجة إلى البرمجة باستخدام الرسومات باستخدام Aspose.PDF لـ .NET.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## الخطوة 4: إنشاء كائن مستطيل وإضافته إلى المخطط

نقوم بإنشاء كائن مستطيل بأبعاد محددة ونضيفه إلى مجموعة أشكال المخطط.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## الخطوة 5: تكوين التعبئة المتدرجة

نقوم بتكوين التعبئة المتدرجة للمستطيل باستخدام فئة GradientAxialShading.

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

أخيرًا، نقوم بحفظ ملف PDF الناتج بالاسم "AddDrawingWithGradientFill_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لإضافة رسم باستخدام تعبئة متدرجة باستخدام Aspose.PDF لـ .NET 

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

في هذا البرنامج التعليمي، شرحنا خطوة بخطوة كيفية إضافة رسم بتعبئة متدرجة إلى برمجة الرسومات باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء مستندات PDF جذابة بتصميمات مخصصة وتعبئة متدرجة.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية إضافة رسم بتعبئة متدرجة إلى برمجة الرسومات باستخدام Aspose.PDF لـ .NET.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. بالإضافة إلى ذلك، يوصى بالحصول على فهم أساسي لبرمجة C#.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: في الكود المصدري المقدم، يمكنك تغيير قيمة المتغير "dataDir" للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: ما هو الغرض من كائن الرسم البياني؟

ج: يعمل كائن الرسم البياني كحاوية لعناصر الرسم. يتم إنشاؤه بأبعاد محددة وإضافته إلى مجموعة فقرات الصفحة.

#### س: كيف يمكنني تكوين التعبئة المتدرجة للشكل؟

ج: لتكوين التعبئة المتدرجة، يمكنك تعيين خاصية fillColor الخاصة بـ GraphInfo للشكل باستخدام فئة GradientAxialShading. يتيح لك هذا تحديد نقاط البداية والنهاية للتدرج والألوان التي سيتم الانتقال بينها.

#### س: هل يمكنني تخصيص الألوان واتجاه التعبئة المتدرجة؟

ج: نعم، يمكنك تخصيص الألوان واتجاه التعبئة المتدرجة عن طريق ضبط كائنات اللون وتحديد نقاط البداية والنهاية لـ GradientAxialShading.

#### س: ما هي الخطوة الأخيرة من البرنامج التعليمي؟

ج: تتضمن الخطوة الأخيرة حفظ ملف PDF الناتج بالاسم "AddDrawingWithGradientFill_out.pdf" في الدليل المحدد.

#### س: هل هناك نموذج للكود المصدري متاح؟

ج: نعم، يوفر البرنامج التعليمي نموذجًا للتعليمات البرمجية المصدرية التي يمكنك استخدامها كمرجع لتنفيذ الخطوات الموضحة.

#### س: هل يمكنني تطبيق تعبئة متدرجة على أشكال أخرى إلى جانب المستطيلات؟

ج: نعم، يمكنك تطبيق تعبئة متدرجة على الأشكال الأخرى أيضًا. تتضمن العملية تكوين خاصية fillColor الخاصة بـ GraphInfo للشكل باستخدام فئة GradientAxialShading.