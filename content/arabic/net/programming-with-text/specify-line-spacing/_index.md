---
title: تحديد تباعد الأسطر في ملف PDF
linktitle: تحديد تباعد الأسطر في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد تباعد الأسطر في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 510
url: /ar/net/programming-with-text/specify-line-spacing/
---
يشرح هذا البرنامج التعليمي كيفية تحديد تباعد الأسطر في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل متابعة البرنامج التعليمي، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف ما يلي باستخدام التوجيهات في بداية ملف C# الخاص بك لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: تحميل ملف PDF الإدخال

 قم بتحميل ملف PDF المدخل باستخدام ملف`Document` فصل:

```csharp
Document doc = new Document();
```

## الخطوة 5: إنشاء خيارات تنسيق النص

 إنشاء`TextFormattingOptions` الكائن واضبط وضع تباعد الأسطر على`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## الخطوة 6: إنشاء TextFragment

 إنشاء`TextFragment` الكائن وتحديد محتوى النص:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## الخطوة 7: تحميل ملف الخط (اختياري)

 إذا كنت تريد استخدام خط معين للنص، فقم بتحميل ملف خط TrueType إلى ملف`FileStream` هدف:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 يستبدل`"HPSimplified.TTF"` مع اسم ملف الخط الفعلي.

## الخطوة 8: تحديد موضع النص وتباعد الأسطر

 قم بتعيين موضع جزء النص وقم بتعيين`TextFormattingOptions` إلى`TextState.FormattingOptions` ملكية:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## الخطوة 9: أضف النص إلى المستند

 قم بإضافة جزء النص إلى المستند، إما عن طريق إلحاقه بـ a`TextBuilder` أو مباشرة إلى الصفحة`Paragraphs` مجموعة:

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

 تأكد من استبدال`"SpecifyLineSpacing_out.pdf"` مع اسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لتحديد تباعد الأسطر باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// تحميل ملف PDF الإدخال
Document doc = new Document();
//قم بإنشاء TextFormattingOptions باستخدام LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// إنشاء كائن منشئ النص للصفحة الأولى من المستند
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// إنشاء جزء نصي باستخدام سلسلة عينة
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// قم بتحميل خط TrueType إلى كائن الدفق
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//قم بتعيين اسم الخط لسلسلة نصية
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// حدد موضع جزء النص
		textFragment.Position = new Position(100, 600);
		//قم بتعيين TextFormattingOptions للجزء الحالي على المحدد مسبقًا (الذي يشير إلى LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// أضف النص إلى TextBuilder بحيث يمكن وضعه فوق ملف PDF
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// احفظ مستند PDF الناتج
	doc.Save(dataDir);
}
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تحديد تباعد الأسطر في مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من إعداد المشروع وحتى حفظ المستند المعدل. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لتخصيص تباعد أسطر النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تحديد تباعد الأسطر في ملف PDF"؟

ج: يهدف البرنامج التعليمي "تحديد تباعد الأسطر في ملف PDF" إلى توجيه المستخدمين حول كيفية استخدام مكتبة Aspose.PDF لـ .NET لتخصيص تباعد الأسطر في النص داخل مستند PDF. يوفر البرنامج التعليمي إرشادات خطوة بخطوة ونماذج تعليمات برمجية C# لتوضيح العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في تحديد تباعد الأسطر داخل مستند PDF؟

ج: يساعد هذا البرنامج التعليمي المستخدمين على فهم كيفية الاستفادة من إمكانيات Aspose.PDF لـ .NET لتحديد تباعد الأسطر للنص في مستند PDF. باتباع الخطوات المقدمة وأمثلة التعليمات البرمجية، يمكن للمستخدمين ضبط تباعد الأسطر وفقًا لتفضيلاتهم.

#### س: ما هي المتطلبات الأساسية المطلوبة لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، تحتاج إلى تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو تثبيته في مشروعك باستخدام NuGet.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET. يمكّنك هذا من الاستفادة من ميزات المكتبة للعمل مع مستندات PDF وتخصيص تباعد الأسطر.

#### س: هل يمكنني استخدام هذا البرنامج التعليمي لتحديد تباعد الأسطر لأي نوع من النص؟

ج: نعم، يوفر هذا البرنامج التعليمي إرشادات حول كيفية تحديد تباعد الأسطر لأي محتوى نصي داخل مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام نماذج التعليمات البرمجية المتوفرة لضبط تباعد الأسطر في النص وفقًا لاحتياجاتك.

#### س: كيف أحدد وضع تباعد الأسطر في البرنامج التعليمي؟

 ج: يوضح البرنامج التعليمي كيفية إنشاء ملف`TextFormattingOptions` الكائن وتعيينه`LineSpacing` الملكية ل`TextFormattingOptions.LineSpacingMode.FullSize`. يحدد هذا الوضع تباعد الأسطر بالكامل لمحتوى النص.

#### س: كيف يمكنني تحميل خط معين للنص؟

 ج: إذا كنت ترغب في استخدام خط معين لمحتوى النص، فإن البرنامج التعليمي يوفر إرشادات حول كيفية تحميل ملف خط TrueType في ملف`FileStream` الكائن وقم بتعيينه كخط لـ`TextFragment`. يمكّنك هذا من تخصيص خط النص مع تباعد الأسطر.

#### س: كيف يمكنني تخصيص موضع النص داخل مستند PDF؟

 ج: لتخصيص موضع النص، قم بإنشاء ملف`TextFragment` الكائن وتعيينه`Position`الخاصية إلى الإحداثيات المطلوبة (X و Y). يتيح لك ذلك التحكم في مكان وضع النص داخل مستند PDF.

#### س: هل يمكنني تطبيق تعديلات تباعد الأسطر على مستندات PDF الموجودة؟

 ج: نعم، يمكنك تعديل تباعد الأسطر للنص في مستندات PDF الموجودة. يوضح البرنامج التعليمي كيفية إنشاء`TextFragment` مع تباعد الأسطر والموضع المحدد، ثم قم بإضافته إلى الصفحة`Paragraphs` مجموعة.