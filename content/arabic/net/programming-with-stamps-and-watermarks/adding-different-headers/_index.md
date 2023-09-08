---
title: إضافة رؤوس مختلفة في ملف PDF
linktitle: إضافة رؤوس مختلفة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة رؤوس مختلفة بسهولة إلى كل صفحة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
في هذا البرنامج التعليمي، سنأخذك خطوة بخطوة حول كيفية إضافة رؤوس مختلفة في ملف PDF باستخدام Aspose.PDF لـ .NET. سنوضح لك كيفية استخدام كود مصدر C# المقدم لإضافة رؤوس مخصصة لكل صفحة من ملف PDF.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF الخاصة بـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF

الخطوة الأولى هي تحميل مستند PDF الموجود في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 3: إنشاء المخازن المؤقتة للرأس

الآن بعد أن قمت بتحميل مستند PDF، يمكنك إنشاء طوابع الرأس لإضافتها. إليك الطريقة:

```csharp
// إنشاء ثلاثة مخازن رأسية
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

ينشئ التعليمة البرمجية أعلاه ثلاثة مخازن رأسية جديدة تحتوي على النص المحدد.

## الخطوة 4: تكوين خصائص المخزن المؤقت للرأس

قبل إضافة طوابع الرأس إلى مستند PDF، يمكنك تكوين خصائص مختلفة لكل ختم، مثل المحاذاة والحجم واللون وما إلى ذلك. وإليك الطريقة:

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

يمكنك ضبط هذه الخصائص حسب الحاجة لكل مخزن مؤقت للرأس.

## الخطوة 5: إضافة طوابع الرأس إلى PDF

الآن بعد أن أصبحت طوابع الرأس جاهزة، يمكنك إضافتها إلى كل صفحة محددة من مستند PDF. إليك الطريقة:

```csharp
// إضافة مخازن رأسية مؤقتة إلى صفحات محددة
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

يضيف الكود أعلاه كل ختم رأس إلى الصفحة المقابلة لمستند PDF.

## الخطوة 6: احفظ مستند الإخراج

بمجرد إضافة طوابع الرأس، يمكنك حفظ مستند PDF المحرر. إليك الطريقة:

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

// إنشاء ثلاثة طوابع
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

// ضبط محاذاة الطوابع (ضع الختم في أعلى الصفحة، مع توسيطه أفقيًا)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// حدد نمط الخط على أنه غامق
stamp1.TextState.FontStyle = FontStyles.Bold;

// قم بتعيين معلومات اللون الأساسي للنص باللون الأحمر
stamp1.TextState.ForegroundColor = Color.Red;

// حدد حجم الخط كـ 14
stamp1.TextState.FontSize = 14;

// نحن الآن بحاجة إلى ضبط المحاذاة الرأسية لكائن الختم الثاني على أنه أعلى
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// قم بتعيين معلومات المحاذاة الأفقية للختم كمحاذاة للوسط
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// قم بتعيين عامل التكبير/التصغير لكائن الطوابع
stamp2.Zoom = 10;

//قم بتعيين تنسيق كائن الطابع الثالث
// حدد معلومات المحاذاة العمودية لكائن الطابع على أنها TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// قم بتعيين معلومات المحاذاة الأفقية لكائن الطابع كمحاذاة للوسط
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// ضبط زاوية الدوران لكائن الطوابع
stamp3.RotateAngle = 35;

// تعيين اللون الوردي كلون خلفية للختم
stamp3.TextState.BackgroundColor = Color.Pink;

// قم بتغيير معلومات وجه الخط للختم إلى Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// تتم إضافة الطابع الأول على الصفحة الأولى؛
doc.Pages[1].AddStamp(stamp1);

// تتم إضافة الطابع الثاني في الصفحة الثانية؛
doc.Pages[2].AddStamp(stamp2);

// تتم إضافة الطابع الثالث في الصفحة الثالثة.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// احفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة رؤوس مختلفة لكل صفحة من مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لتخصيص رؤوس مستندات PDF الخاصة بك.

### الأسئلة الشائعة لإضافة رؤوس مختلفة في ملف PDF

