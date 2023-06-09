---
title: حدد تباعد الأسطر
linktitle: حدد تباعد الأسطر
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد تباعد الأسطر في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 510
url: /ar/net/programming-with-text/specify-line-spacing/
---

يشرح هذا البرنامج التعليمي كيفية تحديد تباعد الأسطر في مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل الشروع في البرنامج التعليمي ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: قم بإعداد المشروع

ابدأ بإنشاء مشروع C # جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف التعليمات التالية باستخدام التوجيهات في بداية ملف C # لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 عيّن المسار إلى دليل المستند الخاص بك باستخدام ملف`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: قم بتحميل ملف PDF المدخل

 قم بتحميل ملف PDF المدخل باستخدام ملف`Document` فصل:

```csharp
Document doc = new Document();
```

## الخطوة 5: إنشاء TextFormattingOptions

 إنشاء`TextFormattingOptions` الكائن وتعيين وضع تباعد الأسطر على`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## الخطوة 6: قم بإنشاء جزء نصي

 إنشاء`TextFragment` كائن وحدد محتوى النص:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## الخطوة 7: تحميل ملف الخط (اختياري)

 إذا كنت تريد استخدام خط معين للنص ، فقم بتحميل ملف خط TrueType في ملف`FileStream` هدف:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 يستبدل`"HPSimplified.TTF"`مع اسم ملف الخط الفعلي.

## الخطوة 8: حدد موضع النص وتباعد الأسطر

 عيّن موضع جزء النص وعيّن الامتداد`TextFormattingOptions` الى`TextState.FormattingOptions` ملكية:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## الخطوة 9: أضف النص إلى المستند

 أضف جزء النص إلى المستند ، إما بإلحاقه بملف`TextBuilder` أو مباشرة إلى الصفحة`Paragraphs` مجموعة:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## الخطوة 10: احفظ مستند PDF الناتج

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 تأكد من استبداله`"SpecifyLineSpacing_out.pdf"` باسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لـ Specify Line Spacing باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// قم بتحميل ملف PDF للإدخال
Document doc = new Document();
//قم بإنشاء TextFormattingOptions باستخدام LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// إنشاء كائن منشئ النص للصفحة الأولى من المستند
//TextBuilder textBuilder = نص جديد (doc.Pages [1]) ؛
// إنشاء جزء نصي مع سلسلة عينة
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// قم بتحميل خط تروتايب إلى كائن دفق
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// قم بتعيين اسم الخط للسلسلة النصية
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// حدد موضع جزء النص
		textFragment.Position = new Position(100, 600);
		//قم بتعيين TextFormattingOptions للجزء الحالي على محدد مسبقًا (والذي يشير إلى LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// أضف النص إلى TextBuilder بحيث يمكن وضعه فوق ملف PDF
		//textBuilder.AppendText (textFragment) ،
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// حفظ مستند PDF الناتج
	doc.Save(dataDir);
}
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تحديد تباعد الأسطر في مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً تفصيليًا ، بدءًا من إعداد المشروع وحتى حفظ المستند المعدل. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لتخصيص تباعد الأسطر في ملفات PDF.