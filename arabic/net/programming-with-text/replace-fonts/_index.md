---
title: استبدال الخطوط
linktitle: استبدال الخطوط
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال الخطوط في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 340
url: /ar/net/programming-with-text/replace-fonts/
---

في هذا البرنامج التعليمي ، سنشرح كيفية استبدال خطوط معينة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنمر في العملية خطوة بخطوة لتحميل مستند PDF ، والبحث عن أجزاء نصية ، وتحديد الخطوط المراد استبدالها ، واستبدال الخطوط ، وحفظ ملف PDF المعدل باستخدام كود المصدر C # المقدم.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى ضبط المسار إلى الدليل حيث لديك ملف PDF للإدخال. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir`متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 بعد ذلك ، نقوم بتحميل ملف PDF باستخدام ملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## الخطوة 3: البحث عن الخطوط واستبدالها

 نقوم بإنشاء ملف`TextFragmentAbsorber` الكائن وقم بتعيين خيار التحرير لإزالة الخطوط غير المستخدمة. بعد ذلك ، نقبل أداة الامتصاص لجميع صفحات مستند PDF للبحث عن أجزاء النص.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## الخطوة 4: استبدال الخطوط

نحن ننتقل عبر جميع أجزاء النص التي حددها جهاز الامتصاص. إذا كان اسم الخط لجزء من النص يطابق الخط المطلوب لاستبداله ، فإننا نستبدل الخط الجديد.

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

أخيرًا ، نقوم بحفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Replace Fonts باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل ملف PDF المصدر
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// البحث في أجزاء النص وتعيين خيار التحرير كإزالة الخطوط غير المستخدمة
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// تقبل الممتص لجميع الصفحات
	pdfDocument.Pages.Accept(absorber);
	// اجتياز جميع أجزاء النص
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// إذا كان اسم الخط ArialMT ، فاستبدل اسم الخط بـ Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// احفظ المستند المحدث
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx. ") ؛
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية استبدال خطوط معينة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تحميل مستند PDF والبحث عن أجزاء نصية وتحديد واستبدال خطوط معينة وحفظ ملف PDF المعدل.