---
title: الصورة في الرأس
linktitle: الصورة في الرأس
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة صورة في قسم الرأس لمستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 140
url: /ar/net/programming-with-stamps-and-watermarks/image-in-header/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية إضافة صورة في قسم الرأس لمستند PDF باستخدام Aspose.PDF لـ .NET. سوف نستخدم كود مصدر C# المقدم لفتح مستند PDF موجود، وإنشاء مخزن مؤقت للصورة، وتعيين خصائصه، وإضافته إلى جميع صفحات مستند PDF.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF الخاصة بـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF الموجود

الخطوة الأولى هي تحميل مستند PDF الموجود في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند PDF الموجود
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 3: إنشاء الصورة وإضافتها في قسم الرأس

الآن بعد أن تم تحميل مستند PDF، يمكننا إنشاء مخزن مؤقت للصور وإضافته إلى جميع صفحات المستند كقسم رأس. إليك الطريقة:

```csharp
// إنشاء المخزن المؤقت للإطار
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// تعيين خصائص المخزن المؤقت للصورة
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// إضافة المخزن المؤقت للصورة إلى كافة الصفحات
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

يقوم التعليمة البرمجية أعلاه بإنشاء مخزن مؤقت للصورة من ملف "aspose-logo.jpg" وتعيين خصائصه، مثل الهامش العلوي والمحاذاة الأفقية والرأسية. ثم تتم إضافة ختم الصورة إلى جميع صفحات مستند PDF كقسم رأس.

## الخطوة 4: حفظ مستند PDF المعدل

بمجرد إضافة الصورة في قسم الرأس، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Imagein Header باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// إنشاء رأس
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// تعيين خصائص الطوابع
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// إضافة رأس على كافة الصفحات
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة صورة في قسم الرأس لمستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تخصيص رؤوس مستندات PDF الخاصة بك عن طريق إضافة الصور.

### الأسئلة الشائعة للصورة في الرأس

#### س: ما هو الغرض من إضافة صورة في قسم الرأس لمستند PDF؟

ج: تتيح لك إضافة صورة في قسم الرأس لمستند PDF تضمين عناصر مرئية، مثل الشعار أو العلامة التجارية، في أعلى كل صفحة. يمكن أن يؤدي ذلك إلى تحسين الشكل والمظهر العام لمحتوى PDF.

#### س: كيف يمكن للكود المصدري لـ C# المقدم إضافة صورة إلى قسم الرأس في مستند PDF؟

 ج: يوضح الكود المقدم كيفية تحميل مستند PDF موجود، وإنشاء ملف`ImageStamp` كائن من ملف صورة، وقم بتعيين خصائص مثل الهامش العلوي والمحاذاة، ثم قم بإضافة ختم الصورة إلى رأس كل الصفحات.

#### س: هل يمكنني ضبط موضع الصورة ومحاذاتها داخل قسم الرأس؟

 ج: نعم، يمكنك ضبط موضع الصورة ومحاذاتها داخل قسم الرأس عن طريق تعديل خصائص`ImageStamp` هدف. يقوم مقتطف الكود بتعيين خصائص مثل`TopMargin`, `HorizontalAlignment` ، و`VerticalAlignment`.

#### س: هل من الممكن إضافة صور مختلفة إلى قسم الرأس في صفحات مختلفة من مستند PDF؟

 ج: نعم، يمكنك إضافة صور مختلفة إلى قسم الرأس في صفحات مختلفة عن طريق إنشاء صور منفصلة`ImageStamp` كائنات ذات ملفات صور وخصائص مختلفة، ثم إضافتها إلى صفحات محددة.

#### س: كيف يضمن الكود إضافة الصورة إلى جميع صفحات قسم رأس مستند PDF؟

ج: يستخدم الكود المقدم أ`foreach` حلقة للتكرار عبر جميع صفحات مستند PDF وإضافة نفس الشيء`ImageStamp`إلى قسم رأس كل صفحة.

#### س: هل يمكنني إضافة عناصر أخرى، مثل النص أو الأشكال، إلى قسم الرأس باستخدام أسلوب مماثل؟

 ج: نعم، يمكنك إضافة عناصر أخرى مثل النص أو الأشكال إلى قسم الرأس باستخدام أسلوب مماثل عن طريق إنشاء كائنات الطوابع المناسبة (على سبيل المثال،`TextStamp`) وتعيين خصائصها وفقا لذلك.

#### س: كيف أحدد المسار إلى ملف الصورة الذي أريد إضافته إلى الرأس؟

 ج: يتم تحديد المسار إلى ملف الصورة عند إنشاء الملف`ImageStamp` الكائن، كما هو موضح في التعليمات البرمجية. تأكد من توفير المسار الصحيح لملف الصورة.

#### س: هل يمكنني تخصيص حجم الصورة داخل قسم الرأس؟

 ج: نعم، يمكنك تخصيص حجم الصورة داخل قسم الرأس عن طريق ضبط أبعاد الصورة`ImageStamp` باستخدام خصائص مثل`Width` و`Height`.

#### س: هل يمكن إزالة الصورة أو استبدالها في قسم الرأس بعد إضافتها؟

 ج: نعم، يمكنك إزالة الصورة أو استبدالها في قسم الرأس عن طريق تعديل محتويات الملف`ImageStamp` كائن أو إزالة الختم من صفحات محددة.

#### س: كيف يتعامل الكود مع السيناريوهات التي تتجاوز فيها أبعاد الصورة المساحة المتوفرة في الرأس؟

 ج: يقوم الكود بتعيين خصائص مثل`TopMargin`, `HorizontalAlignment` ، و`VerticalAlignment` للتحكم في موضع الصورة ومواءمتها. تأكد من تعديل هذه الخصائص لمنع أي تداخل أو مشكلات في التخطيط.
