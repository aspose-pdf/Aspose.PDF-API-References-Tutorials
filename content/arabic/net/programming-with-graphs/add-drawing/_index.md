---
title: إضافة الرسم في ملف PDF
linktitle: إضافة الرسم في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة رسم في ملف PDF باستخدام Aspose.PDF لـ .NET. اتبع هذا الدليل التفصيلي خطوة بخطوة لإنشاء مستندات PDF جذابة مع ميزات الرسم.
type: docs
weight: 10
url: /ar/net/programming-with-graphs/add-drawing/
---
غالبًا ما يتطلب تطوير التطبيقات إضافة ميزات مثل الرسومات والرسومات لجعل المستندات أكثر جاذبية وغنية بالمعلومات. في هذه المقالة، سنرشدك خطوة بخطوة لشرح الكود المصدري لـ C# لإضافة الرسم إلى البرمجة باستخدام الرسومات باستخدام Aspose.PDF for .NET.

قبل البدء، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. تأكد أيضًا من أن لديك المعرفة الأساسية ببرمجة C#.

## الخطوة 1: مقدمة إلى Aspose.PDF لـ .NET وميزاته

Aspose.PDF هي مكتبة قوية ومتعددة الاستخدامات لإنشاء ملفات PDF ومعالجتها وتحويلها في تطبيقات .NET. فهو يوفر مجموعة واسعة من الميزات للعمل مع مستندات PDF، بما في ذلك إضافة الرسومات والرسومات والنصوص وما إلى ذلك.

## الخطوة 2: فهم الكود المصدري لإضافة رسومات باستخدام Aspose.PDF

يستخدم الكود المصدري المقدم مكتبة Aspose.PDF لإنشاء رسم بسيط في مستند PDF. سنقوم الآن بدراسة كل خطوة من خطوات الكود بالتفصيل.

## الخطوة 3: تكوين دليل المستندات وتهيئة المتغيرات

في الكود المصدري، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. يمكنك تعديل المتغير "dataDir" للإشارة إلى الدليل المطلوب.

بالإضافة إلى ذلك، يقوم الكود بتهيئة المتغيرات لمكونات الألوان ألفا، والأحمر، والأخضر، والأزرق.

## الخطوة 4: إنشاء كائن ملون باستخدام Alpha RGB

يقوم السطر التالي من التعليمات البرمجية بإنشاء كائن اللون باستخدام قيم ألفا والأحمر والأخضر والأزرق المحددة:

```csharp
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue);
```

يسمح هذا بتحديد لون بقناة ألفا، مما يعني أن اللون يمكن أن يكون شفافًا جزئيًا.

## الخطوة 5: إنشاء مثيل لكائن المستند

لبدء العمل مع Aspose.PDF، نحتاج إلى إنشاء مثيل لفئة Document. وهذا يمثل مستند PDF الخاص بنا.

```csharp
Document document = new Document();
```

## الخطوة 6: إضافة صفحة إلى ملف PDF

نحتاج إلى إضافة صفحة إلى ملف PDF حيث نريد عرض الرسم الخاص بنا.

```csharp
Page page = document.Pages.Add();
```

## الخطوة 7: إنشاء كائن رسم بياني بأبعاد

