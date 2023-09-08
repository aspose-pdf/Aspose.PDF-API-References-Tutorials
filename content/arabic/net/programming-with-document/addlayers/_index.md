---
title: إضافة طبقات إلى ملف PDF
linktitle: إضافة طبقات إلى ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة طبقات إلى ملفات PDF باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة مع دروس التعليمات البرمجية لإنشاء ملفات PDF ذات طبقات وحفظها.
type: docs
weight: 20
url: /ar/net/programming-with-document/addlayers/
---
لإضافة طبقات إلى ملف PDF، سوف نستخدم Aspose.PDF لـ .NET. تتيح لنا هذه المكتبة العمل مع ملفات PDF في تطبيقات .NET بشكل فعال. اتبع الإرشادات خطوة بخطوة أدناه لإضافة طبقات باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: إنشاء مستند PDF جديد

 ابدأ بإنشاء مثيل جديد لـ`Document` فئة مقدمة من Aspose.PDF لـ .NET. سيكون هذا بمثابة مستند PDF حيث سنضيف الطبقات.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## الخطوة 2: إضافة صفحة إلى المستند

 بعد ذلك، أضف صفحة إلى المستند باستخدام الملف`Add` طريقة`Pages` جمع في`Document` فصل.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء وإضافة طبقات إلى الصفحة

 إنشاء مثيلات`Layer` فئة لكل طبقة تريد إضافتها إلى ملف PDF. حدد معرفًا فريدًا واسمًا لكل طبقة.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

في هذا البرنامج التعليمي، أضفنا ثلاث طبقات بألوان وأسماء مختلفة إلى الصفحة.

## الخطوة 4: احفظ ملف PDF

 احفظ ملف PDF المعدل باستخدام ملف`Save` طريقة`Document` فصل.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

سيحفظ هذا الرمز ملف PDF المعدل في الدليل المحدد.

### مثال على التعليمات البرمجية المصدر لإضافة طبقات إلى صفحات PDF باستخدام Aspose.PDF لـ .NET

```csharp            
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## خاتمة

في هذه المقالة، قدمنا دليلًا خطوة بخطوة لإضافة طبقات إلى ملفات PDF باستخدام Aspose.PDF لـ .NET. باتباع التعليمات والاستفادة من البرامج التعليمية المتوفرة للتعليمات البرمجية، يمكنك بسهولة دمج الطبقات في مستندات PDF الخاصة بك. تسمح لك الطبقات بتنظيم رؤية المحتوى والتحكم فيه، مما يوفر تجربة أكثر تفاعلية وقابلة للتخصيص للمستخدمين.


### الأسئلة الشائعة لإضافة طبقات إلى ملف PDF

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تمكن المطورين من العمل مع ملفات PDF بشكل فعال في تطبيقات .NET. يوفر مجموعة واسعة من الميزات لإنشاء مستندات PDF وتعديلها ومعالجتها.

#### س: ما هي طبقات PDF؟

ج: تسمح لك طبقات PDF، المعروفة أيضًا باسم مجموعات المحتوى الاختيارية (OCGs)، بالتحكم في رؤية ومظهر محتوى معين داخل ملف PDF. وهي مفيدة لتنظيم المحتوى وإنشاء مستندات تفاعلية.

#### س: هل يمكنني إضافة طبقات متعددة إلى ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك إضافة طبقات متعددة إلى ملف PDF باستخدام Aspose.PDF لـ .NET. يمكن أن يكون لكل طبقة معرف واسم فريد خاص بها، كما هو موضح في البرنامج التعليمي.

#### س: كيف يمكنني تخصيص مظهر الطبقات؟

ج: يمكنك تخصيص مظهر الطبقات عن طريق تحديد خصائص مختلفة، مثل اللون والعتامة والرؤية. يوفر Aspose.PDF for .NET خيارات متنوعة لتحقيق ذلك.

#### س: هل Aspose.PDF for .NET مناسب للمشاريع الاحترافية؟

ج: نعم، Aspose.PDF for .NET هي مكتبة موثوقة ومستخدمة على نطاق واسع لمعالجة ملفات PDF في المشاريع الاحترافية. فهو يوفر وظائف واسعة النطاق وأداء ممتازًا للعمل مع ملفات PDF في تطبيقات .NET.