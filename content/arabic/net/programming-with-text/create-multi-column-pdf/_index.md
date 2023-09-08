---
title: إنشاء ملف PDF متعدد الأعمدة
linktitle: إنشاء ملف PDF متعدد الأعمدة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء ملف PDF متعدد الأعمدة باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/programming-with-text/create-multi-column-pdf/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء ملف PDF متعدد الأعمدة باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد إنشاء ملف PDF متعدد الأعمدة فيه، أضف ما يلي باستخدام التوجيهات الموجودة في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء مثيل مستند جديد
 إنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: ضبط هوامش الصفحة
 حدد معلومات الهامش الأيسر والأيمن لملف PDF باستخدام`PageInfo.Margin` ملكية`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## الخطوة 6: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`مجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 7: إنشاء كائن رسم بياني وإضافة خط
 إنشاء جديد`Graph` كائن بأبعاد محددة وإضافة خط إليه. ثم قم بإضافة`Graph` يعترض على`Paragraphs` مجموعة من الصفحة.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## الخطوة 8: إضافة نص العنوان بتنسيق HTML
 يخترع`HtmlFragment` الكائن وقم بتعيين محتواه على نص HTML المطلوب. ثم أضف القطعة إلى`Paragraphs` مجموعة من الصفحة.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## الخطوة 9: إنشاء FloatingBox مع أعمدة متعددة
 إنشاء`FloatingBox` الكائن وتعيين عدد الأعمدة وتباعد الأعمدة. ثم قم بإضافة أجزاء النص وسطر إلى`Paragraphs` جمع من`FloatingBox`.

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

### نموذج التعليمات البرمجية المصدر لإنشاء ملف Pdf متعدد الأعمدة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// حدد معلومات الهامش الأيسر لملف PDF
doc.PageInfo.Margin.Left = 40;
//حدد معلومات الهامش الأيمن لملف PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// أضف السطر إلى مجموعة الفقرات من كائن القسم
page.Paragraphs.Add(graph1);
// حدد إحداثيات الخط
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// قم بإنشاء متغيرات سلسلة تحتوي على نص يحتوي على علامات html
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
// قم بإنشاء كائن رسوم بيانية لرسم خط
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// حدد إحداثيات الخط
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// إضافة السطر إلى مجموعة الفقرات من كائن القسم
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
لقد نجحت في إنشاء ملف PDF متعدد الأعمدة باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو محور هذا البرنامج التعليمي؟

يركز هذا البرنامج التعليمي على إرشادك خلال عملية إنشاء ملف PDF متعدد الأعمدة باستخدام مكتبة Aspose.PDF for .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي مساحات الأسماء التي يجب علي استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية الذي تريد إنشاء ملف PDF متعدد الأعمدة فيه، قم باستيراد مساحات الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني إنشاء مثيل مستند جديد؟

 ج: في الخطوة 4، ستقوم بإنشاء نسخة جديدة`Document` الكائن باستخدام الكود المقدم.

#### س: كيف أقوم بتعيين هوامش الصفحة؟

 ج: في الخطوة 5، ستستخدم`PageInfo.Margin` ملكية`Document` لتحديد معلومات الهامش الأيمن والأيسر لملف PDF.

#### س: كيف يمكنني إضافة صفحة إلى المستند؟

 ج: في الخطوة 6، ستضيف صفحة جديدة إلى المستند باستخدام الملف`Add` طريقة`Pages` مجموعة.

#### س: كيف يمكنني إنشاء كائن رسم بياني وإضافة خط؟

 ج: في الخطوة 7، ستقوم بإنشاء ملف جديد`Graph` الكائن، وأضف سطرًا إليه، ثم أضف`Graph` يعترض على`Paragraphs` مجموعة من الصفحة.

#### س: كيف يمكنني إضافة نص عنوان بتنسيق HTML؟

 ج: في الخطوة 8، ستقوم بإنشاء`HtmlFragment` الكائن وقم بتعيين محتواه على نص HTML المطلوب، ثم قم بإضافة الجزء إلى ملف`Paragraphs` مجموعة من الصفحة.

#### س: كيف أقوم بإنشاء FloatingBox مع أعمدة متعددة؟

 ج: في الخطوة 9، ستقوم بإنشاء ملف`FloatingBox` كائن يحتوي على أعمدة متعددة وتباعد الأعمدة، ثم قم بإضافة أجزاء نص وسطر إلى`Paragraphs` جمع من`FloatingBox`.

#### س: كيف أحفظ وثيقة PDF؟

 ج: في الخطوة 10، ستحفظ مستند PDF باستخدام ملف`Save` طريقة`Document` هدف.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تعلمت كيفية إنشاء مستند PDF متعدد الأعمدة باستخدام Aspose.PDF لـ .NET. يمكن أن يكون هذا مفيدًا لعرض المحتوى في تخطيط منظم ومنظم.