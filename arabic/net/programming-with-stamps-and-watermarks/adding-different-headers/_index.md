---
title: إضافة رؤوس مختلفة في ملف PDF
linktitle: إضافة رؤوس مختلفة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة رؤوس مختلفة بسهولة لكل صفحة في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية إضافة رؤوس مختلفة في ملف PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام شفرة المصدر C # المقدمة لإضافة رؤوس مخصصة لكل صفحة من ملف PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الثانية: تحميل مستند PDF

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: إنشاء مخازن الرؤوس

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك إنشاء أختام رأس لإضافتها. إليك الطريقة:

```csharp
// إنشاء ثلاثة مخازن رأس
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

ينشئ الكود أعلاه ثلاثة مخازن رأس جديدة تحتوي على النص المحدد.

## الخطوة 4: تكوين خصائص المخزن المؤقت للرأس

قبل إضافة أختام الرأس إلى مستند PDF ، يمكنك تكوين خصائص مختلفة لكل ختم ، مثل المحاذاة والحجم واللون وما إلى ذلك ، وإليك الطريقة:

```csharp
// تكوين المخزن المؤقت للرأس الأول
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// تكوين المخزن المؤقت للرأس الثاني
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// تكوين المخزن المؤقت للرأس الثالث
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

يمكنك ضبط هذه الخصائص حسب الحاجة لكل مخزن رأس مؤقت.

## الخطوة 5: إضافة أختام الرأس إلى ملف PDF

الآن بعد أن أصبحت أختام الرأس جاهزة ، يمكنك إضافتها إلى كل صفحة محددة من مستند PDF. إليك الطريقة:

```csharp
// إضافة مخازن رأس إلى صفحات معينة
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

يضيف الرمز أعلاه كل ختم رأس إلى الصفحة المقابلة لمستند PDF.

## الخطوة 6: احفظ المستند الناتج

بمجرد إضافة أختام الرأس ، يمكنك حفظ مستند PDF المحرر. إليك الطريقة:

```csharp
// احفظ المستند المحدث
doc.Save(dataDir);
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لإضافة رؤوس مختلفة باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// وثيقة مفتوحة المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// قم بإنشاء ثلاثة طوابع
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

// ضبط محاذاة الختم (ختم مكان على أعلى الصفحة ، توسيط أفقياً)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// حدد نمط الخط على أنه غامق
stamp1.TextState.FontStyle = FontStyles.Bold;

// قم بتعيين معلومات لون المقدمة الأمامية للنص باللون الأحمر
stamp1.TextState.ForegroundColor = Color.Red;

// حدد حجم الخط كـ 14
stamp1.TextState.FontSize = 14;

// نحتاج الآن إلى ضبط المحاذاة الرأسية لكائن الختم الثاني على أنها Top
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// قم بتعيين معلومات المحاذاة الأفقية للختم كمحاذاة للوسط
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// اضبط عامل التكبير لكائن الختم
stamp2.Zoom = 10;

//اضبط تنسيق كائن الطابع الثالث
// حدد معلومات المحاذاة الرأسية لكائن الطوابع على أنها TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// قم بتعيين معلومات المحاذاة الأفقية لكائن الطوابع كمحاذة للوسط
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// اضبط زاوية الدوران لكائن الختم
stamp3.RotateAngle = 35;

// تعيين اللون الوردي كخلفية للطابع
stamp3.TextState.BackgroundColor = Color.Pink;

// قم بتغيير معلومات وجه الخط للطابع إلى Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// يضاف الطابع الأول على الصفحة الأولى ؛
doc.Pages[1].AddStamp(stamp1);

// يضاف الطابع الثاني على الصفحة الثانية ؛
doc.Pages[2].AddStamp(stamp2);

// يضاف الطابع الثالث على الصفحة الثالثة.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// احفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة رؤوس مختلفة لكل صفحة من مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لتخصيص رؤوس مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول إضافة رؤوس مختلفة في ملف PDF

#### س: ما هو الغرض من إضافة رؤوس مختلفة في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: إضافة رؤوس مختلفة إلى ملف PDF باستخدام Aspose.PDF for .NET يسمح لك بتخصيص المحتوى المعروض أعلى كل صفحة. هذه الميزة مفيدة بشكل خاص لإضافة العناوين وأسماء الأقسام وأرقام الصفحات والمعلومات الأخرى التي تختلف عبر الصفحات المختلفة لمستند PDF.

