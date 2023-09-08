---
title: ملء نص السكتة الدماغية في ملف PDF
linktitle: ملء نص السكتة الدماغية في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعبئة النص وتحديد الخطوط العريضة له بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 90
url: /ar/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
في هذا البرنامج التعليمي، سنأخذك خطوة بخطوة حول كيفية ملء النص وتخطيطه في ملف PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود مصدر C# المتوفر لتطبيق ألوان التعبئة والمخطط التفصيلي على النص في ملف PDF.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF الخاصة بـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: إنشاء كائن TextState

الخطوة الأولى هي إنشاء كائن TextState لتمرير الخصائص المتقدمة. إليك الطريقة:

```csharp
// قم بإنشاء كائن TextState لنقل الخصائص المتقدمة
TextState ts = new TextState();

// تعيين لون المخطط التفصيلي
ts.StrokingColor = Color.Gray;

// تحديد وضع عرض النص
ts.RenderingMode = TextRenderingMode.StrokeText;
```

يقوم التعليمة البرمجية أعلاه بإنشاء كائن TextState جديد وتعيين لون المخطط التفصيلي بالإضافة إلى كيفية عرض النص.

## الخطوة 3: تحميل وثيقة PDF

الآن بعد أن أصبح كائن TextState جاهزًا، يمكننا تحميل مستند PDF حيث نريد تطبيق تعبئة النص والمخطط التفصيلي. إليك الطريقة:

```csharp
// قم بتحميل مستند PDF كمدخل
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

يقوم الكود أعلاه بتحميل مستند PDF الموجود باستخدام فئة PdfFileStamp من مكتبة Aspose.PDF.Facades.

## الخطوة 4: إضافة التعبئة والحد إلى النص

الآن بعد أن تم تحميل مستند PDF، يمكننا إضافة التعبئة والمخطط التفصيلي للنص. إليك الطريقة:

```csharp
// قم بإنشاء ختم (Stamp) بالنص والخصائص المحددة
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// ربط كائن TextState
stamp.BindTextState(ts);

// تعيين الأصل X، Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// أضف الختم إلى المستند
fileStamp.AddStamp(stamp);
```

يقوم الكود أعلاه بإنشاء ختم بالنص المحدد وخصائص التعبئة والحد المحددة.

## الخطوة 5: احفظ مستند الإخراج

بمجرد إضافة ختم النص، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ المستند المعدل
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لتعبئة النص باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بإنشاء كائن TextState لنقل الخصائص المتقدمة
TextState ts = new TextState();

// ضبط اللون للسكتة الدماغية
ts.StrokingColor = Color.Gray;

// ضبط وضع عرض النص
ts.RenderingMode = TextRenderingMode.StrokeText;

// قم بتحميل مستند PDF للإدخال
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// ربط حالة النص
stamp.BindTextState(ts);

// تعيين الأصل X، Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// أضف ختم
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## خاتمة

تهنئة ! لقد تعلمت كيفية تعبئة النص وتحديد الخطوط العريضة له في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه المعرفة لتخصيص ألوان التعبئة والمخطط التفصيلي في مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول تعبئة النص في ملف PDF

#### س: ماذا يعني ملء النص وتحديد الخطوط العريضة له في مستند PDF، ومتى قد أحتاج إلى القيام بذلك؟

ج: تتضمن تعبئة النص وتحديده في مستند PDF تطبيق الألوان على الجزء الداخلي من أحرف النص (التعبئة) وعلى الحدود المحيطة بالنص (المخطط التفصيلي). يمكن استخدام ذلك لتحسين المظهر المرئي للنص، أو إنشاء التركيز، أو تمييز محتوى معين داخل ملف PDF.

#### س: كيف يقوم كود مصدر C# المقدم بإنجاز عملية ملء النص وتحديد الخطوط العريضة له في ملف PDF؟

 ج: يوضح الكود المصدري المقدم كيفية إنشاء ملف`TextState` كائن لتحديد خصائص النص المتقدمة، مثل لون المخطط التفصيلي ووضع العرض. ثم يستخدم Aspose.PDF.Facades لتحميل مستند PDF موجود، وإنشاء ختم يحتوي على النص بخصائص التعبئة والحد المحددة، وإضافة الختم إلى المستند.

####  س: ما هو الغرض من`TextState` object in the code?

 ج: ال`TextState`يتم استخدام الكائن لتحديد خصائص النص المتقدمة، بما في ذلك لون مخطط النص (الحد) ووضع العرض. يسمح لك بتخصيص كيفية ظهور النص من حيث الحد والتعبئة.

#### س: هل يمكنني تطبيق ألوان تعبئة ومخططات تفصيلية مختلفة على أجزاء مختلفة من نفس النص؟

 ج: نعم، يمكنك تعديل الكود لإنشاء كود مختلف`TextState` كائنات ذات ألوان تعبئة ومخطط تفصيلي مميزة وتطبيقها على أجزاء معينة من النص باستخدام منفصلة`Stamp` أشياء.

#### س: هل يمكنني تطبيق ألوان التعبئة والمخطط التفصيلي على النص الموجود بالفعل في مستند PDF؟

 ج: نعم، يمكنك استخدام مبادئ مماثلة لتطبيق ألوان التعبئة والمخطط التفصيلي على النص الموجود في مستند PDF عن طريق تحديد كائنات النص المناسبة وإضافتها كطوابع بالمواصفات المطلوبة`TextState` ملكيات.

#### س: كيف يمكنني ضبط العتامة والمزج للنص المعبأ والمحدد؟

 ج: يسمح لك الكود المقدم بضبط خصائص العتامة والمزج للختم باستخدام`Opacity` و`BlendingSpace`الخصائص، على التوالي. يمكنك ضبط هذه القيم لتحقيق التأثير المرئي المطلوب.

#### س: كيف يمكنني تطبيق ألوان تعبئة ومخطط تفصيلي مختلفة على طوابع متعددة داخل مستند PDF نفسه؟

 ج: يمكنك إنشاء عدة`TextState` كائنات ذات ألوان تعبئة ومخطط تفصيلي مختلفة، ثم قم بإنشاء كائنات منفصلة`Stamp` كائنات لكل مجموعة من النصوص بألوان مميزة. أضف هذه الطوابع إلى نفس مستند PDF باستخدام ملف`PdfFileStamp` فصل.

#### س: هل يمكنني استخدام خطوط أخرى غير Arial للنص المحدد والمعبأ؟

 ج: نعم، يمكنك تغيير الخط عن طريق تعديل معلمة اسم الخط في ملف`FormattedText` منشئ عند إنشاء الطوابع. يمكنك استخدام أي خط متاح على نظامك.

#### س: كيف يمكنني تعديل زاوية التدوير للنص المحدد والمملوء؟

 ج: يسمح لك الكود المقدم بضبط زاوية دوران الختم باستخدام`Rotation` ملكية. يمكنك ضبط هذه الخاصية لتحديد زاوية التدوير المطلوبة للنص.

#### س: كيف يمكنني التحكم في موضع وحجم النص المحدد والمعبأ في الصفحة؟

ج: يمكنك استخدام`SetOrigin` طريقة`Stamp` كائن لتعيين إحداثيات X وY لموضع الختم على الصفحة. بالإضافة إلى ذلك، يمكنك ضبط حجم الخط في`FormattedText` منشئ للتحكم في حجم النص.