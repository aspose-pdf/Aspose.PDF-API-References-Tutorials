---
title: البحث والحصول على صفحة نصية في ملف PDF
linktitle: البحث والحصول على صفحة نصية في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن نص والحصول عليه من صفحة معينة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 430
url: /ar/net/programming-with-text/search-and-get-text-page/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث والحصول على نص من صفحة معينة في ملف PDF. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

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

## الخطوة 3: قم بتحميل مستند PDF

 قم بتعيين المسار إلى دليل مستند PDF الخاص بك وقم بتحميل المستند باستخدام ملف`Document` فصل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: البحث واستخراج النص من الصفحة

 إنشاء`TextFragmentAbsorber`كائن للعثور على كافة مثيلات عبارة البحث المدخلة في صفحة معينة:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 يستبدل`"Figure"` بالنص الفعلي الذي تريد البحث عنه.

## الخطوة 5: البحث في صفحة معينة

قبول الممتص لصفحة معينة من المستند:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 6: الحصول على أجزاء النص المستخرجة

احصل على أجزاء النص المستخرجة باستخدام`TextFragments` ملكية`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 7: قم بالتمرير عبر أجزاء وأجزاء النص

قم بالمراجعة عبر أجزاء النص التي تم الحصول عليها وأجزاءها، وقم بالوصول إلى خصائصها:

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

يمكنك تعديل التعليمات البرمجية داخل الحلقة لتنفيذ المزيد من الإجراءات على كل مقطع نص.

### نموذج التعليمات البرمجية المصدر للبحث والحصول على صفحة نصية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// قم بإنشاء كائن TextAbsorter للعثور على كافة مثيلات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// قبول الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الشظايا
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

تهانينا! لقد تعلمت بنجاح كيفية البحث عن نص والحصول عليه من صفحة محددة في مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من تحميل المستند وحتى الوصول إلى مقاطع النص المستخرجة. يمكنك الآن دمج

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث والحصول على صفحة نصية"؟

ج: تم تصميم البرنامج التعليمي "البحث والحصول على صفحة نصية" لتوضيح كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن النص واسترداده من صفحة معينة داخل ملف PDF. يوفر البرنامج التعليمي تعليمات مفصلة ونموذج كود C# لتوضيح العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في استخراج النص من صفحة معينة في مستند PDF؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من صفحة معينة من مستند PDF باستخدام مكتبة Aspose.PDF. فهو يوضح الخطوات اللازمة ويوفر رمز C# للبحث عن عبارة نصية محددة في الصفحة المحددة واسترداد مقاطع النص المرتبطة بها.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء بهذا البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، تحتاج إلى تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لدمجه في مشروعك.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET. سيمكنك هذا من الاستفادة من إمكانيات المكتبة في مشروعك.

#### س: هل يمكنني البحث عن نص في صفحة معينة من مستند PDF؟

ج: نعم، يوضح هذا البرنامج التعليمي كيفية البحث عن نص في صفحة معينة من مستند PDF. أنها تنطوي على استخدام`TextFragmentAbsorber` فئة لتحديد مثيلات عبارة نصية معينة على الصفحة المختارة.

#### س: كيف يمكنني الوصول إلى مقاطع النص المستخرجة من صفحة معينة؟

 ج: بعد البحث عن النص في الصفحة المخصصة، يمكنك الوصول إلى مقاطع النص المستخرجة باستخدام`TextSegments` ملكية`TextFragment` هدف. توفر هذه الخاصية الوصول إلى مجموعة من`TextSegment` الكائنات التي تحتوي على النص المستخرج والمعلومات ذات الصلة.

#### س: ما هي المعلومات التي يمكنني استرجاعها من مقاطع النص المستخرجة؟

ج: يمكنك استرداد تفاصيل متنوعة من مقاطع النص المستخرجة، بما في ذلك محتوى النص والموضع (إحداثيات X وY) ومعلومات الخط (الاسم والحجم واللون وما إلى ذلك)، والمزيد. يوضح نموذج التعليمات البرمجية الخاص بالبرنامج التعليمي كيفية الوصول إلى هذه التفاصيل وطباعتها لكل مقطع نصي.

#### س: هل يمكنني تنفيذ إجراءات مخصصة على مقاطع النص المستخرجة؟

ج: بالتأكيد. بمجرد حصولك على مقاطع النص المستخرجة، يمكنك تخصيص التعليمات البرمجية داخل الحلقة لتنفيذ إجراءات إضافية على كل مقطع. يمكن أن يشمل ذلك حفظ النص المستخرج، أو تحليل أنماط النص، أو تطبيق تغييرات التنسيق.