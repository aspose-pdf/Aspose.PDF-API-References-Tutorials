---
title: إعادة ترتيب المحتويات باستخدام استبدال النص
linktitle: إعادة ترتيب المحتويات باستخدام استبدال النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إعادة ترتيب المحتويات في مستند PDF باستخدام استبدال النص باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 270
url: /ar/net/programming-with-text/rearrange-contents-using-text-replacement/
---
في هذا البرنامج التعليمي، سنشرح كيفية إعادة ترتيب المحتويات في مستند PDF باستخدام استبدال النص مع مكتبة Aspose.PDF لـ .NET. سنتابع عملية تحميل ملف PDF خطوة بخطوة، والبحث عن أجزاء نصية محددة، واستبدال النص، وحفظ ملف PDF المعدل باستخدام كود مصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي توجد به ملفات PDF الخاصة بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملفات PDF الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل ملف PDF المصدر

 بعد ذلك، نقوم بتحميل مستند PDF المصدر باستخدام الملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## الخطوة 3: البحث عن أجزاء النص واستبدالها

 نقوم بإنشاء أ`TextFragmentAbsorber` كائن بتعبير عادي للبحث عن أجزاء نصية محددة. بعد ذلك، نقوم بمراجعة أجزاء النص، وتخصيص الخط والحجم واللون واستبدال النص.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## الخطوة 4: احفظ ملف PDF المعدل

وأخيرًا، نقوم بحفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لإعادة ترتيب المحتويات باستخدام استبدال النص باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// تحميل ملف PDF المصدر
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// إنشاء كائن TextFragment Absorter بتعبير عادي
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// استبدل كل TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// تعيين خط جزء النص الذي سيتم استبداله
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// ضبط حجم الخط
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// استبدل النص بسلسلة أكبر من العنصر النائب
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// حفظ ملف PDF الناتج
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إعادة ترتيب المحتويات في مستند PDF باستخدام استبدال النص مع مكتبة Aspose.PDF لـ .NET. باتباع الدليل التفصيلي وتنفيذ كود C# المقدم، يمكنك البحث عن أجزاء نصية محددة وتخصيص مظهرها واستبدال النص في مستند PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "إعادة ترتيب المحتويات باستخدام استبدال النص"؟

ج: يوضح البرنامج التعليمي "إعادة ترتيب المحتويات باستخدام استبدال النص" كيفية استخدام مكتبة Aspose.PDF لـ .NET لإعادة ترتيب المحتويات في مستند PDF عن طريق إجراء استبدال النص. يوفر البرنامج التعليمي دليلاً خطوة بخطوة وكود مصدر C# لمساعدتك في تحميل ملف PDF والبحث عن أجزاء نصية محددة واستبدال النص وحفظ ملف PDF المعدل.

#### س: لماذا أرغب في إعادة ترتيب المحتويات في مستند PDF؟

ج: يمكن أن تكون إعادة ترتيب المحتويات في مستند PDF مفيدة لأغراض متعددة، مثل تحديث النص أو إعادة تنسيق التخطيط أو إجراء التصحيحات. تسمح لك هذه التقنية بتعديل محتوى ملف PDF ديناميكيًا مع الحفاظ على بنيته ومظهره.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل حيث توجد ملفات PDF الخاصة بك.

#### س: كيف يمكنني إجراء استبدال النص في مستند PDF؟

 ج: يرشدك البرنامج التعليمي خلال عملية البحث عن أجزاء نصية محددة في ملف PDF باستخدام الملف`TextFragmentAbsorber`فصل. ويوضح كيفية تخصيص مظهر أجزاء النص واستبدال محتواها.

#### س: هل يمكنني تخصيص الخط والحجم واللون للنص المستبدل؟

 ج: نعم، يمكنك تخصيص الخط والحجم واللون للنص المستبدل عن طريق تعديل`TextState` خصائص`TextFragment` هدف. يوفر البرنامج التعليمي مثالاً لكيفية تعيين الخط وحجم الخط ولون المقدمة للنص.

#### س: كيف يمكنني حفظ مستند PDF المعدل؟

 ج: بعد إجراء استبدال النص وتخصيص أجزاء النص، يمكنك حفظ مستند PDF المعدل باستخدام الملف`Save` طريقة`Document` فصل. قم بتوفير مسار ملف الإخراج المطلوب كوسيطة لملف`Save` طريقة.

#### س: ما هو الناتج المتوقع من هذا البرنامج التعليمي؟

ج: باتباع البرنامج التعليمي وتنفيذ كود C# المقدم، سوف تقوم بإنشاء مستند PDF معدل حيث تم استبدال أجزاء نصية محددة وتخصيصها وفقًا لمواصفاتك.

#### س: هل يمكنني استخدام تعبيرات عادية مختلفة للبحث عن النص؟

 ج: نعم، يمكنك استخدام تعبيرات عادية مختلفة للبحث عن أجزاء نصية محددة في مستند PDF. يوضح المثال الموجود في البرنامج التعليمي كيفية إنشاء ملف`TextFragmentAbsorber`كائن بتعبير عادي محدد للبحث عن النص واستبداله.

#### س: هل يلزم وجود ترخيص Aspose صالح لهذا البرنامج التعليمي؟

ج: نعم، يلزم وجود ترخيص Aspose صالح حتى يعمل هذا البرنامج التعليمي بشكل صحيح. يمكنك شراء ترخيص كامل أو الحصول على ترخيص مؤقت لمدة 30 يومًا من موقع Aspose.