في هذه الخطوة، نقوم بإنشاء كائن رسم بياني بأبعاد محددة. سيكون هذا الكائن بمثابة حاوية لرسمنا.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
```

## الخطوة 8: تعيين الحدود للكائن الرسومي

يمكننا ضبط حدود الكائن الرسومي باستخدام فئة BorderInfo.

```csharp
graph.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black);
```

سيؤدي هذا إلى تعيين حد أسود حول رسمنا.

## الخطوة 9: إضافة كائن الرسم البياني إلى الصفحة

نقوم الآن بإضافة كائن الرسم البياني إلى مجموعة الفقرات الخاصة بمثيل فئة الصفحة.

```csharp
page.Paragraphs.Add(graph);
```

## الخطوة 10: إنشاء كائن مستطيل بأبعاد

نقوم بإنشاء كائن مستطيل بأبعاد محددة. سيتم إضافة هذا المستطيل إلى الرسم لدينا.

```csharp
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
```

## الخطوة 11: إنشاء كائن GraphInfo لمثيل المستطيل

نحتاج إلى إنشاء كائن GraphInfo لمثيل Rectangle لتكوين خصائص الرسم البياني الخاص به.

```csharp
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
```

## الخطوة 12: تكوين معلومات اللون لكائن GraphInfo

يمكننا تكوين معلومات اللون لكائن GraphInfo باستخدام خصائص اللون وFillColor.

```csharp
graphInfo.Color = Aspose.Pdf.Color.Red;
graphInfo. FillColor = alphaColor;
```

سيؤدي هذا إلى تعيين لون حدود المستطيل إلى اللون الأحمر ولون التعبئة إلى لون ألفا المحدد.

## الخطوة 13: إضافة الشكل المستطيل إلى كائن الرسم البياني

نضيف الآن الشكل المستطيل إلى مجموعة أشكال كائن الرسم البياني.

```csharp
graph.Shapes.Add(rectangle);
```
## الخطوة 14: احفظ ملف PDF واعرض رسالة النجاح

أخيرًا، نقوم بحفظ ملف PDF ونعرض رسالة تفيد بأنه تمت إضافة الرسم بنجاح.

```csharp
dataDir = dataDir + "AddDrawing_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nSuccessfully added drawing with transparent color.\nFile saved to location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لإضافة رسم باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
// قم بإنشاء كائن اللون باستخدام Alpha RGB
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue); // توفير قناة ألفا
// إنشاء مثيل لكائن المستند
Document document = new Document();
// إضافة صفحة إلى مجموعة الصفحات من ملف PDF
Page page = document.Pages.Add();
//إنشاء كائن رسم بياني بأبعاد معينة
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
// تعيين الحدود لكائن الرسم
graph.Border = (new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black));
// إضافة كائن الرسم البياني إلى مجموعة الفقرات من مثيل الصفحة
page.Paragraphs.Add(graph);
// إنشاء كائن مستطيل بأبعاد معينة
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
// قم بإنشاء كائن graphInfo لمثيل المستطيل
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
// قم بتعيين معلومات اللون لمثيل GraphInfo
graphInfo.Color = (Aspose.Pdf.Color.Red);
// تعيين لون التعبئة لـ GraphInfo
graphInfo.FillColor = (alphaColor);
// إضافة شكل مستطيل إلى مجموعة أشكال كائن الرسم البياني
graph.Shapes.Add(rectangle);
dataDir = dataDir + "AddDrawing_out.pdf";
// حفظ ملف PDF
document.Save(dataDir);
Console.WriteLine("\nDrawing added successfully with transparent color.\nFile saved at " + dataDir);            

```

## خاتمة

تعلمنا في هذه المقالة كيفية إضافة الرسم إلى البرمجة باستخدام الرسومات باستخدام Aspose.PDF لـ .NET. لقد اتبعنا دليلاً خطوة بخطوة لفهم الكود المصدري والخطوات المختلفة المتضمنة في إضافة رسم إلى ملف PDF. باستخدام الميزات القوية لـ Aspose.PDF، يمكنك إنشاء مستندات PDF جذابة وتفاعلية في تطبيقات .NET الخاصة بك.


### الأسئلة الشائعة لإضافة رسم في ملف PDF

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تتيح إنشاء ملفات PDF ومعالجتها وتحويلها داخل تطبيقات .NET.

#### س: هل يمكنني ضبط شفافية الألوان في رسوماتي؟

ج: نعم، باستخدام قناة ألفا في كائن اللون، يمكنك إنشاء ألوان شفافة جزئيًا لرسوماتك.

#### س: كيف يمكنني إضافة حد إلى رسم في مستند PDF؟

ج: يمكنك تعيين حدود كائن رسومي باستخدام فئة BorderInfo، مما يتيح لك تحديد خصائص الحدود مثل اللون والنمط.

#### س: هل Aspose.PDF مناسب للمبتدئين في برمجة C#؟

ج: يوفر Aspose.PDF نطاقًا واسعًا من الميزات، بما في ذلك الرسم، وقد يتطلب فهمًا أساسيًا لبرمجة C# للاستفادة الكاملة من إمكانياته.