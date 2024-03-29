---
title: الصورة ورقم الصفحة في قسم تذييل الرأس
linktitle: الصورة ورقم الصفحة في قسم تذييل الرأس
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة صورة ورقم صفحة في رأس وتذييل مستند PDF باستخدام Aspose.
type: docs
weight: 110
url: /ar/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية إضافة صورة ورقم صفحة في قسم الرأس والتذييل لمستند PDF باستخدام Aspose.PDF لـ .NET. سنوضح لك كيفية استخدام كود مصدر C# لإنشاء صفحة، وتعيين الرأس والتذييل، وإضافة صورة إلى الرأس والنص مع رقم الصفحة لتذييل مستند PDF.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// إنشاء صفحة في المستند
Aspose.Pdf.Page page = doc.Pages.Add();
```

يقوم الكود أعلاه بإنشاء كائن مستند جديد وصفحة فارغة في مستند PDF.

## الخطوة 3: إضافة الرأس مع الصورة

الآن بعد أن تم إنشاء الصفحة، يمكننا إضافة قسم رأس مع صورة. إليك الطريقة:

```csharp
// إنشاء قسم الرأس
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// قم بتعيين رأس الصفحة
page. Header = header;

// إنشاء كائن صورة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// ضبط مسار الصورة
image1.File = dataDir + "aspose-logo.jpg";

// أضف الصورة إلى رأس صفحة مستند PDF
header.Paragraphs.Add(image1);
```

يقوم الكود أعلاه بإنشاء قسم رأس، وتعيين رأس الصفحة مع هذا القسم، وإضافة صورة إلى الرأس.

## الخطوة 4: إضافة تذييل مع رقم الصفحة

الآن وبعد إضافة الرأس، يمكننا إضافة قسم تذييل برقم الصفحة. إليك الطريقة:

```csharp
// إنشاء قسم تذييل
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// حدد تذييل مستند PDF
page. Footer = footer;

