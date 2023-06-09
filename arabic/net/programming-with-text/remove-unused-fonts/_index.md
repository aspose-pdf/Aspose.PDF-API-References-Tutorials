---
title: إزالة الخطوط غير المستخدمة
linktitle: إزالة الخطوط غير المستخدمة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إزالة الخطوط غير المستخدمة من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 300
url: /ar/net/programming-with-text/remove-unused-fonts/
---

في هذا البرنامج التعليمي ، سنشرح كيفية إزالة الخطوط غير المستخدمة من مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنمر في العملية خطوة بخطوة لتحميل ملف PDF وتحديد الخطوط غير المستخدمة وإزالتها وحفظ ملف PDF المحدث باستخدام كود المصدر C # المقدم.

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## الخطوة 3: تحديد وإزالة الخطوط غير المستخدمة

 نقوم بإنشاء ملف`TextFragmentAbsorber` كائن مع`TextEditOptions` تم تعيين المعلمة على`TextEditOptions.FontReplace.RemoveUnusedFonts` . يتيح لنا هذا الخيار تحديد الخطوط غير المستخدمة وإزالتها في مستند PDF. ثم نقوم بالتكرار خلال جميع ملفات`TextFragments` واضبط الخط على الخط المطلوب.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## الخطوة 4: احفظ ملف PDF المحدث

أخيرًا ، نحفظ مستند PDF المحدث في ملف الإخراج المحدد.

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
	// قم بتحميل ملف PDF المصدر
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// كرر عبر كل أجزاء النص
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// احفظ المستند المحدث
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx. ") ؛
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إزالة الخطوط غير المستخدمة من مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل المفصل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تحميل ملف PDF وتحديد وإزالة الخطوط غير المستخدمة وحفظ ملف PDF المحدث.