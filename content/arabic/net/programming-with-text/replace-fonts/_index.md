---
title: استبدال الخطوط في ملف PDF
linktitle: استبدال الخطوط في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استبدال الخطوط في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 340
url: /ar/net/programming-with-text/replace-fonts/
---
في هذا البرنامج التعليمي، سنشرح كيفية استبدال خطوط معينة في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنمر بعملية تحميل مستند PDF خطوة بخطوة، والبحث عن أجزاء نصية، وتحديد الخطوط المراد استبدالها، واستبدال الخطوط، وحفظ ملف PDF المعدّل باستخدام كود المصدر C# المقدم.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت مكتبة Aspose.PDF لـ .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي يحتوي على ملف PDF المدخل. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل مستند PDF

 بعد ذلك، نقوم بتحميل مستند PDF باستخدام`Document` الفئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## الخطوة 3: البحث عن الخطوط واستبدالها

 نحن ننشئ`TextFragmentAbsorber`الكائن وضبط خيار التحرير لإزالة الخطوط غير المستخدمة. ثم نقبل الممتص لجميع صفحات مستند PDF للبحث عن أجزاء النص.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## الخطوة 4: استبدال الخطوط

نقوم بالمرور عبر كل أجزاء النص التي تم تحديدها بواسطة الممتص. إذا كان اسم الخط الخاص بجزء النص يتطابق مع الخط المطلوب استبداله، فإننا نستبدله بالخط الجديد.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## الخطوة 5: احفظ ملف PDF المعدّل

وأخيرًا، نقوم بحفظ مستند PDF المعدّل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### عينة من كود المصدر لاستبدال الخطوط باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// تحميل ملف PDF المصدر
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// ابحث عن أجزاء نصية وقم بتعيين خيار التحرير لإزالة الخطوط غير المستخدمة
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// قبول الممتص لجميع الصفحات
	pdfDocument.Pages.Accept(absorber);
	// التنقل عبر جميع أجزاء النص
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// إذا كان اسم الخط هو ArialMT، فاستبدل اسم الخط بـ Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// حفظ المستند المحدث
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية استبدال خطوط معينة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك تحميل مستند PDF والبحث عن أجزاء نصية وتحديد خطوط معينة واستبدالها وحفظ ملف PDF المعدل.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "استبدال الخطوط في ملف PDF"؟

ج: يوضح البرنامج التعليمي "استبدال الخطوط في ملف PDF" كيفية استخدام مكتبة Aspose.PDF لـ .NET لاستبدال خطوط معينة في مستند PDF. كما يوفر دليلاً خطوة بخطوة حول كيفية تحميل مستند PDF والبحث عن أجزاء نصية وتحديد الخطوط المراد استبدالها واستبدال الخطوط وحفظ ملف PDF المعدل.

#### س: لماذا أرغب في استبدال الخطوط في مستند PDF؟

ج: قد يكون استبدال الخطوط في مستند PDF ضروريًا عندما تريد توحيد مظهر النص أو تحسين توافق المستند عبر الأجهزة والمنصات المختلفة. يتيح لك ذلك ضمان اتساق الطباعة والتنسيق.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي يوجد به ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني استبدال خطوط معينة في مستند PDF؟

أ: يرشدك البرنامج التعليمي خلال العملية خطوة بخطوة:

1.  قم بتحميل مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` قم بتعديل الكائن وتعيين خيار التحرير لإزالة الخطوط غير المستخدمة. اقبل الامتصاص لجميع الصفحات للبحث عن أجزاء النص.
3. قم بالتنقل عبر أجزاء النص المحددة. إذا كان اسم الخط الخاص بجزء النص يتطابق مع الخط الذي تريد استبداله، فاستبدله بالخط الجديد.

####  س: ما هو الغرض من الاستخدام؟`TextFragmentAbsorber` with font replacement options?

 أ: ال`TextFragmentAbsorber` تتيح لك خيارات استبدال الخطوط تحديد أجزاء النص وإزالة الخطوط غير المستخدمة في نفس الوقت. وهذا مهم لضمان عدم إضافة الخطوط المستبدلة كموارد إضافية في ملف PDF.

#### س: كيف يمكنني تحديد الخطوط المحددة لاستبدالها؟

ج: من خلال التنقل عبر أجزاء النص التي تم تحديدها بواسطة الممتص، يمكنك الوصول إلى معلومات الخط لكل جزء نصي. إذا كان اسم الخط يتطابق مع الخط الذي تريد استبداله، فيمكنك إجراء الاستبدال.

#### س: ماذا يحدث إذا لم يتم العثور على الخط الذي يجب استبداله في جزء النص؟

ج: إذا لم يتم العثور على الخط المراد استبداله في جزء من النص، فإن خط جزء النص يظل دون تغيير. ولن يتم الاستبدال إلا إذا تطابق اسم الخط.

#### س: هل هناك قيود على استبدال الخطوط في هذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على استبدال خطوط معينة في أجزاء من النص. إذا كنت بحاجة إلى استبدال الخطوط في سياقات أخرى، مثل التعليقات التوضيحية أو حقول النماذج، فستحتاج إلى توسيع النهج وفقًا لذلك.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، ستستبدل خطوطًا معينة في مستند PDF. سيتم استبدال الخطوط التي تم تحديدها وفقًا للمعايير التي حددتها بالخط الجديد الذي تحدده.

#### س: هل يمكنني استخدام هذا النهج لاستبدال الخطوط في مستند PDF بأكمله؟

ج: نعم، يمكنك تكييف الكود لاستبدال الخطوط في جميع أنحاء مستند PDF عن طريق التنقل عبر جميع أجزاء النص وتطبيق منطق استبدال الخط.