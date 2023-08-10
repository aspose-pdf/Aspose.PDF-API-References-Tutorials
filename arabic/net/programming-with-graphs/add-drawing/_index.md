---
title: أضف الرسم في ملف PDF
linktitle: أضف الرسم في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة الرسم في ملف PDF باستخدام Aspose.PDF for .NET. اتبع هذا الدليل التفصيلي خطوة بخطوة لإنشاء مستندات PDF جذابة مع ميزات الرسم.
type: docs
weight: 10
url: /ar/net/programming-with-graphs/add-drawing/
---
غالبًا ما يتطلب تطوير التطبيقات إضافة ميزات مثل الرسومات والرسومات لجعل المستندات أكثر جاذبية وإفادة. في هذه المقالة ، سنوجهك خطوة بخطوة لشرح الكود المصدري C # لإضافة الرسم إلى البرمجة باستخدام الرسومات باستخدام Aspose.PDF for .NET.

قبل أن تبدأ ، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. تأكد أيضًا من أن لديك معرفة أساسية ببرمجة C #.

## الخطوة 1: مقدمة إلى Aspose.PDF لـ .NET ومميزاتها

Aspose.PDF هي مكتبة قوية ومتعددة الاستخدامات لإنشاء ملفات PDF ومعالجتها وتحويلها في تطبيقات .NET. يوفر مجموعة واسعة من الميزات للعمل مع مستندات PDF ، بما في ذلك إضافة الرسومات والرسومات والنصوص وما إلى ذلك.

## الخطوة 2: فهم الكود المصدري لإضافة رسومات باستخدام Aspose.PDF

يستخدم كود المصدر المقدم مكتبة Aspose.PDF لإنشاء رسم بسيط في وثيقة PDF. سنقوم الآن بفحص كل خطوة من خطوات الكود بالتفصيل.

## الخطوة 3: تكوين دليل المستندات وتهيئة المتغيرات

في التعليمات البرمجية المصدر ، تحتاج إلى تحديد الدليل حيث تريد حفظ ملف PDF الناتج. يمكنك تعديل متغير "dataDir" للإشارة إلى الدليل المطلوب.

بالإضافة إلى ذلك ، يقوم الكود بتهيئة المتغيرات لمكونات اللون ألفا والأحمر والأخضر والأزرق.

## الخطوة 4: إنشاء كائن ملون باستخدام Alpha RGB

ينشئ السطر التالي من التعليمات البرمجية كائن اللون باستخدام قيم ألفا والأحمر والأخضر والأزرق المحددة:

```csharp
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue);
```

يسمح هذا بتحديد لون بقناة ألفا ، مما يعني أن اللون يمكن أن يكون شفافًا جزئيًا.

## الخطوة 5: إنشاء كائن مستند

لبدء العمل مع Aspose.PDF ، نحتاج إلى إنشاء مثيل لفئة Document. هذا يمثل وثيقة PDF الخاصة بنا.

```csharp
Document document = new Document();
```

## الخطوة السادسة: إضافة صفحة إلى ملف PDF

نحتاج إلى إضافة صفحة إلى ملف PDF حيث نريد عرض الرسم الخاص بنا.

```csharp
Page page = document.Pages.Add();
```

## الخطوة 7: إنشاء كائن رسم بأبعاد