#### س: ما هو الغرض من إضافة رؤوس مختلفة في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: تتيح لك إضافة رؤوس مختلفة إلى ملف PDF باستخدام Aspose.PDF لـ .NET تخصيص المحتوى المعروض في أعلى كل صفحة. تعد هذه الميزة مفيدة بشكل خاص لإضافة العناوين وأسماء الأقسام وأرقام الصفحات والمعلومات الأخرى التي تختلف عبر الصفحات المختلفة لمستند PDF.

#### س: هل يمكنني تخصيص مظهر كل رأس، مثل المحاذاة والخط والحجم واللون والتدوير؟

 ج: نعم، يمكنك تخصيص مظهر كل ختم رأسي بشكل كامل. يوضح كود مصدر C# المقدم كيفية تعيين خصائص مختلفة لملف`TextStamp` كائنات لكل رأس، بما في ذلك المحاذاة الرأسية والأفقية ونمط الخط وحجم الخط ولون الخط ولون الخلفية وزاوية التدوير.

#### س: هل من الممكن إضافة طوابع رأسية متعددة إلى نفس الصفحة من مستند PDF؟

ج: بينما يوضح البرنامج التعليمي المقدم إضافة رؤوس مختلفة إلى صفحات مختلفة من مستند PDF، يمكنك تعديل الكود لإضافة طوابع رأسية متعددة إلى نفس الصفحة. قد يكون هذا مفيدًا إذا كنت تريد عرض رؤوس متنوعة داخل نفس القسم.

#### س: كيف يمكنني التأكد من عدم تداخل الرؤوس مع المحتوى الرئيسي لصفحات PDF؟

 ج: لمنع التداخل، يمكنك ضبط`VerticalAlignment`, `HorizontalAlignment` ، وغيرها من خصائص`TextStamp` أشياء. ستتحكم هذه الإعدادات في مكان وضع الرؤوس على الصفحة، مما يسمح لك بوضعها بطريقة لا تعيق المحتوى الرئيسي.

#### س: هل يمكنني استخدام هذه الطريقة لإضافة رؤوس إلى مستندات PDF الموجودة بأعداد مختلفة من الصفحات؟

ج: نعم، يمكنك تعديل كود المصدر المقدم لإضافة رؤوس إلى مستندات PDF الموجودة بأعداد مختلفة من الصفحات. ما عليك سوى ضبط الكود ليتناسب مع عدد الرؤوس التي تريد إضافتها وربط كل رأس بالصفحة المطلوبة.

#### س: ماذا لو أردت إضافة رؤوس إلى صفحات معينة، وليس الصفحات الثلاث الأولى فقط؟

 ج: يوضح البرنامج التعليمي إضافة رؤوس إلى الصفحات الثلاث الأولى لأغراض توضيحية. لإضافة رؤوس إلى صفحات محددة تتجاوز الثلاثة الأولى، قم بضبط الكود من خلال الرجوع إلى فهارس الصفحات المقابلة وإنشاءها`TextStamp` كائنات لكل صفحة.

#### س: هل يمكنني استخدام الصور كرؤوس بدلاً من النص؟

 ج: يركز البرنامج التعليمي المقدم على إضافة رؤوس مستندة إلى النص. ومع ذلك، يمكنك تطبيق أسلوب مماثل لإضافة رؤوس مستندة إلى الصور باستخدام`ImageStamp` الكائنات بدلا من`TextStamp` أشياء. وهذا من شأنه أن ينطوي على إنشاء وتكوين`ImageStamp` الكائنات ذات الخصائص المطلوبة.

#### س: كيف يمكنني تطبيق هذه المعرفة لإضافة تذييلات مختلفة لكل صفحة من مستند PDF؟

 ج: يمكن تطبيق نفس الأسلوب الموضح في هذا البرنامج التعليمي لإضافة تذييلات مختلفة لكل صفحة من مستند PDF. بدلاً من الرؤوس، يمكنك إنشاء وتكوين`TextStamp` أو`ImageStamp` الكائنات وإضافتها إلى أسفل كل صفحة باستخدام`AddStamp` طريقة.

#### س: هل يمكنني أتمتة عملية إضافة الرؤوس إلى مستندات PDF متعددة في عملية دفعية؟

ج: نعم، يمكنك أتمتة عملية إضافة رؤوس إلى مستندات PDF متعددة باستخدام برنامج نصي أو برنامج يتكرر خلال قائمة المستندات ويطبق عملية ختم الرأس على كل مستند.