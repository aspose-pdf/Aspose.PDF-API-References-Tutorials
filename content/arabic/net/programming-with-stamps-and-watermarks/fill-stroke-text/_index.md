---
title: ملء النص في ملف PDF
linktitle: ملء النص في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية ملء النص وتحديد خطوطه العريضة بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 90
url: /ar/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
في هذا البرنامج التعليمي، سنوضح لك خطوة بخطوة كيفية ملء النص وتحديد الخطوط العريضة له في ملف PDF باستخدام Aspose.PDF for .NET. وسنوضح لك كيفية استخدام كود المصدر C# المقدم لتطبيق ألوان التعبئة وتحديد الخطوط العريضة للنص في ملف PDF.

## الخطوة 1: إعداد البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: إنشاء كائن TextState

الخطوة الأولى هي إنشاء كائن TextState لتمرير الخصائص المتقدمة. إليك الطريقة:

```csharp
// إنشاء كائن TextState لنقل الخصائص المتقدمة
TextState ts = new TextState();

// تعيين لون المخطط التفصيلي
ts.StrokingColor = Color.Gray;

// تحديد وضع عرض النص
ts.RenderingMode = TextRenderingMode.StrokeText;
```

يقوم الكود أعلاه بإنشاء كائن TextState جديد ويحدد لون المخطط التفصيلي بالإضافة إلى كيفية عرض النص.

## الخطوة 3: تحميل مستند PDF

الآن بعد أن أصبح كائن TextState جاهزًا، يمكننا تحميل مستند PDF حيث نريد تطبيق تعبئة النص والمخطط التفصيلي. إليك الطريقة:

```csharp
// تحميل مستند PDF كمدخل
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

يقوم الكود أعلاه بتحميل مستند PDF الموجود باستخدام فئة PdfFileStamp من مكتبة Aspose.PDF.Facades.

## الخطوة 4: إضافة التعبئة والحدود إلى النص

الآن بعد تحميل مستند PDF، يمكننا إضافة التعبئة والخطوط العريضة إلى النص. وإليك الطريقة:

```csharp
// إنشاء ختم (Stamp) بالنص والخصائص المحددة
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// ربط كائن TextState
stamp.BindTextState(ts);

// مجموعة الأصل X، Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// أضف الطابع إلى المستند
fileStamp.AddStamp(stamp);
```

يقوم الكود أعلاه بإنشاء ختم بالنص المحدد وخصائص التعبئة والحدود المحددة.

## الخطوة 5: احفظ المستند الناتج

بمجرد إضافة ختم النص، يمكننا حفظ مستند PDF المعدّل. إليك الطريقة:

```csharp
// حفظ المستند المعدل
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

يقوم الكود أعلاه بحفظ مستند PDF المحرر في الدليل المحدد.

### عينة من كود المصدر لتعبئة نص الحدود باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن TextState لنقل الخصائص المتقدمة
TextState ts = new TextState();

// تعيين لون للسكتة الدماغية
ts.StrokingColor = Color.Gray;

// تعيين وضع عرض النص
ts.RenderingMode = TextRenderingMode.StrokeText;

// تحميل مستند PDF المدخل
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// ربط حالة النص
stamp.BindTextState(ts);

// تعيين أصل X و Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// إضافة طابع
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## خاتمة

تهانينا! لقد تعلمت كيفية ملء النص وتحديد الخطوط العريضة له في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة لتخصيص ألوان التعبئة وتحديد الخطوط العريضة له في مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول تعبئة النص في ملف PDF

#### س: ماذا يعني ملء النص وتحديد الخطوط العريضة له في مستند PDF، ومتى قد أحتاج إلى القيام بذلك؟

أ: تتضمن عملية ملء النص وتحديد الخطوط العريضة له في مستند PDF تطبيق الألوان على الجزء الداخلي من أحرف النص (ملء النص) وعلى الحدود المحيطة بالنص (تحديد الخطوط العريضة). ويمكن استخدام هذا لتحسين المظهر المرئي للنص أو التأكيد عليه أو تسليط الضوء على محتوى معين داخل ملف PDF.

