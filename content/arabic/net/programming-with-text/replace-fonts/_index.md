---
title: استبدال الخطوط في ملف PDF
linktitle: استبدال الخطوط في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال الخطوط في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 340
url: /ar/net/programming-with-text/replace-fonts/
---
سنشرح في هذا البرنامج التعليمي كيفية استبدال خطوط معينة في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتابع عملية تحميل مستند PDF خطوة بخطوة، والبحث عن أجزاء النص، وتحديد الخطوط المراد استبدالها، واستبدال الخطوط، وحفظ ملف PDF المعدل باستخدام كود مصدر C# المقدم.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل حيث يوجد ملف PDF المُدخل. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 بعد ذلك، نقوم بتحميل مستند PDF باستخدام الملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## الخطوة 3: البحث عن الخطوط واستبدالها

 نقوم بإنشاء أ`TextFragmentAbsorber`الكائن وقم بتعيين خيار التحرير لإزالة الخطوط غير المستخدمة. بعد ذلك، نقبل الممتص لجميع صفحات مستند PDF للبحث عن أجزاء النص.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## الخطوة 4: استبدال الخطوط

نحن نجتاز جميع أجزاء النص التي حددها المستوعب. إذا كان اسم الخط الخاص بجزء النص يتطابق مع الخط المطلوب استبداله، فإننا نستبدله بالخط الجديد.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## الخطوة 5: احفظ ملف PDF المعدل

وأخيرًا، نقوم بحفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لاستبدال الخطوط باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// تحميل ملف PDF المصدر
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// ابحث في أجزاء النص وقم بتعيين خيار التحرير لإزالة الخطوط غير المستخدمة
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// قبول الممتص لجميع الصفحات
	pdfDocument.Pages.Accept(absorber);
	// اجتياز كافة أجزاء النص
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

في هذا البرنامج التعليمي، تعلمت كيفية استبدال خطوط معينة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك تحميل مستند PDF والبحث عن أجزاء النص وتحديد خطوط معينة واستبدالها وحفظ ملف PDF المعدل.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "استبدال الخطوط في ملف PDF"؟

ج: يوضح البرنامج التعليمي "استبدال الخطوط في ملف PDF" كيفية استخدام مكتبة Aspose.PDF لـ .NET لاستبدال خطوط معينة في مستند PDF. فهو يوفر دليلاً خطوة بخطوة حول كيفية تحميل مستند PDF، والبحث عن أجزاء النص، وتحديد الخطوط المراد استبدالها، واستبدال الخطوط، وحفظ ملف PDF المعدل.

#### س: لماذا أرغب في استبدال الخطوط في مستند PDF؟

ج: قد يكون استبدال الخطوط في مستند PDF ضروريًا عندما تريد توحيد مظهر النص أو تحسين توافق المستند عبر الأجهزة والأنظمة الأساسية المختلفة. يسمح لك بضمان الطباعة والتنسيق المتسقين.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل حيث يوجد ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني استبدال خطوط معينة في مستند PDF؟

ج: يرشدك البرنامج التعليمي خلال العملية خطوة بخطوة:

1.  قم بتحميل مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` الكائن وقم بتعيين خيار التحرير لإزالة الخطوط غير المستخدمة. اقبل الممتص لجميع الصفحات للبحث عن أجزاء النص.
3. اجتياز أجزاء النص المحددة. إذا كان اسم الخط الخاص بجزء النص يتطابق مع الخط الذي تريد استبداله، فاستبدله بالخط الجديد.

####  س: ما هو الغرض من الاستخدام`TextFragmentAbsorber` with font replacement options?

 ج: ال`TextFragmentAbsorber` مع خيارات استبدال الخط، يمكنك تحديد موقع أجزاء النص وإزالة الخطوط غير المستخدمة في نفس الوقت. يعد هذا أمرًا مهمًا لضمان عدم إضافة الخطوط المستبدلة كموارد إضافية في ملف PDF.

#### س: كيف يمكنني تحديد خطوط معينة لاستبدالها؟

ج: من خلال المرور عبر أجزاء النص التي تم تحديدها بواسطة أداة الامتصاص، يمكنك الوصول إلى معلومات الخط لكل جزء من النص. إذا كان اسم الخط يطابق الخط الذي تريد استبداله، فيمكنك إجراء الاستبدال.

#### س: ماذا يحدث إذا لم يتم العثور على الخط المراد استبداله في جزء النص؟

ج: إذا لم يتم العثور على الخط المراد استبداله في جزء النص، فسيظل خط جزء النص بدون تغيير. سيتم الاستبدال فقط في حالة تطابق اسم الخط.

#### س: هل هناك قيود على استبدال الخطوط في هذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على استبدال خطوط معينة في أجزاء النص. إذا كنت بحاجة إلى استبدال الخطوط في سياقات أخرى، مثل التعليقات التوضيحية أو حقول النموذج، فستحتاج إلى توسيع النهج وفقًا لذلك.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، سوف تقوم باستبدال خطوط معينة في مستند PDF. سيتم استبدال الخطوط المحددة بواسطة المعايير التي قمت بتعيينها بالخط الجديد الذي تحدده.

#### س: هل يمكنني استخدام هذا الأسلوب لاستبدال الخطوط في مستند PDF بأكمله؟

ج: نعم، يمكنك تعديل التعليمات البرمجية لاستبدال الخطوط في مستند PDF بأكمله عن طريق المرور عبر جميع أجزاء النص وتطبيق منطق استبدال الخط.