---
title: احصل على عرض النص ديناميكيًا
linktitle: احصل على عرض النص ديناميكيًا
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية الحصول على عرض النص ديناميكيًا باستخدام Aspose.PDF for .NET.
type: docs
weight: 220
url: /ar/net/programming-with-text/get-width-of-text-dynamically/
---

في هذا البرنامج التعليمي ، سنشرح كيفية استخدام Aspose.PDF for .NET لقياس عرض النص ديناميكيًا في C #. يمكن أن يكون هذا مفيدًا عندما تحتاج إلى تحديد حجم سلسلة نصية قبل عرضها على مستند PDF. سنوجهك عبر كود المصدر C # المقدم خطوة بخطوة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- Visual Studio أو أي بيئة تطوير C # أخرى.

## الخطوة 1: قم بتعيين دليل المستندات

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"`مع المسار إلى الدليل حيث توجد المستندات الخاصة بك. سيتم استخدام هذا لتخزين أي ملفات PDF تم إنشاؤها.

## الخطوة 2: ابحث عن الخط

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
```

 يجد الكود أعلاه الخط Arial باستخدام ملف`FindFont` طريقة من`FontRepository` فصل. إذا كنت تريد استخدام خط مختلف ، فاستبدل`"Arial"` مع اسم الخط المطلوب.

## الخطوة 3: اضبط حالة النص

```csharp
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
```

 هنا ، نقوم بإنشاء ملف`TextState` الكائن وتعيين خصائصه. نقوم بتعيين الخط الموجود مسبقًا (`font`) واضبط حجم الخط على 14. اضبط حجم الخط حسب الحاجة.

## الخطوة 4: قم بقياس عرض النص

```csharp
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```

يوضح الكود أعلاه كيفية قياس عرض النص باستخدام كل من الخط مباشرة (`font.MeasureString`) وحالة النص (`ts.MeasureString`). يتضمن بعض عمليات التحقق من الصحة للتأكد من دقة القياسات.

### نموذج التعليمات البرمجية المصدر للحصول على عرض النص ديناميكيًا باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```


## خاتمة

لقد تعلمت كيفية استخدام Aspose.PDF لـ .NET لقياس عرض النص ديناميكيًا في C #. باتباع الخطوات الموضحة في هذا البرنامج التعليمي ، يمكنك تحديد عرض السلاسل النصية بدقة قبل عرضها في مستند PDF.