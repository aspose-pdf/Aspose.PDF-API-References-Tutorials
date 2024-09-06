---
title: البحث عن أجزاء النص في صفحة ملف PDF
linktitle: البحث عن أجزاء النص في صفحة ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث عن أجزاء نصية على صفحة في ملف PDF واسترجاع خصائصها باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 470
url: /ar/net/programming-with-text/search-text-segments-page/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن أجزاء نصية معينة على صفحة من ملف PDF واسترداد خصائصها. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل المتابعة بالبرنامج التعليمي، تأكد من توفر ما يلي:

- المعرفة الأساسية للغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك الحصول عليها من موقع Aspose على الويب أو استخدام NuGet لتثبيتها في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات الأساسية الضرورية

أضف التوجيهات التالية في بداية ملف C# الخاص بك لاستيراد المساحات المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: تعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: تحميل مستند PDF

 قم بتحميل مستند PDF باستخدام`Document` فصل:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 يستبدل`"SearchTextSegmentsPage.pdf"` مع الاسم الفعلي لملف PDF الخاص بك.

## الخطوة 5: إنشاء TextFragmentAbsorber

 إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات عبارة البحث المدخلة:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 يستبدل`"text"` مع عبارة البحث المطلوبة.

## الخطوة 6: قبول الممتص لصفحة معينة

اقبل الممتص للصفحة المطلوبة من المستند:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 يستبدل`2` مع رقم الصفحة المطلوب (فهرس يعتمد على 1).

## الخطوة 7: استرداد أجزاء النص المستخرجة

 احصل على مقاطع النص المستخرجة باستخدام`TextFragments` ممتلكات`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 8: التنقل عبر أجزاء النص

قم بالتنقل عبر أجزاء النص المسترجعة والوصول إلى خصائصها:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

قم بتعديل الكود الموجود داخل الحلقة لأداء إجراءات أخرى على كل جزء من النص إذا لزم الأمر.

### عينة من كود المصدر لصفحة البحث عن أجزاء النص باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// إنشاء كائن TextAbsorber للعثور على جميع حالات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// قبول الممتص لجميع الصفحات
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// التنقل عبر الشظايا
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## خاتمة

مبروك! لقد تعلمت بنجاح كيفية البحث عن مقاطع نصية محددة على صفحة من مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من تحميل المستند إلى الوصول إلى مقاطع النص المستخرجة. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك لإجراء عمليات بحث متقدمة عن مقاطع النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "صفحة البحث عن أجزاء النص في ملف PDF"؟

ج: يوفر البرنامج التعليمي "بحث عن أجزاء نصية في صفحة ملف PDF" دليلاً شاملاً حول كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن أجزاء نصية محددة في صفحة معينة من مستند PDF. ويغطي عملية إعداد مشروع، وتحميل مستند PDF، والبحث عن أجزاء نصية، واسترداد خصائصها باستخدام كود C#.

#### س: كيف يساعد هذا البرنامج التعليمي في البحث عن أجزاء نصية محددة في مستند PDF؟

أ: يوضح هذا البرنامج التعليمي عملية تحديد واستخراج أجزاء نصية معينة على صفحة معينة من مستند PDF. باتباع الخطوات وعينات التعليمات البرمجية المقدمة، يمكن للمستخدمين البحث بفعالية عن أجزاء النص المطلوبة واسترجاع المعلومات حول خصائصها.

#### س: ما هي المتطلبات الأساسية المطلوبة لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، يجب أن يكون لديك مكتبة Aspose.PDF for .NET مثبتة. يمكنك الحصول عليها من موقع Aspose على الويب أو تثبيتها في مشروعك باستخدام NuGet.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF for .NET. سيمكنك هذا من الاستفادة من ميزات المكتبة للبحث عن مستندات PDF والعمل عليها.

#### س: هل يمكنني استخدام هذا البرنامج التعليمي للبحث عن أجزاء نصية محددة على أي صفحة من ملف PDF؟

ج: نعم، يوفر هذا البرنامج التعليمي إرشادات حول كيفية البحث عن مقاطع نصية محددة في صفحة محددة من مستند PDF. وهو يرشد المستخدمين إلى إعداد مشروع وتحميل ملف PDF واستخدام مكتبة Aspose.PDF لتحديد خصائص مقاطع النص المطلوبة واسترجاعها.

#### س: كيف أحدد النص الذي أريد البحث عنه في هذا البرنامج التعليمي؟

 أ: لتحديد النص الذي تريد البحث عنه، قم بإنشاء`TextFragmentAbsorber` الكائن وتعيين معلمة البحث الخاصة به باستخدام`Text` الملكية. استبدال الافتراضي`"text"` في كود البرنامج التعليمي مع عبارة البحث المطلوبة.

#### س: كيف يمكنني استرجاع خصائص أجزاء النص المستخرجة؟

بعد قبول`TextFragmentAbsorber` بالنسبة لصفحة معينة من ملف PDF، يمكنك استرداد أجزاء النص المستخرجة باستخدام`TextFragments` خاصية كائن الامتصاص. يوفر هذا إمكانية الوصول إلى مجموعة من أجزاء النص، كل منها يحتوي على أجزاء نصية متعددة.

#### س: هل يمكنني تخصيص الكود لأداء إجراءات إضافية على كل جزء من النص؟

ج: بالتأكيد. يوفر الكود النموذجي للبرنامج التعليمي حلقة للتكرار عبر مقاطع النص المسترجعة. يمكنك تخصيص الكود داخل هذه الحلقة لأداء إجراءات إضافية على كل مقطع نصي، بناءً على متطلبات مشروعك.

#### س: كيف يمكنني حفظ مستند PDF المعدل بعد استخراج أجزاء النص؟

ج: يركز هذا البرنامج التعليمي بشكل أساسي على البحث عن أجزاء النص واسترجاع خصائصها. إذا كنت تنوي إجراء تعديلات على ملف PDF، فيمكنك الرجوع إلى وثائق Aspose.PDF الأخرى لمعرفة كيفية التعامل مع المستند وحفظه بناءً على احتياجاتك المحددة.