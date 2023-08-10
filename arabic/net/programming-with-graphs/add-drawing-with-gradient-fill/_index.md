---
title: أضف الرسم بتعبئة متدرجة
linktitle: أضف الرسم بتعبئة متدرجة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة رسم بتعبئة متدرجة باستخدام Aspose.PDF for .NET. برنامج تعليمي خطوة بخطوة لإنشاء مستندات PDF جذابة.
type: docs
weight: 20
url: /ar/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
في هذا البرنامج التعليمي ، سنرشدك عبر التعليمات البرمجية المصدر C # التالية خطوة بخطوة لإضافة رسم بتعبئة متدرجة إلى البرمجة باستخدام الرسومات باستخدام Aspose.PDF for .NET.

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
Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن رسم وإضافته إلى الصفحة

نقوم بإنشاء كائن رسم بأبعاد محددة وإضافته إلى مجموعة فقرات الصفحة.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## الخطوة 4: إنشاء كائن مستطيل وإضافة إلى الرسم البياني

نقوم بإنشاء كائن مستطيل بأبعاد محددة وإضافته إلى مجموعة أشكال الرسم البياني.

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

يؤدي هذا إلى إنشاء تعبئة متدرجة من الأحمر إلى الأزرق ، من النقطة (0 ، 0) إلى النقطة (300 ، 300).

## الخطوة السادسة: حفظ ملف PDF

أخيرًا ، نحفظ ملف PDF الناتج باسم "AddDrawingWithGradientFill_out.pdf" في الدليل المحدد.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Add Drawing With Gradient Fill باستخدام Aspose.PDF for .NET 

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

في هذا البرنامج التعليمي ، أوضحنا خطوة بخطوة كيفية إضافة رسم بتعبئة متدرجة إلى البرمجة باستخدام الرسومات باستخدام Aspose.PDF for .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء مستندات PDF جذابة بتصميمات مخصصة وتعبئة متدرجة.

### التعليمات

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية إضافة رسم بتعبئة متدرجة إلى البرمجة باستخدام الرسومات باستخدام Aspose.PDF for .NET.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. بالإضافة إلى ذلك ، يوصى بوجود فهم أساسي لبرمجة C #.

#### س: كيف أحدد الدليل لحفظ ملف PDF؟

ج: في الكود المصدري المتوفر ، يمكنك تغيير قيمة متغير "dataDir" للإشارة إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: ما هو الغرض من كائن الرسم البياني؟

ج: يعمل كائن الرسم البياني كحاوية لعناصر الرسم. يتم إنشاؤه بأبعاد محددة وإضافته إلى مجموعة فقرات الصفحة.

#### س: كيف يمكنني تكوين تعبئة متدرجة لشكل؟

ج: لتكوين تعبئة متدرجة ، يمكنك تعيين خاصية FillColor الخاصة بـ GraphInfo للشكل باستخدام فئة GradientAxialShading. يتيح لك ذلك تحديد نقطتي البداية والنهاية للتدرج اللوني والألوان المراد الانتقال بينها.

#### س: هل يمكنني تخصيص الألوان واتجاه التعبئة المتدرجة؟

ج: نعم ، يمكنك تخصيص ألوان واتجاه التعبئة المتدرجة عن طريق ضبط كائنات اللون وتحديد نقطتي البداية والنهاية لـ GradientAxialShading.

#### س: ما هي الخطوة الأخيرة من البرنامج التعليمي؟

ج: تتضمن الخطوة الأخيرة حفظ ملف PDF الناتج باسم "AddDrawingWithGradientFill_out.pdf" في الدليل المحدد.

#### س: هل يتوفر نموذج لشفرة المصدر؟

ج: نعم ، يوفر البرنامج التعليمي عينة من التعليمات البرمجية المصدر التي يمكنك استخدامها كمرجع لتنفيذ الخطوات الموضحة.

#### س: هل يمكنني تطبيق تعبئة متدرجة على أشكال أخرى غير المستطيلات؟

ج: نعم ، يمكنك تطبيق تعبئة متدرجة على أشكال أخرى أيضًا. تتضمن العملية تكوين خاصية FillColor الخاصة بالشكل GraphInfo باستخدام فئة GradientAxialShading.