#### س: كيف يقوم كود المصدر C# المقدم بملء النص وتحديد الخطوط العريضة له في ملف PDF؟

 أ: يوضح كود المصدر المقدم كيفية إنشاء`TextState` يستخدم هذا الكائن لتحديد خصائص نص متقدمة، مثل لون المخطط التفصيلي ووضع العرض. ثم يستخدم Aspose.PDF.Facades لتحميل مستند PDF موجود، وإنشاء طابع يحتوي على النص بخصائص التعبئة والحدود المحددة، وإضافة الطابع إلى المستند.

####  س: ما هو الغرض من`TextState` object in the code?

 أ: ال`TextState`يستخدم الكائن لتحديد خصائص النص المتقدمة، بما في ذلك لون مخطط النص (الخط) ووضع العرض. وهو يسمح لك بتخصيص كيفية ظهور النص من حيث الخط والتعبئة.

#### س: هل يمكنني تطبيق ألوان تعبئة وألوان مخطط مختلفة على أجزاء مختلفة من نفس النص؟

 ج: نعم، يمكنك تعديل الكود لإنشاء مختلف`TextState` الكائنات ذات ألوان التعبئة والخطوط العريضة المميزة وتطبيقها على أجزاء معينة من النص باستخدام ألوان منفصلة`Stamp` أشياء.

#### س: هل يمكنني تطبيق ألوان التعبئة والخطوط العريضة على النص الموجود بالفعل في مستند PDF؟

 ج: نعم، يمكنك استخدام مبادئ مماثلة لتطبيق ألوان التعبئة والخطوط العريضة على النص الموجود في مستند PDF عن طريق تحديد كائنات النص المناسبة وإضافتها كطوابع باللون المطلوب.`TextState` ملكيات.

#### س: كيف يمكنني ضبط التعتيم ودمج النص المملوء والمحدد؟

 أ: يسمح لك الكود المقدم بتعيين خصائص التعتيم والمزج للختم باستخدام`Opacity` و`BlendingSpace`الخصائص على التوالي. يمكنك ضبط هذه القيم لتحقيق التأثير المرئي المطلوب.

#### س: كيف يمكنني تطبيق ألوان تعبئة وخطوط عريضة مختلفة على طوابع متعددة ضمن نفس مستند PDF؟

 أ: يمكنك إنشاء العديد`TextState` الكائنات بألوان تعبئة وخطوط عريضة مختلفة، ثم قم بإنشاء كائنات منفصلة`Stamp` كائنات لكل مجموعة نصية بألوان مميزة. أضف هذه الطوابع إلى نفس مستند PDF باستخدام`PdfFileStamp` فصل.

#### س: هل يمكنني استخدام خطوط أخرى غير Arial للنص المحدد والمملوء؟

 ج: نعم، يمكنك تغيير الخط عن طريق تعديل معلمة اسم الخط في`FormattedText` عند إنشاء الطابع، يمكنك استخدام أي خط متوفر على نظامك.

#### س: كيف يمكنني تعديل زاوية دوران النص المحدد والمملوء؟

 أ: يسمح لك الكود المقدم بتعيين زاوية دوران الختم باستخدام`Rotation` الخاصية. يمكنك ضبط هذه الخاصية لتحديد زاوية الدوران المطلوبة للنص.

#### س: كيف يمكنني التحكم في موضع وحجم النص المحدد والمملوء على الصفحة؟

 أ: يمكنك استخدام`SetOrigin` طريقة`Stamp` كائن لتعيين إحداثيات X وY لموضع الختم على الصفحة. بالإضافة إلى ذلك، يمكنك ضبط حجم الخط في`FormattedText` منشئ للتحكم في حجم النص.