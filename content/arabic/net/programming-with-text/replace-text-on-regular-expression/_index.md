---
title: استبدال النص في تعبير عادي في ملف PDF
linktitle: استبدال تعبير Texton العادي في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استبدال النص بناءً على تعبير منتظم في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 360
url: /ar/net/programming-with-text/replace-text-on-regular-expression/
---
في هذا البرنامج التعليمي، سنشرح كيفية استبدال النص بناءً على تعبير عادي في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. وسنقدم دليلًا خطوة بخطوة مع الكود المصدري C# اللازم.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 قم بتعيين المسار إلى الدليل الذي يوجد به ملف PDF المدخل. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل مستند PDF

 قم بتحميل مستند PDF باستخدام`Document` الفئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## الخطوة 3: البحث عن النص واستبداله باستخدام التعبيرات العادية

 إنشاء`TextFragmentAbsorber` حدد نمط التعبير العادي للعثور على جميع العبارات المطابقة للنمط. اضبط خيار البحث النصي لتمكين استخدام التعبير العادي.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## الخطوة 4: استبدال النص

قم بالتنقل عبر أجزاء النص المستخرجة واستبدال النص حسب الحاجة. قم بتحديث النص والخصائص الأخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

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

## الخطوة 5: احفظ ملف PDF المعدّل

احفظ مستند PDF المعدّل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### عينة من كود المصدر لاستبدال تعبير Texton العادي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// إنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
// تعيين خيار البحث النصي لتحديد استخدام التعبيرات العادية
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// تقبل الممتص لصفحة واحدة
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// التنقل عبر الشظايا
foreach (TextFragment textFragment in textFragmentCollection)
{
	// تحديث النص والخصائص الأخرى
	textFragment.Text = "New Phrase";
	// تم تعيينه إلى مثيل للكائن.
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

في هذا البرنامج التعليمي، تعلمت كيفية استبدال نص بناءً على تعبير عادي في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك تحميل مستند PDF والبحث عن نص باستخدام تعبير عادي واستبداله وحفظ ملف PDF المعدل.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "استبدال النص في التعبير العادي في ملف PDF"؟

أ: يهدف البرنامج التعليمي "استبدال النص في تعبير عادي في ملف PDF" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن نص واستبداله في مستند PDF استنادًا إلى تعبير عادي. وهو يوفر دليلًا خطوة بخطوة مع عينة من التعليمات البرمجية بلغة C#.

#### س: لماذا أرغب في استخدام تعبير عادي لاستبدال النص في مستند PDF؟

أ: يتيح لك استخدام التعبيرات العادية البحث عن أنماط النص التي تتبع تنسيقًا معينًا واستبدالها، مما يجعلها طريقة فعّالة للتعامل مع المحتوى. يُعد هذا النهج مفيدًا بشكل خاص عندما تحتاج إلى استبدال نص يتطابق مع نمط أو بنية معينة عبر مستند PDF.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي يوجد به ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني استبدال النص بناءً على تعبير منتظم في مستند PDF؟

أ: يرشدك البرنامج التعليمي خلال الخطوات التالية:

1.  قم بتحميل مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` الكائن وحدد نمط التعبير العادي للعثور على العبارات المطابقة للنمط. اضبط خيار البحث النصي لتمكين استخدام التعبير العادي.
3. قم بالتنقل عبر أجزاء النص المستخرجة واستبدال النص. قم بتحديث خصائص أخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية حسب الحاجة.
4. احفظ مستند PDF المعدّل.

#### س: هل يمكنني استبدال النص باستخدام التعبيرات العادية المعقدة؟

ج: نعم، يمكنك استخدام تعبيرات منتظمة معقدة لمطابقة واستبدال النص في مستند PDF. توفر التعبيرات المنتظمة طريقة مرنة لتحديد أنماط أو هياكل معينة في النص.

####  س: ما هو الغرض من`TextSearchOptions` class in the tutorial?

 أ: ال`TextSearchOptions`تتيح لك الفئة تحديد خيارات البحث عن النص، مثل تمكين استخدام التعبيرات العادية عند البحث عن أجزاء نصية. في البرنامج التعليمي، يتم استخدامها لتمكين وضع التعبيرات العادية لـ`TextFragmentAbsorber`.

#### س: هل استبدال الخط اختياري عند استخدام التعبيرات العادية لاستبدال النص؟

ج: نعم، يعد استبدال الخط اختياريًا عند استخدام التعبيرات العادية لاستبدال النص. إذا لم تحدد خطًا جديدًا، فسيحتفظ النص بخط جزء النص الأصلي.

#### س: كيف يمكنني استبدال النص في صفحات متعددة باستخدام تعبير عادي؟

ج: يمكنك تعديل الحلقة عبر أجزاء النص لتشمل جميع صفحات مستند PDF، على غرار مثال البرنامج التعليمي. بهذه الطريقة، يمكنك استبدال النص في صفحات متعددة بناءً على نمط التعبيرات العادية.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، ستستبدل النص في مستند PDF الذي يطابق نمط التعبيرات العادية المحدد. سيحتوي النص المستبدل على الخصائص التي حددتها، مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

#### س: هل يمكنني استخدام هذا النهج لاستبدال النص ذي التنسيق المعقد؟

ج: نعم، يمكنك تخصيص تنسيق النص المستبدل من خلال تحديث خصائص مثل الخط وحجم الخط ولون المقدمة ولون الخلفية. يتيح لك هذا الحفاظ على التنسيق أو تعديله حسب الحاجة.