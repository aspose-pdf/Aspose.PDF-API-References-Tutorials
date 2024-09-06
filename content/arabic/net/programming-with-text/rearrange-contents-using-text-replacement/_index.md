---
title: إعادة ترتيب المحتويات باستخدام استبدال النص
linktitle: إعادة ترتيب المحتويات باستخدام استبدال النص
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إعادة ترتيب المحتويات في مستند PDF باستخدام استبدال النص مع Aspose.PDF لـ .NET.
type: docs
weight: 270
url: /ar/net/programming-with-text/rearrange-contents-using-text-replacement/
---
في هذا البرنامج التعليمي، سنشرح كيفية إعادة ترتيب المحتويات في مستند PDF باستخدام استبدال النص مع مكتبة Aspose.PDF لـ .NET. سنمر بعملية تحميل PDF خطوة بخطوة، والبحث عن أجزاء نصية محددة، واستبدال النص، وحفظ ملف PDF المعدل باستخدام كود المصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت مكتبة Aspose.PDF لـ .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي توجد به ملفات PDF الخاصة بك. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى ملفات PDF الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل ملف PDF المصدر

 بعد ذلك، نقوم بتحميل مستند PDF المصدر باستخدام`Document` الفئة من مكتبة Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## الخطوة 3: البحث عن أجزاء النص واستبدالها

 نحن ننشئ`TextFragmentAbsorber` كائن به تعبير عادي للبحث عن أجزاء نصية محددة. ثم نكرر البحث في أجزاء النص، ونخصص الخط والحجم واللون ونستبدل النص.

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

## الخطوة 4: احفظ ملف PDF المعدّل

وأخيرًا، نقوم بحفظ مستند PDF المعدّل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### عينة من كود المصدر لإعادة ترتيب المحتويات باستخدام استبدال النص باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// تحميل ملف PDF المصدر
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// إنشاء كائن امتصاص TextFragment باستخدام تعبير عادي
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// استبدال كل جزء نصي
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// تعيين خط جزء النص الذي يتم استبداله
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// ضبط حجم الخط
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// استبدال النص بسلسلة أكبر من العنصر النائب
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

في هذا البرنامج التعليمي، تعلمت كيفية إعادة ترتيب المحتويات في مستند PDF باستخدام استبدال النص باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك البحث عن أجزاء نصية معينة وتخصيص مظهرها واستبدال النص في مستند PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "إعادة ترتيب المحتويات باستخدام استبدال النص"؟

ج: يوضح البرنامج التعليمي "إعادة ترتيب المحتويات باستخدام استبدال النص" كيفية استخدام مكتبة Aspose.PDF لـ .NET لإعادة ترتيب المحتويات في مستند PDF عن طريق استبدال النص. يوفر البرنامج التعليمي دليلاً خطوة بخطوة وكود مصدر C# لمساعدتك في تحميل ملف PDF والبحث عن أجزاء نصية معينة واستبدال النص وحفظ ملف PDF المعدل.

#### س: لماذا أرغب في إعادة ترتيب المحتويات في مستند PDF؟

ج: يمكن أن تكون إعادة ترتيب المحتويات في مستند PDF مفيدة لأغراض مختلفة، مثل تحديث النص أو إعادة تنسيق التخطيط أو إجراء تصحيحات. تتيح لك هذه التقنية تعديل محتوى ملف PDF ديناميكيًا مع الحفاظ على بنيته ومظهره.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي توجد به ملفات PDF الخاصة بك.

#### س: كيف أقوم باستبدال النص في مستند PDF؟

 أ: يرشدك البرنامج التعليمي خلال عملية البحث عن أجزاء نصية محددة في ملف PDF باستخدام`TextFragmentAbsorber`يوضح كيفية تخصيص مظهر أجزاء النص واستبدال محتواها.

#### س: هل يمكنني تخصيص الخط والحجم ولون النص المستبدل؟

 ج: نعم، يمكنك تخصيص الخط والحجم ولون النص المستبدل عن طريق تعديل`TextState` خصائص`TextFragment` يوفر البرنامج التعليمي مثالاً لكيفية تعيين الخط وحجم الخط ولون مقدمة النص.

#### س: كيف أحفظ مستند PDF المعدل؟

 أ: بعد إجراء استبدال النص وتخصيص أجزاء النص، يمكنك حفظ مستند PDF المعدل باستخدام`Save` طريقة`Document` الفئة. قم بتوفير مسار ملف الإخراج المطلوب كحجة لـ`Save` طريقة.

#### س: ما هي النتيجة المتوقعة من هذا البرنامج التعليمي؟

ج: باتباع البرنامج التعليمي وتنفيذ كود C# المقدم، ستتمكن من إنشاء مستند PDF معدّل حيث تم استبدال أجزاء نصية محددة وتخصيصها وفقًا لمواصفاتك.

#### س: هل يمكنني استخدام تعبيرات منتظمة مختلفة للبحث النصي؟

 ج: نعم، يمكنك استخدام تعبيرات منتظمة مختلفة للبحث عن أجزاء نصية محددة في مستند PDF. يوضح المثال المقدم في البرنامج التعليمي كيفية إنشاء`TextFragmentAbsorber`كائن يحتوي على تعبير منتظم محدد للبحث عن نص واستبداله.

#### س: هل يلزم الحصول على ترخيص Aspose صالح لهذا البرنامج التعليمي؟

ج: نعم، يلزم الحصول على ترخيص Aspose صالح حتى يعمل هذا البرنامج التعليمي بشكل صحيح. يمكنك شراء ترخيص كامل أو الحصول على ترخيص مؤقت لمدة 30 يومًا من موقع Aspose على الويب.