#### س: هل يمكنني تخصيص مظهر كل رأس ، مثل المحاذاة والخط والحجم واللون والتدوير؟

 ج: نعم ، يمكنك تخصيص مظهر كل ختم رأس بشكل كامل. يوضح كود المصدر C # المقدم كيفية تعيين الخصائص المختلفة لملف`TextStamp` كائنات لكل رأس ، بما في ذلك المحاذاة الرأسية والأفقية ونمط الخط وحجم الخط ولون الخط ولون الخلفية وزاوية التدوير.

#### س: هل من الممكن إضافة أختام رأس متعددة إلى نفس الصفحة من مستند PDF؟

ج: بينما يوضح البرنامج التعليمي المقدم إضافة رؤوس مختلفة إلى صفحات مميزة من مستند PDF ، يمكنك تكييف الكود لإضافة أختام رأس متعددة إلى نفس الصفحة. قد يكون هذا مفيدًا إذا كنت تريد عرض رؤوس متنوعة داخل نفس القسم.

#### س: كيف يمكنني التأكد من عدم تداخل الرؤوس مع المحتوى الرئيسي لصفحات PDF؟

 ج: لمنع التداخل ، يمكنك ضبط ملف`VerticalAlignment`, `HorizontalAlignment` ، وغيرها من خصائص`TextStamp` أشياء. ستتحكم هذه الإعدادات في مكان وضع الرؤوس على الصفحة ، مما يسمح لك بوضعها بطريقة لا تعيق المحتوى الرئيسي.

#### س: هل يمكنني استخدام هذه الطريقة لإضافة رؤوس إلى مستندات PDF الحالية بأعداد متفاوتة من الصفحات؟

ج: نعم ، يمكنك تكييف كود المصدر المقدم لإضافة رؤوس إلى مستندات PDF الحالية بأعداد مختلفة من الصفحات. ما عليك سوى ضبط الشفرة لمطابقة عدد الرؤوس التي تريد إضافتها وربط كل رأس بالصفحة المطلوبة.

#### س: ماذا لو كنت أرغب في إضافة رؤوس إلى صفحات معينة ، وليس الصفحات الثلاث الأولى فقط؟

 ج: يوضح البرنامج التعليمي إضافة رؤوس إلى الصفحات الثلاث الأولى لأغراض التوضيح. لإضافة رؤوس إلى صفحات معينة بعد الثلاثة الأولى ، اضبط الكود بالرجوع إلى فهارس الصفحات المقابلة وإنشاءها`TextStamp` كائنات لكل صفحة.

#### س: هل يمكنني استخدام الصور كرؤوس بدلاً من نص؟

 ج: يركز البرنامج التعليمي المقدم على إضافة رؤوس نصية. ومع ذلك ، يمكنك تطبيق طريقة مماثلة لإضافة رؤوس قائمة على الصور باستخدام`ImageStamp` كائنات بدلا من`TextStamp` أشياء. سيشمل هذا إنشاء وتكوين`ImageStamp` كائنات ذات الخصائص المرغوبة.

#### س: كيف يمكنني تطبيق هذه المعرفة لإضافة تذييلات مختلفة لكل صفحة من مستند PDF؟

 ج: يمكن تطبيق نفس الطريقة الموضحة في هذا البرنامج التعليمي لإضافة تذييلات مختلفة لكل صفحة من مستند PDF. بدلاً من الرؤوس ، يمكنك إنشاء وتكوين`TextStamp` أو`ImageStamp` كائنات وإضافتها إلى أسفل كل صفحة باستخدام`AddStamp` طريقة.

#### س: هل يمكنني أتمتة عملية إضافة رؤوس إلى مستندات PDF متعددة في عملية مجمعة؟

ج: نعم ، يمكنك أتمتة عملية إضافة رؤوس إلى مستندات PDF متعددة باستخدام برنامج نصي أو برنامج يتكرر من خلال قائمة المستندات ويطبق عملية ختم العنوان على كل مستند.