---
title: أضف التعليق التوضيحي lnk
linktitle: أضف التعليق التوضيحي lnk
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة ميزة التعليقات التوضيحية بالحبر إلى مستندات PDF في C # باستخدام Aspose.PDF for .NET مع دليل خطوة بخطوة وكود المصدر الكامل.
type: docs
weight: 20
url: /ar/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET مكتبة قوية تمكن المطورين من إجراء عمليات PDF متنوعة. تتمثل إحدى هذه العمليات في إضافة التعليقات التوضيحية بالحبر إلى مستندات PDF. في هذه المقالة ، سنقدم دليلاً خطوة بخطوة لشرح كود المصدر C # لإضافة تعليق توضيحي بالحبر باستخدام Aspose.PDF for .NET. هيا بنا نبدأ!

## فهم ميزة التعليقات التوضيحية بالحبر لـ Aspose.PDF لـ .NET

قبل الغوص في الكود المصدري C # ، دعنا أولاً نفهم ماهية التعليق التوضيحي بالحبر واستخداماته.

التعليقات التوضيحية بالحبر هي طريقة لرسم تعليقات توضيحية بالحبر على مستندات PDF. يسمح لك بإنشاء تعليقات توضيحية باستخدام قلم أو ماوس. هذه الميزة مفيدة في المواقف التي تحتاج فيها إلى رسم مخططات أو رسومات أو أنواع أخرى من التعليقات التوضيحية.

## الخطوة الأولى: إنشاء مستند جديد

تتمثل الخطوة الأولى في إضافة التعليقات التوضيحية بالحبر إلى مستند PDF في إنشاء مثيل جديد لفئة المستند. يتم تحقيق ذلك باستخدام مقتطف الشفرة التالي:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

هنا ، نقوم بإنشاء مثيل جديد لفئة المستند وإضافة صفحة جديدة إليه.

## الخطوة 2: إنشاء تعليق توضيحي بالحبر

الخطوة التالية هي إنشاء مثيل لفئة InkAnnotation. يتم ذلك باستخدام مقتطف الشفرة التالي:

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
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString (stroke.InkColor)) ؛
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

هنا ، نقوم أولاً بإنشاء مستطيل باستخدام فئة System.Drawing.Rectangle وتحويله إلى Aspose.Pdf.Rectangle باستخدام طريقة FromRect. نقوم بعد ذلك بإنشاء مثيل لفئة InkAnnotation باستخدام المستطيل وقائمة النقاط والصفحة التي تمت إضافة التعليق التوضيحي فيها.

ثم قمنا بتعيين خصائص مختلفة للتعليقات التوضيحية بالحبر ، مثل العنوان واللون ونمط الغطاء والحدود والتعتيم. أخيرًا ، نضيف التعليق التوضيحي إلى الصفحة باستخدام طريقة التعليقات التوضيحية.

## الخطوة 3: حفظ المستند

الخطوة الأخيرة هي حفظ مستند PDF مع إضافة التعليقات التوضيحية بالحبر. يتم تحقيق ذلك باستخدام مقتطف الشفرة التالي:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

هنا ، نقوم بربط اسم ملف الإخراج بدليل البيانات وحفظ المستند باستخدام طريقة الحفظ.

### مثال على كود المصدر لإضافة تعليق توضيحي بالحبر باستخدام Aspose.PDF لـ .NET

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
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString (stroke.InkColor)) ؛
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

في هذا البرنامج التعليمي ، اكتشفنا كيفية إضافة التعليقات التوضيحية بالحبر إلى مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وشفرة المصدر C # المتوفرة ، يمكن للمطورين بسهولة تنفيذ وظيفة Ink Annotation في تطبيقات معالجة PDF الخاصة بهم.

### التعليمات

#### س: ما هو التعليق التوضيحي بالحبر في مستند PDF؟

ج: يسمح التعليق التوضيحي بالحبر في مستند PDF للمستخدمين برسم تعليقات توضيحية بالحبر بشكل حر باستخدام قلم أو ماوس. يتم استخدامه بشكل شائع لإضافة الرسومات التخطيطية أو الرسوم البيانية أو التعليقات التوضيحية الأخرى المرسومة يدويًا إلى ملف PDF.

#### س: هل يمكنني تخصيص مظهر التعليقات التوضيحية بالحبر؟

ج: نعم ، يوفر Aspose.PDF for .NET خصائص متنوعة لتخصيص مظهر التعليقات التوضيحية بالحبر ، مثل اللون والعتامة ونمط الغطاء وعرض الحدود والمزيد. يمكن للمطورين تعديل هذه الخصائص لتلبي متطلباتهم الخاصة.

#### س: هل من الممكن إضافة العديد من التعليقات التوضيحية بالحبر إلى صفحة PDF واحدة؟

ج: نعم ، يمكنك إضافة العديد من التعليقات التوضيحية بالحبر إلى صفحة PDF واحدة باستخدام Aspose.PDF لـ .NET. يمكن أن يكون لكل تعليق توضيحي بالحبر مجموعته الخاصة من النقاط والمظهر المخصص.

#### س: هل يمكنني إضافة التعليقات التوضيحية بالحبر إلى مستندات PDF الموجودة؟

ج: نعم ، يتيح لك Aspose.PDF for .NET إضافة التعليقات التوضيحية بالحبر إلى كل من مستندات PDF المنشأة حديثًا وملفات PDF الموجودة. يمكنك فتح ملف PDF موجود وإضافة التعليقات التوضيحية بالحبر وحفظ المستند المحدث.

#### س: ما هي بعض حالات الاستخدام الشائعة للتعليقات التوضيحية بالحبر في مستندات PDF؟

ج: التعليقات التوضيحية بالحبر مفيدة لمجموعة كبيرة من التطبيقات ، بما في ذلك إضافة التوقيعات أو الملاحظات المكتوبة بخط اليد إلى نماذج PDF ، ووضع تعليقات توضيحية على المخططات المعمارية أو الرسومات الهندسية ، وترميز المستندات للمراجعة التعاونية.