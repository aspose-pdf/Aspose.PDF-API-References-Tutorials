---
title: إنشاء ملف PDF متعدد الأعمدة
linktitle: إنشاء ملف PDF متعدد الأعمدة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إنشاء ملف PDF متعدد الأعمدة باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/programming-with-text/create-multi-column-pdf/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء ملف PDF متعدد الأعمدة باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إنشاء ملف PDF متعدد الأعمدة فيه، أضف ما يلي باستخدام التوجيهات في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: إنشاء مثيل مستند جديد
 إنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Document doc = new Document();
```

## الخطوة 5: ضبط هوامش الصفحة
 حدد معلومات الهامش الأيسر والأيمن لملف PDF باستخدام`PageInfo.Margin` ممتلكات`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## الخطوة 6: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`المجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 7: إنشاء كائن رسم بياني وإضافة خط
 إنشاء جديد`Graph` كائن ذو أبعاد محددة وأضف إليه خطًا. ثم أضف`Graph` الاعتراض على`Paragraphs` مجموعة من الصفحات.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## الخطوة 8: إضافة نص العنوان بتنسيق HTML
 إنشاء`HtmlFragment` الكائن وضبط محتواه على النص HTML المطلوب. ثم أضف الجزء إلى`Paragraphs` مجموعة من الصفحات.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## الخطوة 9: إنشاء صندوق عائم يحتوي على أعمدة متعددة
 إنشاء`FloatingBox` الكائن وحدد عدد الأعمدة والتباعد بين الأعمدة. ثم أضف أجزاء نصية وسطرًا إلى`Paragraphs` مجموعة من`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## الخطوة 10: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir);
```

### عينة من كود المصدر لإنشاء ملف Pdf متعدد الأعمدة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//تحديد معلومات الهامش الأيسر لملف PDF
doc.PageInfo.Margin.Left = 40;
// حدد معلومات الهامش الأيمن لملف PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// أضف السطر إلى مجموعة الفقرات الخاصة بكائن القسم
page.Paragraphs.Add(graph1);
// حدد إحداثيات الخط
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// إنشاء متغيرات سلسلة تحتوي على نص يحتوي على علامات HTML
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// إنشاء فقرات نصية تحتوي على نص HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// أضف أربعة أعمدة في القسم
box.ColumnInfo.ColumnCount = 2;
// ضبط المسافة بين الأعمدة
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// إنشاء كائن رسوم بيانية لرسم خط
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// حدد إحداثيات الخط
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// إضافة السطر إلى مجموعة فقرات كائن القسم
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في إنشاء ملف PDF متعدد الأعمدة باستخدام Aspose.PDF لـ .NET. يمكنك الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز في هذا البرنامج التعليمي؟

يركز هذا البرنامج التعليمي على إرشادك خلال عملية إنشاء ملف PDF متعدد الأعمدة باستخدام مكتبة Aspose.PDF for .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي المساحات الأسماء التي ينبغي لي استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تريد إنشاء ملف PDF متعدد الأعمدة فيه، قم باستيراد المساحات التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### س: كيف أحدد دليل المستند؟

 أ: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف أقوم بإنشاء مثيل مستند جديد؟

 أ: في الخطوة 4، ستقوم بإنشاء مثيل جديد`Document` الكائن باستخدام الكود المقدم.

#### س: كيف أقوم بتعيين هوامش الصفحة؟

 أ: في الخطوة 5، سوف تستخدم`PageInfo.Margin` ممتلكات`Document` لتحديد معلومات الهامش الأيسر والأيمن لملف PDF.

#### س: كيف أضيف صفحة إلى المستند؟

 أ: في الخطوة 6، ستضيف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` مجموعة.

#### س: كيف أقوم بإنشاء كائن رسم بياني وإضافة خط؟

 أ: في الخطوة 7، ستقوم بإنشاء ملف جديد`Graph` الكائن، أضف إليه خطًا، ثم أضف`Graph` الاعتراض على`Paragraphs` مجموعة من الصفحات.

#### س: كيف أضيف نص العنوان بتنسيق HTML؟

 أ: في الخطوة 8، ستقوم بإنشاء`HtmlFragment` الكائن وتعيين محتواه إلى النص HTML المطلوب، ثم إضافة الجزء إلى`Paragraphs` مجموعة من الصفحات.

#### س: كيف أقوم بإنشاء FloatingBox يحتوي على أعمدة متعددة؟

 أ: في الخطوة 9، ستقوم بإنشاء`FloatingBox` كائن يحتوي على أعمدة متعددة ومسافات بين الأعمدة، ثم أضف أجزاء نصية وسطرًا إلى`Paragraphs` مجموعة من`FloatingBox`.

#### س: كيف أحفظ مستند PDF؟

 أ: في الخطوة 10، ستحفظ مستند PDF باستخدام`Save` طريقة`Document` هدف.

#### س: ما هو الدرس الرئيسي المستفاد من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم كيفية إنشاء مستند PDF متعدد الأعمدة باستخدام Aspose.PDF لـ .NET. يمكن أن يكون هذا مفيدًا لعرض المحتوى في تخطيط منظم ومنظم.