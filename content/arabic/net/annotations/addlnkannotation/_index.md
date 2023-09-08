---
title: إضافة تعليق توضيحي لـ LNK
linktitle: إضافة تعليق توضيحي لـ LNK
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة ميزة Ink Annotation إلى مستندات PDF في C# باستخدام Aspose.PDF لـ .NET مع دليل خطوة بخطوة وكود المصدر الكامل.
type: docs
weight: 20
url: /ar/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET هي مكتبة قوية تمكن المطورين من تنفيذ عمليات PDF المختلفة. إحدى هذه العمليات هي إضافة تعليق توضيحي بالحبر إلى مستندات PDF. في هذه المقالة، سنقدم دليلًا خطوة بخطوة لشرح الكود المصدري لـ C# لإضافة تعليق توضيحي بالحبر باستخدام Aspose.PDF لـ .NET. هيا بنا نبدأ!

## فهم ميزة التعليقات التوضيحية بالحبر في Aspose.PDF لـ .NET

قبل الغوص في الكود المصدري لـ C#، دعونا أولاً نفهم ما هو Ink Annotation واستخداماته.

التعليقات التوضيحية بالحبر هي طريقة لرسم تعليقات توضيحية بالحبر بشكل حر على مستندات PDF. يسمح لك بإنشاء تعليقات توضيحية باستخدام قلم أو ماوس. تعد هذه الميزة مفيدة في المواقف التي تحتاج فيها إلى رسم مخططات أو رسومات تخطيطية أو أنواع أخرى من التعليقات التوضيحية.

## الخطوة 1: إنشاء مستند جديد

الخطوة الأولى في إضافة تعليق توضيحي بالحبر إلى مستند PDF هي إنشاء مثيل جديد لفئة المستند. يتم تحقيق ذلك باستخدام مقتطف الكود التالي:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

هنا، نقوم بإنشاء مثيل جديد لفئة المستند وإضافة صفحة جديدة إليه.

## الخطوة 2: إنشاء تعليق توضيحي بالحبر

الخطوة التالية هي إنشاء مثيل لفئة InkAnnotation. ويتم ذلك باستخدام مقتطف التعليمات البرمجية التالي:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

هنا، نقوم أولاً بإنشاء مستطيل باستخدام فئة System.Drawing.Rectangle وتحويله إلى Aspose.Pdf.Rectangle باستخدام طريقة FromRect. نقوم بعد ذلك بإنشاء مثيل لفئة InkAnnotation باستخدام المستطيل وقائمة النقاط والصفحة التي تمت إضافة التعليق التوضيحي فيها.

نقوم بعد ذلك بتعيين خصائص مختلفة للتعليق التوضيحي بالحبر، مثل العنوان واللون ونمط الغطاء والحدود والعتامة. وأخيرًا، نضيف التعليق التوضيحي إلى الصفحة باستخدام طريقة Annotations.Add.

## الخطوة 3: حفظ المستند

الخطوة الأخيرة هي حفظ مستند PDF مع إضافة التعليق التوضيحي بالحبر. يتم تحقيق ذلك باستخدام مقتطف الكود التالي:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

هنا، نقوم بتسلسل اسم ملف الإخراج إلى دليل البيانات وحفظ المستند باستخدام طريقة الحفظ.

### مثال على التعليمات البرمجية المصدر لإضافة تعليق توضيحي بالحبر باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// حفظ ملف الإخراج
doc.Save(dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية إضافة التعليقات التوضيحية بالحبر إلى مستند PDF باستخدام Aspose.PDF لـ .NET. من خلال اتباع الدليل خطوة بخطوة والتعليمة البرمجية المصدر C# المتوفرة، يمكن للمطورين تنفيذ وظيفة Ink Annotation بسهولة في تطبيقات معالجة PDF الخاصة بهم.

### الأسئلة الشائعة

#### س: ما هو التعليق التوضيحي بالحبر في مستند PDF؟

ج: يتيح التعليق التوضيحي بالحبر الموجود في مستند PDF للمستخدمين رسم تعليقات توضيحية بالحبر باستخدام القلم أو الماوس. يتم استخدامه بشكل شائع لإضافة رسومات أو رسوم بيانية أو تعليقات توضيحية أخرى مرسومة يدويًا إلى ملف PDF.

#### س: هل يمكنني تخصيص مظهر التعليق التوضيحي بالحبر؟

ج: نعم، يوفر Aspose.PDF for .NET خصائص متنوعة لتخصيص مظهر التعليق التوضيحي بالحبر، مثل اللون، والعتامة، ونمط الغطاء، وعرض الحدود، والمزيد. يمكن للمطورين تعديل هذه الخصائص لتلبية متطلباتهم المحددة.

#### س: هل من الممكن إضافة تعليقات توضيحية متعددة بالحبر إلى صفحة PDF واحدة؟

ج: نعم، يمكنك إضافة تعليقات توضيحية متعددة بالحبر إلى صفحة PDF واحدة باستخدام Aspose.PDF لـ .NET. يمكن أن يكون لكل تعليق توضيحي بالحبر مجموعة نقاط خاصة به ومظهر مخصص.

#### س: هل يمكنني إضافة تعليقات توضيحية بالحبر إلى مستندات PDF الموجودة؟

ج: نعم، يسمح لك Aspose.PDF for .NET بإضافة تعليقات توضيحية بالحبر إلى كل من مستندات PDF المنشأة حديثًا وملفات PDF الموجودة. يمكنك فتح ملف PDF موجود وإضافة تعليقات توضيحية بالحبر وحفظ المستند المحدث.

#### س: ما هي بعض حالات الاستخدام الشائعة للتعليقات التوضيحية بالحبر في مستندات PDF؟

ج: تعد التعليقات التوضيحية بالحبر مفيدة لمجموعة واسعة من التطبيقات، بما في ذلك إضافة التوقيعات أو الملاحظات المكتوبة بخط اليد إلى نماذج PDF، والتعليق على المخططات المعمارية أو الرسومات الهندسية، وترميز المستندات للمراجعة التعاونية.