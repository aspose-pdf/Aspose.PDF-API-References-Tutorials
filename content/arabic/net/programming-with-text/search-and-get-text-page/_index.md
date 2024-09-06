---
title: البحث والحصول على صفحة نصية في ملف PDF
linktitle: البحث والحصول على صفحة نصية في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث والحصول على نص من صفحة معينة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 430
url: /ar/net/programming-with-text/search-and-get-text-page/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن نص من صفحة معينة في ملف PDF والحصول عليه. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

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

## الخطوة 3: تحميل مستند PDF

 قم بتعيين المسار إلى دليل مستند PDF الخاص بك وقم بتحميل المستند باستخدام`Document` فصل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 تأكد من الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: البحث عن نص واستخراجه من الصفحة

 إنشاء`TextFragmentAbsorber`كائن للعثور على جميع حالات عبارة البحث المدخلة في صفحة معينة:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 يستبدل`"Figure"` مع النص الفعلي الذي تريد البحث عنه.

## الخطوة 5: البحث في صفحة معينة

قبول الامتصاص لصفحة معينة من المستند:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 6: الحصول على أجزاء نصية مستخرجة

احصل على أجزاء النص المستخرجة باستخدام`TextFragments` ممتلكات`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 7: التنقل عبر أجزاء النص ومقاطعه

قم بالتنقل عبر أجزاء النص getd وأجزاءها، والوصول إلى خصائصها:

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

بإمكانك تعديل الكود داخل الحلقة لأداء إجراءات أخرى على كل جزء من النص.

### عينة من كود المصدر للبحث والحصول على صفحة نصية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// إنشاء كائن TextAbsorber للعثور على جميع حالات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// قبول الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// التنقل عبر الشظايا
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## خاتمة

مبروك! لقد تعلمت بنجاح كيفية البحث والحصول على نص من صفحة معينة من مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من تحميل المستند إلى الوصول إلى أجزاء النص المستخرجة. يمكنك الآن دمج

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "صفحة البحث والحصول على النص"؟

ج: تم تصميم البرنامج التعليمي "البحث والحصول على صفحة نصية" لتوضيح كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن نص واسترجاعه من صفحة معينة داخل ملف PDF. يوفر البرنامج التعليمي تعليمات مفصلة وعينة من كود C# لتوضيح العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في استخراج النص من صفحة معينة في مستند PDF؟

أ: يرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من صفحة معينة من مستند PDF باستخدام مكتبة Aspose.PDF. ويوضح الخطوات اللازمة ويوفر كود C# للبحث عن عبارة نصية محددة في الصفحة المحددة واسترداد أجزاء النص المرتبطة بها.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في هذا البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، يجب أن يكون لديك مكتبة Aspose.PDF for .NET مثبتة. يمكنك الحصول عليها من موقع Aspose على الويب أو استخدام NuGet لدمجها في مشروعك.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF for .NET. سيمكنك هذا من الاستفادة من إمكانيات المكتبة في مشروعك.

#### س: هل يمكنني البحث عن نص في صفحة معينة من مستند PDF؟

ج: نعم، يوضح هذا البرنامج التعليمي كيفية البحث عن نص في صفحة معينة من مستند PDF. ويتضمن ذلك استخدام`TextFragmentAbsorber` فئة لتحديد حالات عبارة نصية معينة على الصفحة المحددة.

#### س: كيف يمكنني الوصول إلى مقاطع النص المستخرجة من الصفحة المحددة؟

 أ: بعد البحث عن النص في الصفحة المحددة، يمكنك الوصول إلى مقاطع النص المستخرجة باستخدام`TextSegments` ممتلكات`TextFragment` الكائن. توفر هذه الخاصية إمكانية الوصول إلى مجموعة من`TextSegment` الكائنات التي تحتوي على النص المستخرج والمعلومات ذات الصلة.

#### س: ما هي المعلومات التي يمكنني استرجاعها من مقاطع النص المستخرجة؟

ج: يمكنك استرداد تفاصيل مختلفة من مقاطع النص المستخرجة، بما في ذلك محتوى النص والموضع (إحداثيات X وY) ومعلومات الخط (الاسم والحجم واللون وما إلى ذلك) والمزيد. يوضح كود العينة الخاص بالبرنامج التعليمي كيفية الوصول إلى هذه التفاصيل وطباعتها لكل مقطع نصي.

#### س: هل يمكنني تنفيذ إجراءات مخصصة على أجزاء النص المستخرجة؟

ج: بالتأكيد. بمجرد استخراج أجزاء النص، يمكنك تخصيص الكود داخل الحلقة لتنفيذ إجراءات إضافية على كل جزء. وقد يتضمن ذلك حفظ النص المستخرج أو تحليل أنماط النص أو تطبيق تغييرات التنسيق.