---
title: استبدال النص على التعبير العادي في ملف PDF
linktitle: استبدال التعبير العادي Texton في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال النص بناءً على تعبير عادي في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 360
url: /ar/net/programming-with-text/replace-text-on-regular-expression/
---
سنشرح في هذا البرنامج التعليمي كيفية استبدال النص بناءً على تعبير عادي في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنقدم دليلًا خطوة بخطوة بالإضافة إلى كود مصدر C# الضروري.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- الفهم الأساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 قم بتعيين المسار إلى الدليل حيث يوجد ملف PDF المدخل. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 قم بتحميل مستند PDF باستخدام`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## الخطوة 3: البحث عن النص واستبداله باستخدام التعبير العادي

 إنشاء`TextFragmentAbsorber` كائن وحدد نمط التعبير العادي للعثور على جميع العبارات المطابقة للنمط. قم بتعيين خيار البحث عن النص لتمكين استخدام التعبير العادي.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## الخطوة 4: استبدال النص

قم بالمراجعة خلال أجزاء النص المستخرجة واستبدل النص كما هو مطلوب. قم بتحديث النص والخصائص الأخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## الخطوة 5: احفظ ملف PDF المعدل

احفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لاستبدال Texton Regular Expression باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// قم بإنشاء كائن TextAbsorter للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
// قم بتعيين خيار البحث عن النص لتحديد استخدام التعبير العادي
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// قبول الممتص لصفحة واحدة
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الشظايا
foreach (TextFragment textFragment in textFragmentCollection)
{
	// تحديث النص والخصائص الأخرى
	textFragment.Text = "New Phrase";
	// تعيين إلى مثيل كائن.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية استبدال النص بناءً على تعبير عادي في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك تحميل مستند PDF والبحث عن نص باستخدام تعبير عادي واستبداله وحفظ ملف PDF المعدل.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "استبدال النص في التعبير العادي في ملف PDF"؟

ج: يهدف البرنامج التعليمي "استبدال النص في التعبير العادي في ملف PDF" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن النص واستبداله في مستند PDF استنادًا إلى التعبير العادي. فهو يوفر دليلاً خطوة بخطوة مع نموذج كود C#.

#### س: لماذا أرغب في استخدام تعبير عادي لاستبدال النص في مستند PDF؟

ج: يتيح لك استخدام التعبيرات العادية البحث عن أنماط النص التي تتبع تنسيقًا معينًا واستبدالها، مما يجعلها وسيلة فعالة للتعامل مع المحتوى. يعد هذا الأسلوب مفيدًا بشكل خاص عندما تحتاج إلى استبدال النص الذي يطابق نمطًا أو بنية معينة عبر مستند PDF.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل حيث يوجد ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني استبدال النص بناءً على تعبير عادي في مستند PDF؟

ج: يرشدك البرنامج التعليمي خلال الخطوات التالية:

1.  قم بتحميل مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` كائن وحدد نمط التعبير العادي للعثور على العبارات المطابقة للنمط. قم بتعيين خيار البحث عن النص لتمكين استخدام التعبير العادي.
3. قم بالمرور عبر أجزاء النص المستخرجة واستبدل النص. قم بتحديث الخصائص الأخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية كما هو مطلوب.
4. احفظ مستند PDF المعدل.

#### س: هل يمكنني استبدال النص باستخدام تعبيرات عادية معقدة؟

ج: نعم، يمكنك استخدام التعبيرات العادية المعقدة لمطابقة النص في مستند PDF واستبداله. توفر التعبيرات العادية طريقة مرنة لتحديد أنماط أو بنيات معينة في النص.

####  س: ما هو الغرض من`TextSearchOptions` class in the tutorial?

 ج: ال`TextSearchOptions`تتيح لك الفئة تحديد خيارات البحث عن النص، مثل تمكين استخدام التعبير العادي عند البحث عن أجزاء النص. في البرنامج التعليمي، يتم استخدامه لتمكين وضع التعبير العادي لـ`TextFragmentAbsorber`.

#### س: هل استبدال الخط اختياري عند استخدام التعبيرات العادية لاستبدال النص؟

ج: نعم، يعد استبدال الخط أمرًا اختياريًا عند استخدام التعبيرات العادية لاستبدال النص. إذا لم تحدد خطًا جديدًا، فسيحتفظ النص بخط جزء النص الأصلي.

#### س: كيف يمكنني استبدال النص في صفحات متعددة باستخدام تعبير عادي؟

ج: يمكنك تعديل الحلقة عبر أجزاء النص لتشمل جميع صفحات مستند PDF، على غرار المثال التعليمي. بهذه الطريقة، يمكنك استبدال النص في صفحات متعددة بناءً على نمط التعبير العادي.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، سوف تقوم باستبدال النص في مستند PDF الذي يتطابق مع نمط التعبير العادي المحدد. سيكون للنص المستبدل الخصائص التي حددتها، مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

#### س: هل يمكنني استخدام هذا الأسلوب لاستبدال النص بتنسيق معقد؟

ج: نعم، يمكنك تخصيص تنسيق النص المستبدل عن طريق تحديث خصائص مثل الخط وحجم الخط ولون المقدمة ولون الخلفية. يتيح لك ذلك الحفاظ على التنسيق أو تعديله حسب الحاجة.