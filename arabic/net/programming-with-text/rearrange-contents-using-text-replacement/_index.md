---
title: إعادة ترتيب المحتويات باستخدام استبدال النص
linktitle: إعادة ترتيب المحتويات باستخدام استبدال النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إعادة ترتيب المحتويات في مستند PDF باستخدام استبدال النص مع Aspose.PDF for .NET.
type: docs
weight: 270
url: /ar/net/programming-with-text/rearrange-contents-using-text-replacement/
---

في هذا البرنامج التعليمي ، سنشرح كيفية إعادة ترتيب المحتويات في مستند PDF باستخدام استبدال النص مع مكتبة Aspose.PDF لـ .NET. سنتابع العملية خطوة بخطوة لتحميل ملف PDF ، والبحث عن أجزاء نصية محددة ، واستبدال النص ، وحفظ ملف PDF المعدل باستخدام كود المصدر C # المقدم.

## متطلبات

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى الدليل حيث توجد ملفات PDF الخاصة بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملفات PDF الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل ملف PDF المصدر

 بعد ذلك ، نقوم بتحميل ملف PDF المصدر باستخدام ملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## الخطوة 3: البحث عن أجزاء النص واستبدالها

 نقوم بإنشاء ملف`TextFragmentAbsorber` كائن بتعبير عادي للبحث عن أجزاء نصية معينة. بعد ذلك ، نقوم بتكرار أجزاء النص وتخصيص الخط والحجم واللون واستبدال النص.

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

أخيرًا ، نقوم بحفظ مستند PDF المعدل في ملف الإخراج المحدد.

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
	// قم بتحميل ملف PDF المصدر
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	//قم بإنشاء كائن TextFragment Absorber بتعبير عادي
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// استبدل كل TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// تعيين خط جزء النص الذي يتم استبداله
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// تعيين حجم الخط
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// استبدل النص بسلسلة أكبر من العنصر النائب
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// احفظ ملف PDF الناتج
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx. ") ؛
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إعادة ترتيب المحتويات في مستند PDF باستخدام استبدال النص مع مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك البحث عن أجزاء نصية معينة ، وتخصيص مظهرها ، واستبدال النص في مستند PDF.