في هذه الخطوة ، نقوم بإنشاء كائن رسم بأبعاد محددة. سيكون هذا الكائن بمثابة حاوية لرسمنا.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
```

## الخطوة 8: تعيين الحدود لكائن الرسم

يمكننا تعيين حدود كائن الرسم باستخدام فئة BorderInfo.

```csharp
graph.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black);
```

سيؤدي هذا إلى وضع حد أسود حول الرسم.

## الخطوة 9: إضافة كائن الرسم البياني إلى الصفحة

نضيف الآن كائن الرسم البياني إلى مجموعة الفقرات لمثيل فئة الصفحة.

```csharp
page.Paragraphs.Add(graph);
```

## الخطوة 10: إنشاء كائن مستطيل بأبعاد

نقوم بإنشاء كائن مستطيل بأبعاد محددة. سيتم إضافة هذا المستطيل إلى الرسم الخاص بنا.

```csharp
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
```

## الخطوة 11: إنشاء كائن GraphInfo لمثيل المستطيل

نحتاج إلى إنشاء كائن GraphInfo لمثيل المستطيل لتكوين خصائص الرسم البياني الخاصة به.

```csharp
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
```

## الخطوة 12: تكوين معلومات اللون لكائن GraphInfo

يمكننا تكوين معلومات اللون لكائن GraphInfo باستخدام خصائص Color و FillColor.

```csharp
graphInfo.Color = Aspose.Pdf.Color.Red;
graphInfo. FillColor = alphaColor;
```

سيؤدي هذا إلى تعيين لون حدود المستطيل إلى اللون الأحمر ولون التعبئة إلى لون ألفا المحدد.

## الخطوة 13: إضافة شكل المستطيل إلى كائن الرسم البياني

نضيف الآن شكل المستطيل إلى مجموعة أشكال كائن الرسم البياني.

```csharp
graph.Shapes.Add(rectangle);
```
## الخطوة 14: احفظ ملف PDF واعرض رسالة النجاح

أخيرًا ، نحفظ ملف PDF ونعرض رسالة تفيد بإضافة الرسم بنجاح.

```csharp
dataDir = dataDir + "AddDrawing_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nSuccessfully added drawing with transparent color.\nFile saved to location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Add Drawing باستخدام Aspose.PDF for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
// قم بإنشاء كائن ملون باستخدام Alpha RGB
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue); // توفير قناة ألفا
// إنشاء كائن المستند
Document document = new Document();
// أضف صفحة إلى مجموعة صفحات من ملف PDF
Page page = document.Pages.Add();
//إنشاء كائن رسم بأبعاد معينة
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
// تعيين حد لكائن الرسم
graph.Border = (new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black));
// أضف كائن الرسم البياني إلى مجموعة فقرات مثيل الصفحة
page.Paragraphs.Add(graph);
// إنشاء كائن مستطيل بأبعاد معينة
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
// إنشاء كائن GraphInfo لمثيل المستطيل
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
// قم بتعيين معلومات اللون لمثيل GraphInfo
graphInfo.Color = (Aspose.Pdf.Color.Red);
// قم بتعيين لون التعبئة لـ GraphInfo
graphInfo.FillColor = (alphaColor);
// أضف شكل مستطيل إلى مجموعة أشكال لكائن الرسم البياني
graph.Shapes.Add(rectangle);
dataDir = dataDir + "AddDrawing_out.pdf";
// احفظ ملف PDF
document.Save(dataDir);
Console.WriteLine("\nDrawing added successfully with transparent color.\nFile saved at " + dataDir);            

```

## خاتمة

في هذه المقالة ، تعلمنا كيفية إضافة الرسم إلى البرمجة باستخدام الرسومات باستخدام Aspose.PDF for .NET. لقد اتبعنا دليلًا تفصيليًا لفهم الكود المصدري والخطوات المختلفة المتضمنة في إضافة رسم إلى ملف PDF. باستخدام الميزات القوية لـ Aspose.PDF ، يمكنك إنشاء مستندات PDF جذابة وتفاعلية في تطبيقات .NET الخاصة بك.


### الأسئلة الشائعة لإضافة الرسم في ملف PDF

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET مكتبة قوية تتيح إنشاء ومعالجة وتحويل ملفات PDF ضمن تطبيقات .NET.

#### س: هل يمكنني ضبط شفافية الألوان في رسوماتي؟

ج: نعم ، باستخدام قناة ألفا في كائن اللون ، يمكنك إنشاء ألوان شفافة جزئيًا لرسوماتك.

#### س: كيف أقوم بإضافة حد إلى رسم في مستند PDF؟

ج: يمكنك تعيين حد كائن رسم باستخدام فئة BorderInfo ، مما يتيح لك تحديد خصائص الحدود مثل اللون والنمط.

#### س: هل Aspose.PDF مناسب للمبتدئين في برمجة C #؟

ج: يقدم Aspose.PDF مجموعة واسعة من الميزات ، بما في ذلك الرسم ، وقد يتطلب فهمًا أساسيًا لبرمجة C # للاستفادة الكاملة من إمكاناتها.