---
title: البحث عن صفحة شرائح النص في ملف PDF
linktitle: البحث عن صفحة شرائح النص في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن أجزاء نصية على صفحة في ملف PDF واسترداد خصائصها باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 470
url: /ar/net/programming-with-text/search-text-segments-page/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن مقاطع نصية محددة على صفحة ملف PDF واسترداد خصائصها. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل متابعة البرنامج التعليمي، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف ما يلي باستخدام التوجيهات في بداية ملف C# الخاص بك لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: قم بتحميل مستند PDF

 قم بتحميل مستند PDF باستخدام`Document` فصل:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 يستبدل`"SearchTextSegmentsPage.pdf"` بالاسم الفعلي لملف PDF الخاص بك.

## الخطوة 5: إنشاء TextFragmentAbsorter

 إنشاء`TextFragmentAbsorber` كائن للعثور على كافة مثيلات عبارة البحث المدخلة:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 يستبدل`"text"` مع عبارة البحث المطلوبة.

## الخطوة 6: قبول الممتص لصفحة معينة

قبول الممتص للصفحة المطلوبة من المستند:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 يستبدل`2` برقم الصفحة المطلوبة (فهرس يعتمد على 1).

## الخطوة 7: استرداد أجزاء النص المستخرجة

 احصل على أجزاء النص المستخرجة باستخدام`TextFragments` ملكية`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 8: قم بالتمرير عبر أجزاء النص

قم بالمراجعة عبر مقاطع النص المستردة والوصول إلى خصائصها:

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

قم بتعديل التعليمات البرمجية داخل الحلقة لتنفيذ المزيد من الإجراءات على كل مقطع نص إذا لزم الأمر.

### نموذج التعليمات البرمجية المصدر لصفحة البحث في مقاطع النص باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// قم بإنشاء كائن TextAbsorter للعثور على كافة مثيلات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// قبول الممتص لجميع الصفحات
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الشظايا
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

تهانينا! لقد تعلمت بنجاح كيفية البحث عن مقاطع نصية محددة في صفحة مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من تحميل المستند وحتى الوصول إلى مقاطع النص المستخرجة. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لإجراء عمليات بحث متقدمة لأجزاء النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث عن صفحات مقاطع النص في ملف PDF"؟

ج: يوفر البرنامج التعليمي "البحث في صفحة شرائح النص في ملف PDF" دليلاً شاملاً حول كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن مقاطع نصية محددة في صفحة معينة من مستند PDF. ويغطي عملية إعداد المشروع، وتحميل مستند PDF، والبحث عن أجزاء النص، واسترداد خصائصها باستخدام كود C#.

#### س: كيف يساعد هذا البرنامج التعليمي في البحث عن أجزاء نصية محددة في مستند PDF؟

ج: يوضح هذا البرنامج التعليمي عملية تحديد موقع مقاطع نصية معينة واستخراجها في صفحة معينة من مستند PDF. باتباع الخطوات ونماذج التعليمات البرمجية المتوفرة، يمكن للمستخدمين البحث بشكل فعال عن مقاطع النص المطلوبة واسترداد المعلومات حول خصائصها.

#### س: ما هي المتطلبات الأساسية المطلوبة لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، تحتاج إلى تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو تثبيته في مشروعك باستخدام NuGet.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET. سيمكنك هذا من الاستفادة من ميزات المكتبة للبحث عن مستندات PDF والعمل معها.

#### س: هل يمكنني استخدام هذا البرنامج التعليمي للبحث عن أجزاء نصية محددة في أي صفحة من ملف PDF؟

ج: نعم، يوفر هذا البرنامج التعليمي إرشادات حول كيفية البحث عن أجزاء نصية محددة في صفحة محددة من مستند PDF. فهو يرشد المستخدمين حول كيفية إعداد مشروع، وتحميل ملف PDF، واستخدام مكتبة Aspose.PDF لتحديد موقع واسترداد خصائص مقاطع النص المطلوبة.

#### س: كيف أحدد النص الذي أريد البحث عنه في هذا البرنامج التعليمي؟

 ج: لتحديد النص الذي تريد البحث عنه، قم بإنشاء ملف`TextFragmentAbsorber` كائن وقم بتعيين معلمة البحث الخاصة به باستخدام`Text` ملكية. استبدل الافتراضي`"text"` في رمز البرنامج التعليمي مع عبارة البحث المطلوبة.

#### س: كيف يمكنني استرجاع خصائص أجزاء النص المستخرجة؟

بعد قبول`TextFragmentAbsorber` بالنسبة لصفحة معينة من ملف PDF، يمكنك استرداد أجزاء النص المستخرجة باستخدام الملف`TextFragments` خاصية الكائن الممتص. يوفر هذا إمكانية الوصول إلى مجموعة من أجزاء النص، تحتوي كل منها على أجزاء نصية متعددة.

#### س: هل يمكنني تخصيص التعليمات البرمجية لتنفيذ إجراءات إضافية على كل مقطع نصي؟

ج: بالتأكيد. يوفر نموذج التعليمة البرمجية للبرنامج التعليمي حلقة للتكرار عبر مقاطع النص المستردة. يمكنك تخصيص التعليمات البرمجية داخل هذه الحلقة لتنفيذ إجراءات إضافية على كل مقطع نص، بناءً على متطلبات مشروعك.

#### س: كيف يمكنني حفظ مستند PDF المعدل بعد استخراج أجزاء النص؟

ج: يركز هذا البرنامج التعليمي بشكل أساسي على البحث عن أجزاء النص واسترداد خصائصها. إذا كنت تنوي إجراء تعديلات على ملف PDF، فيمكنك الرجوع إلى وثائق Aspose.PDF الأخرى لمعرفة كيفية التعامل مع المستند وحفظه بناءً على احتياجاتك الخاصة.