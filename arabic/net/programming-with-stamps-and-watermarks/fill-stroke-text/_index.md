---
title: قم بتعبئة نص الحد في ملف PDF
linktitle: قم بتعبئة نص الحد في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية ملء النص وتحديد الخطوط العريضة بسهولة في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 90
url: /ar/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية ملء النص ومخططه في ملف PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام الكود المصدري C # لتطبيق ألوان التعبئة والمخطط التفصيلي على النص في ملف PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة 2: إنشاء كائن حالة النص

الخطوة الأولى هي إنشاء كائن TextState لتمرير الخصائص المتقدمة. إليك الطريقة:

```csharp
// قم بإنشاء كائن TextState لنقل الخصائص المتقدمة
TextState ts = new TextState();

// تعيين لون المخطط التفصيلي
ts.StrokingColor = Color.Gray;

// تحديد وضع تجسيد النص
ts.RenderingMode = TextRenderingMode.StrokeText;
```

يقوم الكود أعلاه بإنشاء كائن TextState جديد ويضبط لون المخطط التفصيلي وكذلك كيفية عرض النص.

## الخطوة 3: تحميل مستند PDF

الآن بعد أن أصبح كائن TextState جاهزًا ، يمكننا تحميل مستند PDF حيث نريد تطبيق تعبئة النص والمخطط التفصيلي. إليك الطريقة:

```csharp
// قم بتحميل مستند PDF كمدخل
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

يقوم الكود أعلاه بتحميل مستند PDF الحالي باستخدام فئة PdfFileStamp من مكتبة Aspose.PDF.Facades.

## الخطوة 4: أضف Fill and Stroke إلى النص

الآن بعد أن تم تحميل مستند PDF ، يمكننا إضافة التعبئة والمخطط التفصيلي للنص. إليك الطريقة:

```csharp
// قم بإنشاء طابع (ختم) بالنص المحدد والخصائص
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// ربط كائن حالة النص
stamp.BindTextState(ts);

// تعيين الأصل X ، Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// أضف الختم إلى المستند
fileStamp.AddStamp(stamp);
```

يُنشئ الكود أعلاه طابعًا بالنص المحدد وخصائص التعبئة والحد المحددة.

## الخطوة 5: احفظ المستند الناتج

بمجرد إضافة ختم النص ، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ المستند المعدل
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### عينة من التعليمات البرمجية المصدر لتعبئة النص باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بإنشاء كائن TextState لنقل الخصائص المتقدمة
TextState ts = new TextState();

// اضبط لون السكتة الدماغية
ts.StrokingColor = Color.Gray;

// تعيين وضع عرض النص
ts.RenderingMode = TextRenderingMode.StrokeText;

// قم بتحميل مستند إدخال PDF
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// ربط TextState
stamp.BindTextState(ts);

// تعيين أصل X ، Y.
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// أضف طابع
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## خاتمة

تهنئة ! لقد تعلمت كيفية تعبئة النص وتحديد الخطوط العريضة له في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة لتخصيص ألوان التعبئة والمخطط التفصيلي في مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول نص التعبئة في ملف PDF

#### س: ما المقصود بملء النص وتحديده في مستند PDF ، ومتى أحتاج إلى القيام بذلك؟

ج: يتضمن ملء النص وتحديد الخطوط العريضة في مستند PDF تطبيق الألوان على الأجزاء الداخلية من أحرف النص (تعبئة) وعلى الحدود حول النص (مخطط تفصيلي). يمكن استخدام هذا لتحسين المظهر المرئي للنص أو إنشاء التركيز أو إبراز محتوى معين داخل ملف PDF.

#### س: كيف يُنجز الكود المصدري C # المقدم تعبئة النص وتحديد الخطوط العريضة له في ملف PDF؟

 ج: يوضح كود المصدر المقدم كيفية إنشاء ملف`TextState` لتعريف خصائص النص المتقدمة ، مثل لون المخطط التفصيلي ووضع العرض. ثم يستخدم Aspose.PDF.Facades لتحميل مستند PDF موجود وإنشاء ختم يحتوي على النص بخصائص تعبئة وحد محددة وإضافة الختم إلى المستند.

####  س: ما هو الغرض من`TextState` object in the code?

 ج: إن`TextState`يتم استخدام الكائن لتعريف خصائص النص المتقدمة ، بما في ذلك لون مخطط النص (الحد) ووضع التجسيد. يسمح لك بتخصيص كيفية ظهور النص من حيث السكتة الدماغية والتعبئة.

#### س: هل يمكنني تطبيق ألوان مختلفة للتعبئة والتخطيط على أجزاء مختلفة من نفس النص؟

 ج: نعم ، يمكنك تعديل الكود لإنشاء رمز مختلف`TextState` كائنات ذات ألوان تعبئة وتخطيط تفصيلي مميزة وتطبيقها على أجزاء معينة من النص باستخدام منفصل`Stamp` أشياء.

#### س: هل يمكنني تطبيق ألوان التعبئة والمخطط التفصيلي على نص موجود بالفعل في مستند PDF؟

 ج: نعم ، يمكنك استخدام مبادئ مماثلة لتطبيق ألوان التعبئة والمخطط التفصيلي على النص الموجود في مستند PDF عن طريق تحديد كائنات النص المناسبة وإضافتها كطوابع مع المطلوب`TextState` ملكيات.

#### س: كيف يمكنني ضبط عتامة ومزج النص المعبأ والمخطط؟

 ج: يسمح لك الكود المقدم بتعيين خصائص التعتيم والمزج للختم باستخدام`Opacity` و`BlendingSpace`الخصائص ، على التوالي. يمكنك ضبط هذه القيم لتحقيق التأثير المرئي المطلوب.

#### س: كيف يمكنني تطبيق ألوان مختلفة للتعبئة والتخطيط على أختام متعددة في نفس مستند PDF؟

 ج: يمكنك إنشاء ملفات متعددة`TextState` كائنات ذات ألوان مختلفة للتعبئة والمخطط التفصيلي ، ثم قم بإنشاء منفصلة`Stamp` كائنات لكل مجموعة نصية بألوان مميزة. أضف هذه الأختام إلى نفس مستند PDF باستخدام ملف`PdfFileStamp` فصل.

#### س: هل يمكنني استخدام خطوط أخرى غير Arial للنص المحدد والمعبأ؟

 ج: نعم ، يمكنك تغيير الخط عن طريق تعديل معلمة اسم الخط في ملف`FormattedText` منشئ عند إنشاء الطابع. يمكنك استخدام أي خط متاح على نظامك.

#### س: كيف يمكنني تعديل زاوية الدوران للنص المحدد والمعبأ؟

 ج: يسمح لك الكود المقدم بضبط زاوية دوران الختم باستخدام`Rotation` ملكية. يمكنك ضبط هذه الخاصية لتحديد زاوية التدوير المطلوبة للنص.

#### س: كيف يمكنني التحكم في موضع وحجم النص المحدد والمعبأ على الصفحة؟

ج: يمكنك استخدام ملف`SetOrigin` طريقة`Stamp` لتعيين إحداثيات X و Y لموضع الطابع على الصفحة. بالإضافة إلى ذلك ، يمكنك ضبط حجم الخط بتنسيق`FormattedText` منشئ للتحكم في حجم النص.