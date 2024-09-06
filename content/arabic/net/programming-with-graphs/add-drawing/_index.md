---
title: إضافة رسم في ملف PDF
linktitle: إضافة رسم في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة رسم في ملف PDF باستخدام Aspose.PDF لـ .NET. اتبع هذا الدليل خطوة بخطوة لإنشاء مستندات PDF جذابة مع ميزات الرسم.
type: docs
weight: 10
url: /ar/net/programming-with-graphs/add-drawing/
---
يتطلب تطوير التطبيقات غالبًا إضافة ميزات مثل الرسومات والرسومات لجعل المستندات أكثر جاذبية وإفادة. في هذه المقالة، سنرشدك خطوة بخطوة لشرح كود المصدر C# لإضافة الرسم إلى البرمجة بالرسومات باستخدام Aspose.PDF لـ .NET.

قبل البدء، تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك. وتأكد أيضًا من امتلاكك للمعرفة الأساسية ببرمجة C#.

## الخطوة 1: مقدمة حول Aspose.PDF لـ .NET وميزاته

Aspose.PDF هي مكتبة قوية ومتعددة الاستخدامات لإنشاء ملفات PDF ومعالجتها وتحويلها في تطبيقات .NET. وهي توفر مجموعة واسعة من الميزات للعمل مع مستندات PDF، بما في ذلك إضافة الرسومات والنصوص وما إلى ذلك.

## الخطوة 2: فهم الكود المصدر لإضافة الرسومات باستخدام Aspose.PDF

يستخدم الكود المصدر المقدم مكتبة Aspose.PDF لإنشاء رسم بسيط في مستند PDF. سنفحص الآن كل خطوة من خطوات الكود بالتفصيل.

## الخطوة 3: تكوين دليل المستندات وتهيئة المتغيرات

في الكود المصدر، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. يمكنك تعديل المتغير "dataDir" للإشارة إلى الدليل المطلوب.

بالإضافة إلى ذلك، يقوم الكود بتهيئة المتغيرات لمكونات الألوان ألفا والأحمر والأخضر والأزرق.

## الخطوة 4: إنشاء كائن ملون باستخدام Alpha RGB

يؤدي سطر التعليمات البرمجية التالي إلى إنشاء كائن لون باستخدام قيم ألفا، والأحمر، والأخضر، والأزرق المحددة:

```csharp
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue);
```

يسمح هذا بتحديد لون باستخدام قناة ألفا، مما يعني أن اللون يمكن أن يكون شفافًا جزئيًا.

## الخطوة 5: إنشاء كائن مستند

للبدء في العمل مع Aspose.PDF، نحتاج إلى إنشاء مثيل لفئة Document. يمثل هذا مستند PDF الخاص بنا.

```csharp
Document document = new Document();
```

## الخطوة 6: إضافة صفحة إلى ملف PDF

نحن بحاجة إلى إضافة صفحة إلى ملف PDF حيث نريد عرض رسمنا.

```csharp
Page page = document.Pages.Add();
```

## الخطوة 7: إنشاء كائن رسم بياني بأبعاد

في هذه الخطوة، نقوم بإنشاء كائن رسم بياني بأبعاد محددة. سيعمل هذا الكائن كحاوية لرسمنا.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
```

## الخطوة 8: تعيين الحدود لكائن الرسم

يمكننا تعيين حدود كائن الرسم باستخدام فئة BorderInfo.

```csharp
graph.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black);
```

سيؤدي هذا إلى إنشاء حدود سوداء حول رسمنا.

## الخطوة 9: إضافة كائن الرسم البياني إلى الصفحة

نضيف الآن كائن الرسم البياني إلى مجموعة الفقرات الخاصة بمثيل فئة الصفحة.

```csharp
page.Paragraphs.Add(graph);
```

## الخطوة 10: إنشاء كائن مستطيل بأبعاد

نقوم بإنشاء كائن مستطيل بأبعاد محددة، وسيتم إضافة هذا المستطيل إلى الرسم الخاص بنا.

```csharp
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
```

## الخطوة 11: إنشاء كائن GraphInfo لنسخة المستطيل

نحن بحاجة إلى إنشاء كائن GraphInfo لنموذج المستطيل لتكوين خصائص الرسم البياني الخاص به.

```csharp
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
```

## الخطوة 12: تكوين معلومات اللون لكائن GraphInfo

يمكننا تكوين معلومات اللون لكائن GraphInfo باستخدام خصائص Color وFillColor.

```csharp
graphInfo.Color = Aspose.Pdf.Color.Red;
graphInfo. FillColor = alphaColor;
```

سيؤدي هذا إلى تعيين لون حدود المستطيل إلى اللون الأحمر ولون التعبئة إلى لون ألفا المحدد.

## الخطوة 13: إضافة شكل المستطيل إلى كائن الرسم البياني

الآن نضيف شكل المستطيل إلى مجموعة الأشكال الخاصة بكائن الرسم البياني.

```csharp
graph.Shapes.Add(rectangle);
```
## الخطوة 14: احفظ ملف PDF واعرض رسالة النجاح

وأخيرا نقوم بحفظ ملف PDF ونعرض رسالة تفيد بأن الرسم تم إضافته بنجاح.

```csharp
dataDir = dataDir + "AddDrawing_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nSuccessfully added drawing with transparent color.\nFile saved to location: " + dataDir);
```

### عينة من كود المصدر لإضافة رسم باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
// إنشاء كائن ملون باستخدام Alpha RGB
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue); // توفير قناة ألفا
// إنشاء كائن مستند
Document document = new Document();
// إضافة صفحة إلى مجموعة صفحات ملف PDF
Page page = document.Pages.Add();
//إنشاء كائن رسم بياني بأبعاد معينة
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
// تعيين حدود لكائن الرسم
graph.Border = (new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black));
// إضافة كائن الرسم البياني إلى مجموعة الفقرات الخاصة بنسخة الصفحة
page.Paragraphs.Add(graph);
// إنشاء كائن مستطيل بأبعاد معينة
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
// إنشاء كائن graphInfo لنموذج المستطيل
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
// تعيين معلومات اللون لنسخة GraphInfo
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

في هذه المقالة، تعلمنا كيفية إضافة رسم إلى البرمجة باستخدام الرسومات باستخدام Aspose.PDF لـ .NET. لقد اتبعنا دليلًا خطوة بخطوة لفهم الكود المصدر والخطوات المختلفة المتضمنة في إضافة رسم إلى ملف PDF. باستخدام الميزات القوية لـ Aspose.PDF، يمكنك إنشاء مستندات PDF جذابة وتفاعلية في تطبيقات .NET الخاصة بك.


### الأسئلة الشائعة حول إضافة رسم في ملف PDF

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تتيح إنشاء ملفات PDF ومعالجتها وتحويلها داخل تطبيقات .NET.

#### س: هل يمكنني تعديل شفافية الألوان في رسوماتي؟

ج: نعم، باستخدام قناة ألفا في كائن اللون، يمكنك إنشاء ألوان شفافة جزئيًا لرسوماتك.

#### س: كيف أضيف حدودًا إلى رسم في مستند PDF؟

ج: يمكنك تعيين حدود كائن الرسم باستخدام فئة BorderInfo، مما يسمح لك بتحديد خصائص الحدود مثل اللون والأسلوب.

#### س: هل Aspose.PDF مناسب للمبتدئين في برمجة C#؟

ج: يوفر Aspose.PDF مجموعة واسعة من الميزات، بما في ذلك الرسم، وقد يتطلب فهمًا أساسيًا لبرمجة C# للاستفادة الكاملة من قدراته.