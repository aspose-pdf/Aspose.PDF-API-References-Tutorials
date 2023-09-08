---
title: احصل على عرض النص ديناميكيًا
linktitle: احصل على عرض النص ديناميكيًا
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية الحصول على عرض النص ديناميكيًا باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 220
url: /ar/net/programming-with-text/get-width-of-text-dynamically/
---
سنشرح في هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لقياس عرض النص ديناميكيًا في لغة C#. يمكن أن يكون هذا مفيدًا عندما تحتاج إلى تحديد حجم سلسلة نصية قبل عرضها على مستند PDF. سنرشدك عبر كود مصدر C# المقدم خطوة بخطوة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- Visual Studio أو أي بيئة تطوير أخرى لـ C#.

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

 يعثر الكود أعلاه على الخط Arial باستخدام ملف`FindFont` الطريقة من`FontRepository` فصل. إذا كنت تريد استخدام خط مختلف، فاستبدله`"Arial"` مع اسم الخط المطلوب

## الخطوة 3: ضبط حالة النص

```csharp
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
```

 هنا نقوم بإنشاء جديد`TextState` الكائن وتعيين خصائصه. نقوم بتعيين الخط الموجود مسبقًا (`font`) واضبط حجم الخط على 14. اضبط حجم الخط حسب الحاجة.

## الخطوة 4: قياس عرض النص

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

يوضح الكود أعلاه كيفية قياس عرض النص باستخدام الخط مباشرة (`font.MeasureString`) وحالة النص (`ts.MeasureString`). يتضمن بعض عمليات التحقق من الصحة للتأكد من دقة القياسات.

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

لقد تعلمت كيفية استخدام Aspose.PDF لـ .NET لقياس عرض النص ديناميكيًا في لغة C#. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تحديد عرض السلاسل النصية بدقة قبل عرضها في مستند PDF.

## الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "الحصول على عرض النص ديناميكيًا"؟

ج: يشرح البرنامج التعليمي "الحصول على عرض النص ديناميكيًا" كيفية استخدام Aspose.PDF لـ .NET لقياس عرض النص ديناميكيًا في C#. يعد هذا مفيدًا بشكل خاص عندما تحتاج إلى تحديد حجم سلسلة نصية قبل عرضها على مستند PDF.

#### س: لماذا أحتاج إلى قياس عرض النص ديناميكيًا؟

ج: يتيح لك قياس عرض النص ديناميكيًا تحديد المساحة المطلوبة للنص بدقة قبل عرضه. يعد هذا أمرًا بالغ الأهمية لتصميم التخطيط والمحاذاة والتأكد من احتواء النص بشكل صحيح داخل المناطق المحددة في مستند PDF الخاص بك.

#### س: كيف يمكنني العثور على الخط الذي سيتم استخدامه لقياس النص؟

ج: في البرنامج التعليمي، يمكنك استخدام`FontRepository.FindFont` طريقة تحديد الخط المطلوب يستخدم المثال الخط Arial، ولكن يمكنك استبداله`"Arial"` مع اسم أي خط آخر تريد استخدامه.

####  س: ما هو الغرض من`TextState` class?

 ج: ال`TextState` يتم استخدام الفئة لتعيين خصائص تنسيق النص مثل الخط وحجم الخط. يسمح لك بتحديد كيفية تقديم النص.

#### س: كيف يمكنني قياس عرض النص باستخدام حالة الخط والنص؟

ج: يوضح البرنامج التعليمي كيفية قياس عرض النص باستخدام كلا الخطين مباشرة (`font.MeasureString`) وحالة النص (`ts.MeasureString`). ويتضمن فحوصات التحقق لضمان دقة القياس.

#### س: هل يمكنني استخدام هذه التقنية لأحجام وأنماط الخطوط المختلفة؟

 ج: نعم، يمكنك تعديل حجم الخط والخصائص الأخرى في الملف`TextState` كائن لقياس عرض النص لأحجام وأنماط مختلفة.

#### س: ما الذي تؤكده خاتمة البرنامج التعليمي؟

ج: يلخص الاستنتاج محتوى البرنامج التعليمي ويسلط الضوء على أنك تعلمت كيفية قياس عرض النص ديناميكيًا في مستند PDF باستخدام Aspose.PDF لـ .NET وC#. يمكن أن تساهم هذه المعرفة في تحسين تصميم تخطيط PDF الخاص بك ودقة العرض.