// قم بإنشاء كائن TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// أضف النص الذي يحتوي على رقم الصفحة إلى تذييل مستند PDF
footer.Paragraphs.Add(txt);
```

يقوم التعليمة البرمجية أعلاه بإنشاء قسم تذييل، وتعيين تذييل الصفحة مع هذا القسم وإضافة TextFragment الذي يحتوي على النص "الصفحة: ($p of $P )"

  الذي يعرض رقم الصفحة.

## الخطوة 5: حفظ مستند PDF المعدل

بمجرد إضافة الرأس والتذييل، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لقسم تذييلات رأس الصورة ورقم الصفحة باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// قم بإنشاء صفحة في كائن المستند
Aspose.Pdf.Page page = doc.Pages.Add();

// إنشاء قسم رأس الوثيقة
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// قم بتعيين الرأس لملف PDF
page.Header = header;

// قم بإنشاء كائن صورة في الصفحة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// ضبط مسار ملف الصورة
image1.File = dataDir + "aspose-logo.jpg";

// إضافة صورة إلى الصفحة الرئيسية لملف Pdf
header.Paragraphs.Add(image1);

//قم بإنشاء قسم تذييل للمستند
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// قم بتعيين تذييل ملف PDF
page.Footer = footer;

// قم بإنشاء كائن نصي
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// أضف نصًا إلى قسم الرأس في ملف Pdf
footer.Paragraphs.Add(txt);

// احفظ ملف PDF
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة صورة ورقم صفحة في قسم الرأس والتذييل لمستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه الطريقة لتخصيص الرأس والتذييل في مستندات PDF الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو الغرض من إضافة صورة ورقم الصفحة في قسم الرأس والتذييل لمستند PDF؟

ج: يمكن أن تؤدي إضافة صورة ورقم صفحة في قسم الرأس والتذييل لمستند PDF إلى تحسين جاذبيته المرئية وعلامته التجارية وعناصر التنقل. يمكن أن تمثل الصورة شعارًا أو علامة مائية أو أي عنصر رسومي، بينما يساعد رقم الصفحة المستخدمين على تتبع تقدمهم وتحديد صفحات معينة.

#### س: كيف يساعد كود مصدر C# المقدم في إضافة صورة ورقم صفحة إلى رأس وتذييل مستند PDF؟

ج: يوضح الكود المقدم كيفية إنشاء مستند PDF، وإضافة صفحة، ثم تخصيص أقسام الرأس والتذييل. يوضح كيفية إضافة صورة إلى الرأس وجزء نصي مع ترقيم الصفحات في التذييل.

#### س: هل يمكنني استخدام أي تنسيق صورة للرأس، وكيف أحدد مساره؟

 ج: نعم، يمكنك استخدام تنسيقات صور مختلفة (مثل JPEG وPNG وGIF وما إلى ذلك) لصورة الرأس. يتم تحديد مسار الصورة باستخدام`File` ملكية`Aspose.Pdf.Image` هدف.

#### س: كيف يمكنني تخصيص مظهر الصورة وموضعها في قسم الرأس؟

 ج: يمكنك تخصيص مظهر الصورة وموضعها عن طريق ضبط خصائص الصورة`Aspose.Pdf.Image` الكائن قبل إضافته إلى قسم الرأس. على سبيل المثال، يمكنك ضبط أبعاد الصورة، والمحاذاة، والتدوير، والتعتيم، وما إلى ذلك.

####  س: ما هو الغرض من`TextFragment` object used for the footer?

 ج: ال`TextFragment` يتم استخدام الكائن لإنشاء وتنسيق النص الذي سيتم عرضه في قسم التذييل. وفي الكود المقدم، يتم استخدامه لعرض رقم الصفحة وإجمالي عدد الصفحات.

#### س: هل يمكنني تعديل نص التذييل ليشمل معلومات إضافية أو تنسيقًا؟

 ج: نعم، يمكنك تعديل نص التذييل عن طريق تعديل محتويات الملف`TextFragment` هدف. يمكنك إضافة نص إضافي وتغيير الخطوط والألوان والتنسيق وفقًا لمتطلباتك.

#### س: هل يمكنني تطبيق محتويات مختلفة للرأس والتذييل على صفحات مختلفة من مستند PDF؟

 ج: نعم، يمكنك تطبيق محتويات مختلفة للرأس والتذييل على صفحات مختلفة عن طريق إنشاء صفحات منفصلة`HeaderFooter` الكائنات وتخصيصها لصفحات محددة باستخدام`Header` و`Footer` خصائص`Aspose.Pdf.Page` هدف.

#### س: كيف يمكنني تخصيص الرأس والتذييل بشكل أكبر، مثل تغيير أنماط الخطوط أو إضافة عناصر إضافية؟

ج: يمكنك تخصيص الرأس والتذييل باستخدام الفئات والخصائص المتنوعة التي يوفرها Aspose.PDF لـ .NET. على سبيل المثال، يمكنك استخدام خيارات مختلفة لتنسيق النص، أو إضافة المزيد من الفقرات، أو الصور، أو حتى الجداول إلى أقسام الرأس والتذييل.

#### س: هل يمكنني إزالة أو مسح أقسام الرأس والتذييل إذا لزم الأمر؟

ج: نعم، يمكنك إزالة أو مسح أقسام الرأس والتذييل عن طريق تعيين`Header` و`Footer` خصائص`Aspose.Pdf.Page` يعترض على`null`.

#### س: كيف يمكنني التأكد من أن الصورة المضافة ورقم الصفحة يظلان متسقين عبر الأجهزة والمشاهدين المختلفين؟

ج: يوفر Aspose.PDF for .NET وظيفة لإنشاء مستندات PDF موحدة ومتسقة، مما يضمن ظهور الصورة المضافة ورقم الصفحة بشكل متسق عبر الأجهزة المختلفة وعارضات PDF.