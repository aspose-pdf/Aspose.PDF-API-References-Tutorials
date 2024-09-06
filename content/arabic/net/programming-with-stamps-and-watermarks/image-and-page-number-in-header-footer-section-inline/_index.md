---
title: الصورة ورقم الصفحة في قسم التذييل والرأس مضمنًا
linktitle: الصورة ورقم الصفحة في قسم التذييل والرأس مضمنًا
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة صورة ورقم الصفحة في الرأس والتذييل باستخدام الفقرات المضمنة مع Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية إضافة صورة ورقم صفحة في قسم الرأس والتذييل في مستند PDF باستخدام Aspose.PDF for .NET. سنستخدم كود المصدر C# المقدم لإنشاء صفحة وتعيين الرأس والتذييل وإضافة صورة ونص باستخدام فقرات مضمنة في رأس مستند PDF.

## الخطوة 1: إعداد البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: إنشاء مستند PDF والصفحة

الخطوة الأولى هي إنشاء كائن مستند جديد وصفحة في مستند PDF. وإليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن مستند جديد
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// إنشاء صفحة في المستند
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

يقوم الكود أعلاه بإنشاء كائن مستند جديد وصفحة فارغة في مستند PDF.

## الخطوة 3: إضافة العنوان مع صورة ونص مضمن

الآن بعد إنشاء الصفحة، يمكننا إضافة قسم رأس الصفحة مع صورة ونص باستخدام فقرات مضمنة. وإليك الطريقة:

```csharp
// إنشاء قسم رأس الصفحة
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// تعيين رأس الصفحة
page. Header = header;

// إنشاء كائن TextFragment للنص المضمن الأول
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// تحديد لون النص
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// إنشاء كائن صورة للصورة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// تعيين مسار الصورة
image1.File = dataDir + "aspose-logo.jpg";

// تحديد أبعاد الصورة
image1.FixWidth = 50;
image1.FixHeight = 20;

// أشر إلى أن النص المضمن الأول عبارة عن صورة
image1.IsInLineParagraph = true;

// إنشاء نص مضمن ثانٍ
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// إضافة عناصر إلى الرأس
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

يقوم الكود أعلاه بإنشاء قسم رأس الصفحة، ويحدد رأس الصفحة بهذا القسم، ويضيف TextFragment مع نص مضمن وكائن صورة مضمن.

## الخطوة 4: حفظ مستند PDF المعدل

بمجرد إضافة العنوان الذي يحتوي على الصورة والنص المضمن، يمكننا حفظ مستند PDF المعدّل. إليك الطريقة:

```csharp
// حفظ مستند PDF المعدل
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

يقوم الكود أعلاه بحفظ مستند PDF المحرر في الدليل المحدد.

### عينة من كود المصدر للصورة ورقم الصفحة في قسم الرأس والتذييل المضمن باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند عن طريق استدعاء المنشئ الفارغ الخاص به
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// إنشاء صفحة في كائن Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// إنشاء قسم رأس المستند
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// تعيين رأس ملف PDF
page.Header = header;

// إنشاء كائن نصي
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// حدد اللون
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// إنشاء كائن صورة في القسم
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// تعيين مسار ملف الصورة
image1.File = dataDir + "aspose-logo.jpg";

//تعيين معلومات عرض الصورة
image1.FixWidth = 50;
image1.FixHeight = 20;

// تشير إلى أن InlineParagraph في seg1 عبارة عن صورة.
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

تهانينا! لقد تعلمت كيفية إضافة صورة ورقم صفحة في قسم الرأس والتذييل في مستند PDF باستخدام فقرات مضمنة باستخدام Aspose.PDF لـ .NET. يمكنك الآن تخصيص الرأس والتذييل لمستندات PDF الخاصة بك بمرونة.

### الأسئلة الشائعة

#### س: ما هي فائدة استخدام الفقرات المضمنة لإضافة صورة ونص إلى رأس مستند PDF؟

أ: يتيح لك استخدام الفقرات المضمنة دمج الصور والنصوص بسلاسة داخل الفقرة نفسها، مما يوفر تحكمًا دقيقًا في وضعها وتنسيقها. هذه الطريقة مفيدة بشكل خاص لإنشاء عناوين مخصصة بعناصر مرئية.

#### س: كيف يعمل كود المصدر C# المقدم على تحقيق فقرات مضمنة للرأس في مستند PDF؟

ج: يوضح الكود المقدم كيفية إنشاء مستند PDF وإضافة صفحة وتخصيص الرأس باستخدام فقرات مضمنة. فهو يضيف TextFragment بنص مضمن وصورة مضمنة وTextFragment مضمن آخر.

#### س: كيف يمكنني تحديد لون النص المضمن في العنوان؟

 أ: يتم تحديد لون النص المضمن باستخدام`ForegroundColor` ممتلكات`TextState` التابع`TextFragment` هدف.

#### س: هل يمكنني تعديل أبعاد الصورة المضمنة في العنوان؟

 ج: نعم، يمكنك تعديل أبعاد الصورة المضمنة باستخدام`FixWidth` و`FixHeight` خصائص`Image` الكائن. يتيح لك هذا التحكم في عرض وارتفاع الصورة داخل الرأس.

#### س: هل يمكنني تضمين عناصر مضمنة إضافية، مثل الارتباطات التشعبية أو أنماط الخطوط المختلفة، في العنوان؟

 ج: نعم، يمكنك تضمين عناصر مضمنة إضافية في الرأس من خلال إنشاء المزيد`TextFragment` أو`Image` الكائنات ذات الخصائص المطلوبة. يتيح لك هذا تخصيص الرأس بشكل أكبر، بما في ذلك الارتباطات التشعبية أو أنماط الخطوط المختلفة أو العناصر المرئية الأخرى.

#### س: كيف يمكنني التأكد من أن الصورة والنص المضمنين يظلان محاذيين ومنسقين بشكل صحيح عبر الأجهزة والمشاهدين المختلفة؟

أ: يضمن Aspose.PDF لـ .NET محاذاة وتنسيق الصور والنصوص المضمنة بشكل صحيح، مما يؤدي إلى ظهور متناسق عبر الأجهزة المختلفة وعارضات PDF.

#### س: هل يمكنني تطبيق الفقرات المضمنة على قسم التذييل أيضًا؟

 ج: نعم، يمكنك تطبيق نفس تقنية استخدام الفقرات المضمنة على قسم التذييل عن طريق إنشاء`Footer` الكائن وإضافة عناصر مضمنة إليه مثل النص والصور.

#### س: هل من الممكن دمج الفقرات المضمنة مع طرق تخصيص الرأس أو التذييل الأخرى؟

ج: نعم، يمكنك دمج الفقرات المضمنة مع طرق تخصيص الرأس أو التذييل الأخرى التي يوفرها Aspose.PDF لـ .NET لإنشاء تصميمات رأس أو تذييل أكثر تعقيدًا وتخصيصًا.

#### س: هل يمكنني إزالة أو مسح العناصر المضمنة من الرأس إذا لزم الأمر؟

 ج: نعم، يمكنك إزالة العناصر المضمنة أو مسحها عن طريق تعديل محتويات`HeaderFooter`الكائن وإزالة الفقرات المضمنة ذات الصلة.

#### س: كيف يمكنني تطبيق الفقرات المضمنة على صفحات محددة من مستند PDF؟

 أ: لتطبيق الفقرات المضمنة على صفحات معينة، يمكنك إنشاء فقرات منفصلة`HeaderFooter` الكائنات لكل صفحة وتعيينها باستخدام`Header` ممتلكات المعنيين`Aspose.Pdf.Page` أشياء.