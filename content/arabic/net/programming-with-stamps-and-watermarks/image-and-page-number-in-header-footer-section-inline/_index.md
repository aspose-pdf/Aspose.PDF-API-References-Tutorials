---
title: الصورة ورقم الصفحة في قسم تذييل الرأس مضمن
linktitle: الصورة ورقم الصفحة في قسم تذييل الرأس مضمن
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة صورة ورقم الصفحة في الرأس والتذييل باستخدام الفقرات المضمنة مع Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية إضافة صورة ورقم الصفحة في قسم الرأس والتذييل لمستند PDF باستخدام Aspose.PDF لـ .NET. سنستخدم كود مصدر C# المقدم لإنشاء صفحة وتعيين الرأس والتذييل وإضافة صورة ونص باستخدام الفقرات المضمنة في رأس مستند PDF.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF الخاصة بـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: إنشاء مستند وصفحة PDF

الخطوة الأولى هي إنشاء كائن مستند جديد وصفحة في مستند PDF. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء كائن مستند جديد
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// إنشاء صفحة في المستند
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

يقوم الكود أعلاه بإنشاء كائن مستند جديد وصفحة فارغة في مستند PDF.

## الخطوة 3: إضافة الرأس مع صورة ونص مضمّن

الآن بعد أن تم إنشاء الصفحة، يمكننا إضافة قسم رأس يحتوي على صورة ونص باستخدام الفقرات المضمنة. إليك الطريقة:

```csharp
// إنشاء قسم الرأس
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// قم بتعيين رأس الصفحة
page. Header = header;

// قم بإنشاء كائن TextFragment للنص المضمن الأول
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// تحديد لون النص
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// قم بإنشاء كائن صورة للصورة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// ضبط مسار الصورة
image1.File = dataDir + "aspose-logo.jpg";

// تحديد أبعاد الصورة
image1.FixWidth = 50;
image1.FixHeight = 20;

// أشر إلى أن النص المضمن الأول هو صورة
image1.IsInLineParagraph = true;

// قم بإنشاء نص مضمن ثانٍ
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// إضافة عناصر إلى الرأس
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

يقوم الكود أعلاه بإنشاء قسم رأس، وتعيين رأس الصفحة مع هذا القسم، وإضافة TextFragment مع نص مضمن وكائن صورة مضمن.

## الخطوة 4: حفظ مستند PDF المعدل

بمجرد إضافة الرأس الذي يحتوي على الصورة والنص المضمن، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Imageand Page Numberin Header Footersection Inline باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بإنشاء مثيل لكائن مستند عن طريق استدعاء منشئه الفارغ
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// قم بإنشاء صفحة في كائن Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// إنشاء قسم رأس الوثيقة
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// قم بتعيين الرأس لملف PDF
page.Header = header;

// قم بإنشاء كائن نصي
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// تحديد اللون
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// قم بإنشاء كائن صورة في القسم
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// ضبط مسار ملف الصورة
image1.File = dataDir + "aspose-logo.jpg";

// ضبط معلومات عرض الصورة
image1.FixWidth = 50;
image1.FixHeight = 20;

// أشر إلى أن InlineParagraph الخاص بـ seg1 عبارة عن صورة.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// احفظ ملف PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة صورة ورقم صفحة في قسم الرأس والتذييل لمستند PDF باستخدام الفقرات المضمنة مع Aspose.PDF لـ .NET. يمكنك الآن تخصيص رأس وتذييل مستندات PDF الخاصة بك بمرونة.

### الأسئلة الشائعة

#### س: ما هي ميزة استخدام الفقرات المضمنة لإضافة صورة ونص إلى رأس مستند PDF؟

ج: يتيح لك استخدام الفقرات المضمنة دمج الصور والنص بسلاسة داخل الفقرة نفسها، مما يوفر تحكمًا دقيقًا في موضعها وتنسيقها. تعتبر هذه الطريقة مفيدة بشكل خاص لإنشاء رؤوس مخصصة تحتوي على عناصر مرئية.

#### س: كيف يحقق كود مصدر C# المقدم فقرات مضمنة للرأس في مستند PDF؟

ج: يوضح الكود المقدم كيفية إنشاء مستند PDF وإضافة صفحة وتخصيص الرأس باستخدام الفقرات المضمنة. يقوم بإضافة TextFragment مع نص مضمن وصورة مضمنة وTextFragment مضمنة أخرى.

#### س: كيف يمكنني تحديد لون النص المضمن في الرأس؟

 ج: يتم تحديد لون النص المضمن باستخدام`ForegroundColor` ملكية`TextState` التابع`TextFragment` هدف.

#### س: هل يمكنني ضبط أبعاد الصورة المضمنة في الرأس؟

 ج: نعم، يمكنك ضبط أبعاد الصورة المضمنة باستخدام`FixWidth` و`FixHeight` خصائص`Image` هدف. يتيح لك ذلك التحكم في عرض الصورة وارتفاعها داخل الرأس.

#### س: هل يمكنني تضمين عناصر سطرية إضافية، مثل الارتباطات التشعبية أو أنماط الخطوط المختلفة، في الرأس؟

 ج: نعم، يمكنك تضمين عناصر إضافية مضمنة في الرأس عن طريق إنشاء المزيد`TextFragment` أو`Image` الكائنات مع الخصائص المطلوبة. يتيح لك هذا تخصيص الرأس بشكل أكبر، بما في ذلك الارتباطات التشعبية أو أنماط الخطوط المختلفة أو العناصر المرئية الأخرى.

#### س: كيف يمكنني التأكد من أن الصورة والنص المضمنين يظلان محاذيين ومنسقين بشكل صحيح عبر أجهزة وعارضين مختلفين؟

ج: يضمن Aspose.PDF for .NET محاذاة الصور والنصوص المضمنة وتنسيقها بشكل صحيح، مما يؤدي إلى ظهور متسق عبر الأجهزة المختلفة وعارضات PDF.

#### س: هل يمكنني تطبيق الفقرات المضمنة على قسم التذييل أيضًا؟

 ج: نعم، يمكنك تطبيق نفس الأسلوب المتمثل في استخدام الفقرات المضمنة في قسم التذييل عن طريق إنشاء ملف`Footer` كائن وإضافة عناصر مضمنة مثل النص والصور إليه.

#### س: هل من الممكن دمج الفقرات المضمنة مع طرق تخصيص الرأس أو التذييل الأخرى؟

ج: نعم، يمكنك دمج الفقرات المضمنة مع طرق تخصيص الرأس أو التذييل الأخرى التي يوفرها Aspose.PDF لـ .NET لإنشاء تصميمات أكثر تعقيدًا وتخصيصًا للرأس أو التذييل.

#### س: هل يمكنني إزالة العناصر المضمنة أو مسحها من الرأس إذا لزم الأمر؟

 ج: نعم، يمكنك إزالة العناصر المضمنة أو مسحها عن طريق تعديل محتويات الملف`HeaderFooter` كائن وإزالة الفقرات المضمنة المعنية.

#### س: كيف يمكنني تطبيق فقرات مضمنة على صفحات معينة من مستند PDF؟

 ج: لتطبيق فقرات مضمنة على صفحات معينة، يمكنك إنشاء فقرات منفصلة`HeaderFooter` كائنات لكل صفحة وتعيينها باستخدام`Header` ممتلكات المعنيين`Aspose.Pdf.Page` أشياء.