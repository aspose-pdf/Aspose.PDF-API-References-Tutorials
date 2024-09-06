---
title: إضافة عناوين مختلفة في ملف PDF
linktitle: إضافة عناوين مختلفة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة رؤوس مختلفة بسهولة لكل صفحة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
في هذا البرنامج التعليمي، سنوضح لك خطوة بخطوة كيفية إضافة رؤوس مختلفة في ملف PDF باستخدام Aspose.PDF لـ .NET. وسنوضح لك كيفية استخدام كود المصدر C# المقدم لإضافة رؤوس مخصصة لكل صفحة من ملف PDF.

## الخطوة 1: إعداد البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF

الخطوة الأولى هي تحميل مستند PDF الموجود في مشروعك. وإليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي إلى الدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 3: إنشاء مخازن رأسية

الآن بعد أن قمت بتحميل مستند PDF، يمكنك إنشاء طوابع الرأس لإضافتها. إليك الطريقة:

```csharp
// إنشاء ثلاثة مخازن رأسية
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

يقوم الكود أعلاه بإنشاء ثلاثة مخازن رأسية جديدة تحتوي على النص المحدد.

## الخطوة 4: تكوين خصائص مخزن الرأس

قبل إضافة طوابع الرأس إلى مستند PDF، يمكنك تكوين خصائص مختلفة لكل ختم، مثل المحاذاة والحجم واللون وما إلى ذلك. وإليك الطريقة:

```csharp
// تكوين مخزن الرأس الأول
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// تكوين مخزن الرأس الثاني
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// تكوين مخزن الرأس الثالث
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

يمكنك ضبط هذه الخصائص حسب الحاجة لكل مخزن رأس.

## الخطوة 5: إضافة طوابع الرأس إلى ملف PDF

الآن بعد أن أصبحت طوابع الرأس جاهزة، يمكنك إضافتها إلى كل صفحة محددة من مستند PDF. وإليك الطريقة:

