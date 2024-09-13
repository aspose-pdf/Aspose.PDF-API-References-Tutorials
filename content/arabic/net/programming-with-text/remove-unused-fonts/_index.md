---
title: إزالة الخطوط غير المستخدمة في ملف PDF
linktitle: إزالة الخطوط غير المستخدمة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إزالة الخطوط غير المستخدمة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 300
url: /ar/net/programming-with-text/remove-unused-fonts/
---
في هذا البرنامج التعليمي، سنشرح كيفية إزالة الخطوط غير المستخدمة في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتناول عملية تحميل ملف PDF خطوة بخطوة، وتحديد الخطوط غير المستخدمة وإزالتها، وحفظ ملف PDF المحدث باستخدام كود المصدر C# المقدم.

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## الخطوة 3: تحديد الخطوط غير المستخدمة وإزالتها

 نحن ننشئ`TextFragmentAbsorber` كائن مع`TextEditOptions` تم تعيين المعلمة إلى`TextEditOptions.FontReplace.RemoveUnusedFonts` يتيح لنا هذا الخيار تحديد الخطوط غير المستخدمة وإزالتها من مستند PDF. ثم نكرر كل الخطوات`TextFragments` وضبط الخط إلى الخط المطلوب.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## الخطوة 4: احفظ ملف PDF المحدث

وأخيرًا، نقوم بحفظ مستند PDF المحدث في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### عينة من كود المصدر لإزالة الخطوط غير المستخدمة باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// تحميل ملف PDF المصدر
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// قم بالتكرار خلال جميع أجزاء النص
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// حفظ المستند المحدث
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إزالة الخطوط غير المستخدمة من مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك تحميل ملف PDF وتحديد الخطوط غير المستخدمة وإزالتها وحفظ ملف PDF المحدث.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "إزالة الخطوط غير المستخدمة في ملف PDF"؟

ج: يوضح البرنامج التعليمي "إزالة الخطوط غير المستخدمة في ملف PDF" كيفية استخدام مكتبة Aspose.PDF لـ .NET لإزالة الخطوط غير المستخدمة من مستند PDF. يرشدك البرنامج التعليمي خلال عملية تحميل ملف PDF، وتحديد الخطوط غير المستخدمة وإزالتها، وحفظ ملف PDF المحدث.

#### س: لماذا أرغب في إزالة الخطوط غير المستخدمة من مستند PDF؟

ج: إن إزالة الخطوط غير المستخدمة من مستند PDF يمكن أن يساعد في تقليل حجم الملف وتحسين المستند لتحسين الأداء. وهذا مفيد بشكل خاص عند التعامل مع ملفات PDF التي تحتوي على خطوط مضمنة لا يتم استخدامها فعليًا في محتوى المستند.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي توجد به ملفات PDF الخاصة بك.

#### س: كيف يمكنني إزالة الخطوط غير المستخدمة من مستند PDF باستخدام مكتبة Aspose.PDF؟

أ: يرشدك البرنامج التعليمي خلال العملية خطوة بخطوة:

1.  افتح مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` كائن مع`TextEditOptions` تم ضبطه على`FontReplace.RemoveUnusedFonts`.
3. وافق على الامتصاص لتحديد الخطوط غير المستخدمة وإزالتها من ملف PDF.
4.  كرر كل شيء`TextFragments` وضبط الخط إلى الخط المطلوب.
5. احفظ مستند PDF المحدث.

####  س: ما هو الغرض من`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 أ: ال`TextEditOptions.FontReplace.RemoveUnusedFonts` المعلمة تعطي التعليمات`TextFragmentAbsorber`لتحديد الخطوط غير المستخدمة وإزالتها من مستند PDF.

#### س: هل يمكنني استبدال الخطوط غير المستخدمة بخط من اختياري؟

ج: نعم، يمكنك تعديل الكود لاستبدال الخطوط غير المستخدمة بخط من اختيارك. في الكود النموذجي المقدم، تم استخدام الخط "Arial, Bold" كبديل.

#### س: كيف يتم ذلك؟`TextFragmentAbsorber` work to remove unused fonts?

 أ: ال`TextFragmentAbsorber` تم تكوينه باستخدام`TextEditOptions.FontReplace.RemoveUnusedFonts` المعلمة التي تحدد الخطوط غير المستخدمة داخل أجزاء النص في ملف PDF. بعد الامتصاص، يمكنك التكرار خلال`TextFragments` وتعيين الخطوط الخاصة بهم إلى الخطوط البديلة المطلوبة.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، ستتمكن من إزالة الخطوط غير المستخدمة من مستند PDF المدخل وحفظ الإصدار المحدث كملف PDF المخرج.

#### س: هل يمكنني تعديل الكود لإزالة الخطوط من صفحات أو مناطق محددة فقط؟

ج: يركز الكود المقدم على إزالة الخطوط غير المستخدمة من مستند PDF بالكامل. إذا كنت تريد استهداف صفحات أو مناطق معينة لإزالة الخطوط، فستحتاج إلى تعديل النهج واستخدام منطق أكثر تعقيدًا لتحديد الخطوط غير المستخدمة في تلك المناطق.