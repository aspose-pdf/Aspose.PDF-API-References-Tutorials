---
title: إزالة الخطوط غير المستخدمة في ملف PDF
linktitle: إزالة الخطوط غير المستخدمة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إزالة الخطوط غير المستخدمة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 300
url: /ar/net/programming-with-text/remove-unused-fonts/
---
سنشرح في هذا البرنامج التعليمي كيفية إزالة الخطوط غير المستخدمة في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتابع عملية تحميل ملف PDF خطوة بخطوة، وتحديد الخطوط غير المستخدمة وإزالتها، وحفظ ملف PDF المحدث باستخدام كود مصدر C# المقدم.

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## الخطوة 3: تحديد الخطوط غير المستخدمة وإزالتها

 نقوم بإنشاء أ`TextFragmentAbsorber` كائن مع`TextEditOptions` تم تعيين المعلمة على`TextEditOptions.FontReplace.RemoveUnusedFonts` . يتيح لنا هذا الخيار تحديد الخطوط غير المستخدمة وإزالتها في مستند PDF. ثم نقوم بالتكرار من خلال كل`TextFragments` وضبط الخط على الخط المطلوب.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## الخطوة 4: احفظ ملف PDF المحدث

أخيرًا، نقوم بحفظ مستند PDF المحدث في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لإزالة الخطوط غير المستخدمة باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// تحميل ملف PDF المصدر
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// التكرار من خلال جميع TextFragments
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

في هذا البرنامج التعليمي، تعلمت كيفية إزالة الخطوط غير المستخدمة من مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل الموضح خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك تحميل ملف PDF وتحديد الخطوط غير المستخدمة وإزالتها وحفظ ملف PDF المحدث.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "إزالة الخطوط غير المستخدمة في ملف PDF"؟

ج: يشرح البرنامج التعليمي "إزالة الخطوط غير المستخدمة في ملف PDF" كيفية استخدام مكتبة Aspose.PDF لـ .NET لإزالة الخطوط غير المستخدمة من مستند PDF. يرشدك البرنامج التعليمي خلال عملية تحميل ملف PDF، وتحديد الخطوط غير المستخدمة وإزالتها، وحفظ ملف PDF المحدث.

#### س: لماذا أرغب في إزالة الخطوط غير المستخدمة من مستند PDF؟

ج: يمكن أن تساعد إزالة الخطوط غير المستخدمة من مستند PDF في تقليل حجم الملف وتحسين المستند للحصول على أداء أفضل. يعد هذا مفيدًا بشكل خاص عند التعامل مع ملفات PDF التي تحتوي على خطوط مضمنة لا يتم استخدامها فعليًا في محتوى المستند.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل حيث توجد ملفات PDF الخاصة بك.

#### س: كيف يمكنني إزالة الخطوط غير المستخدمة من مستند PDF باستخدام مكتبة Aspose.PDF؟

ج: يرشدك البرنامج التعليمي خلال العملية خطوة بخطوة:

1.  افتح مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` كائن مع`TextEditOptions` ضبط ل`FontReplace.RemoveUnusedFonts`.
3. اقبل أداة الامتصاص لتحديد الخطوط غير المستخدمة وإزالتها من ملف PDF.
4.  التكرار من خلال الكل`TextFragments` وضبط الخط على الخط المطلوب.
5. احفظ مستند PDF المحدث.

####  س: ما هو الغرض من`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 ج: ال`TextEditOptions.FontReplace.RemoveUnusedFonts` المعلمة ترشد`TextFragmentAbsorber` لتحديد وإزالة الخطوط غير المستخدمة من مستند PDF.

#### س: هل يمكنني استبدال الخطوط غير المستخدمة بخط من اختياري؟

ج: نعم، يمكنك تعديل الكود لاستبدال الخطوط غير المستخدمة بخط من اختيارك. في نموذج التعليمات البرمجية المتوفرة، يتم استخدام الخط "Arial, Bold" كبديل.

####  س: كيف`TextFragmentAbsorber` work to remove unused fonts?

 ج: ال`TextFragmentAbsorber` تم تكوينه مع`TextEditOptions.FontReplace.RemoveUnusedFonts` المعلمة، التي تحدد الخطوط غير المستخدمة داخل أجزاء النص في ملف PDF. بعد الاستيعاب، يمكنك التكرار من خلال`TextFragments` وقم بتعيين الخطوط الخاصة بهم على الخطوط البديلة المطلوبة.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، سوف تقوم بإزالة الخطوط غير المستخدمة من مستند PDF المدخل وحفظ الإصدار المحدث كملف PDF الناتج.

#### س: هل يمكنني تعديل التعليمات البرمجية لإزالة الخطوط من صفحات أو مناطق معينة فقط؟

ج: يركز الكود المقدم على إزالة الخطوط غير المستخدمة من مستند PDF بأكمله. إذا كنت تريد استهداف صفحات أو مناطق معينة لإزالة الخطوط، فستحتاج إلى تعديل النهج واستخدام منطق أكثر تعقيدًا لتحديد الخطوط غير المستخدمة في تلك المناطق.