```csharp
// إضافة مخازن رأسية إلى صفحات محددة
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

يضيف الكود أعلاه كل ختم رأس إلى الصفحة المقابلة من مستند PDF.

## الخطوة 6: احفظ المستند الناتج

بمجرد إضافة طوابع الرأس، يمكنك حفظ مستند PDF المحرر. إليك الطريقة:

```csharp
// حفظ المستند المحدث
doc.Save(dataDir);
```

يقوم الكود أعلاه بحفظ مستند PDF المحرر في الدليل المحدد.

### نموذج كود المصدر لإضافة رؤوس مختلفة باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// وثيقة مفتوحة المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// إنشاء ثلاثة طوابع
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

// ضبط محاذاة الطوابع (وضع الطوابع في أعلى الصفحة، في المنتصف أفقيًا)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// حدد نمط الخط على أنه غامق
stamp1.TextState.FontStyle = FontStyles.Bold;

// تعيين معلومات لون الخلفية للنص باللون الأحمر
stamp1.TextState.ForegroundColor = Color.Red;

// حدد حجم الخط بـ 14
stamp1.TextState.FontSize = 14;

// الآن نحتاج إلى ضبط المحاذاة الرأسية لكائن الطابع الثاني على أعلى
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// تعيين معلومات المحاذاة الأفقية للطابع على أنها محاذاة إلى المنتصف
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// تعيين عامل التكبير لكائن الطوابع
stamp2.Zoom = 10;

//تعيين تنسيق كائن الطوابع الثالث
// حدد معلومات المحاذاة الرأسية لكائن الطوابع كأعلى
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// تعيين معلومات المحاذاة الأفقية لكائن الطوابع على محاذاة المركز
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// ضبط زاوية الدوران لكائن الطوابع
stamp3.RotateAngle = 35;

// تعيين اللون الوردي كلون خلفية للطابع
stamp3.TextState.BackgroundColor = Color.Pink;

// تغيير معلومات وجه الخط للطابع إلى Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// تمت إضافة الختم الأول على الصفحة الأولى؛
doc.Pages[1].AddStamp(stamp1);

// تمت إضافة الختم الثاني على الصفحة الثانية؛
doc.Pages[2].AddStamp(stamp2);

// تمت إضافة الختم الثالث على الصفحة الثالثة.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// حفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهانينا! لقد تعلمت كيفية إضافة عناوين مختلفة لكل صفحة من مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لتخصيص العناوين لمستندات PDF الخاصة بك.

### الأسئلة الشائعة حول إضافة عناوين مختلفة في ملف PDF

#### س: ما هو الغرض من إضافة رؤوس مختلفة في ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: إن إضافة عناوين مختلفة إلى ملف PDF باستخدام Aspose.PDF for .NET يسمح لك بتخصيص المحتوى المعروض في أعلى كل صفحة. وهذه الميزة مفيدة بشكل خاص لإضافة العناوين وأسماء الأقسام وأرقام الصفحات وغيرها من المعلومات التي تختلف عبر الصفحات المختلفة في مستند PDF.

#### س: هل يمكنني تخصيص مظهر كل رأس، مثل المحاذاة، والخط، والحجم، واللون، والدوران؟

 ج: نعم، يمكنك تخصيص مظهر كل ختم رأس الصفحة بالكامل. يوضح كود المصدر C# المقدم كيفية تعيين خصائص مختلفة لختم الرأس.`TextStamp` الكائنات لكل رأس، بما في ذلك المحاذاة الرأسية والأفقية، ونمط الخط، وحجم الخط، ولون الخط، ولون الخلفية، وزاوية الدوران.

#### س: هل من الممكن إضافة عدة طوابع رأسية إلى نفس الصفحة من مستند PDF؟

ج: في حين يوضح البرنامج التعليمي المقدم إضافة رؤوس مختلفة إلى صفحات مميزة من مستند PDF، يمكنك تعديل الكود لإضافة عدة رؤوس إلى نفس الصفحة. قد يكون هذا مفيدًا إذا كنت تريد عرض رؤوس مختلفة داخل نفس القسم.

#### س: كيف يمكنني التأكد من أن العناوين لا تتداخل مع المحتوى الرئيسي لصفحات PDF؟

 أ: لمنع التداخل، يمكنك ضبط`VerticalAlignment`, `HorizontalAlignment` ، وغيرها من خصائص`TextStamp` الكائنات. ستتحكم هذه الإعدادات في مكان وضع العناوين على الصفحة، مما يسمح لك بوضعها بطريقة لا تعيق المحتوى الرئيسي.

#### س: هل يمكنني استخدام هذه الطريقة لإضافة رؤوس إلى مستندات PDF موجودة تحتوي على عدد متفاوت من الصفحات؟

ج: نعم، يمكنك تعديل الكود المصدر المقدم لإضافة عناوين إلى مستندات PDF الموجودة التي تحتوي على عدد متفاوت من الصفحات. ما عليك سوى تعديل الكود ليتناسب مع عدد العناوين التي تريد إضافتها وربط كل عنوان بالصفحة المطلوبة.

#### س: ماذا لو أردت إضافة رؤوس لصفحات محددة، وليس فقط الصفحات الثلاث الأولى؟

 أ: يوضح البرنامج التعليمي إضافة عناوين إلى الصفحات الثلاث الأولى لأغراض توضيحية. لإضافة عناوين إلى صفحات معينة بعد الصفحات الثلاث الأولى، اضبط الكود من خلال الرجوع إلى مؤشرات الصفحات المقابلة وإنشاء`TextStamp` الأشياء لكل صفحة.

#### س: هل يمكنني استخدام الصور كعناوين بدلاً من النص؟

 ج: يركز البرنامج التعليمي المقدم على إضافة عناوين نصية. ومع ذلك، يمكنك تطبيق نهج مماثل لإضافة عناوين تعتمد على الصور باستخدام`ImageStamp` الأشياء بدلا من`TextStamp` الكائنات. وهذا يتضمن إنشاء وتكوين`ImageStamp` الأشياء ذات الخصائص المرغوبة.

#### س: كيف يمكنني تطبيق هذه المعرفة لإضافة تذييلات مختلفة لكل صفحة من مستند PDF؟

 ج: يمكن تطبيق نفس النهج الموضح في هذا البرنامج التعليمي لإضافة تذييلات مختلفة لكل صفحة من مستند PDF. بدلاً من العناوين، يمكنك إنشاء وتكوين`TextStamp` أو`ImageStamp` الكائنات وإضافتها إلى أسفل كل صفحة باستخدام`AddStamp` طريقة.

#### س: هل يمكنني أتمتة عملية إضافة الرؤوس إلى مستندات PDF المتعددة في عملية دفعية؟

ج: نعم، يمكنك أتمتة عملية إضافة الرؤوس إلى مستندات PDF المتعددة باستخدام البرنامج النصي أو البرنامج الذي يتكرر عبر قائمة المستندات ويطبق عملية ختم الرأس على كل مستند.