---
title: تحديد مسافة السطور في ملف PDF
linktitle: تحديد مسافة السطور في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تحديد مسافة السطور في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 510
url: /ar/net/programming-with-text/specify-line-spacing/
---
يوضح هذا البرنامج التعليمي كيفية تحديد مسافة السطور في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل المتابعة بالبرنامج التعليمي، تأكد من توفر ما يلي:

- المعرفة الأساسية للغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك الحصول عليها من موقع Aspose على الويب أو استخدام NuGet لتثبيتها في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات الأساسية الضرورية

أضف التوجيهات التالية في بداية ملف C# الخاص بك لاستيراد المساحات المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## الخطوة 3: تعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: تحميل ملف PDF المدخل

 قم بتحميل ملف PDF المدخل باستخدام`Document` فصل:

```csharp
Document doc = new Document();
```

## الخطوة 5: إنشاء خيارات تنسيق النص

 إنشاء`TextFormattingOptions` الكائن وتعيين وضع تباعد الأسطر إلى`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## الخطوة 6: إنشاء جزء نصي

 إنشاء`TextFragment` الكائن وتحديد محتوى النص:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## الخطوة 7: تحميل ملف الخط (اختياري)

 إذا كنت تريد استخدام خط معين للنص، فقم بتحميل ملف الخط TrueType في`FileStream` هدف:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 يستبدل`"HPSimplified.TTF"` مع اسم ملف الخط الفعلي.

## الخطوة 8: تحديد موضع النص والتباعد بين السطور

 تعيين موضع جزء النص وتعيينه`TextFormattingOptions` الى`TextState.FormattingOptions` ملكية:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## الخطوة 9: أضف النص إلى المستند

 أضف جزءًا من النص إلى المستند، إما عن طريق إضافته إلى`TextBuilder` أو مباشرة إلى الصفحة`Paragraphs` مجموعة:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## الخطوة 10: احفظ مستند PDF الناتج

حفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 تأكد من الاستبدال`"SpecifyLineSpacing_out.pdf"` مع اسم ملف الإخراج المطلوب.

### عينة من كود المصدر لتحديد مسافة السطور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// تحميل ملف PDF المدخل
Document doc = new Document();
//إنشاء TextFormattingOptions باستخدام LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// إنشاء كائن إنشاء نص للصفحة الأولى من المستند
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// إنشاء جزء نصي باستخدام سلسلة عينة
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// تحميل الخط TrueType في كائن التدفق
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// تعيين اسم الخط لسلسلة النص
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//حدد موضع جزء النص
		textFragment.Position = new Position(100, 600);
		//تعيين TextFormattingOptions للجزء الحالي إلى predefined (الذي يشير إلى LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// أضف النص إلى TextBuilder حتى يمكن وضعه فوق ملف PDF
		//textBuilder.AppendText(جزء النص);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// حفظ مستند PDF الناتج
	doc.Save(dataDir);
}
```

## خاتمة

مبروك! لقد تعلمت بنجاح كيفية تحديد المسافة بين الأسطر في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من إعداد المشروع إلى حفظ المستند المعدل. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك لتخصيص المسافة بين أسطر النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تحديد المسافة بين السطور في ملف PDF"؟

أ: يهدف البرنامج التعليمي "تحديد المسافة بين الأسطر في ملف PDF" إلى توجيه المستخدمين حول كيفية استخدام مكتبة Aspose.PDF لـ .NET لتخصيص المسافة بين أسطر النص داخل مستند PDF. يوفر البرنامج التعليمي تعليمات خطوة بخطوة وعينات من التعليمات البرمجية بلغة C# لتوضيح العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في تحديد المسافة بين الأسطر داخل مستند PDF؟

ج: يساعد هذا البرنامج التعليمي المستخدمين على فهم كيفية الاستفادة من إمكانيات Aspose.PDF for .NET لتحديد المسافة بين السطور للنص في مستند PDF. باتباع الخطوات وأمثلة التعليمات البرمجية المقدمة، يمكن للمستخدمين ضبط المسافة بين السطور وفقًا لتفضيلاتهم.

#### س: ما هي المتطلبات الأساسية المطلوبة لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، يجب أن يكون لديك مكتبة Aspose.PDF for .NET مثبتة. يمكنك الحصول عليها من موقع Aspose على الويب أو تثبيتها في مشروعك باستخدام NuGet.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF for .NET. يتيح لك هذا الاستفادة من ميزات المكتبة للعمل مع مستندات PDF وتخصيص المسافات بين السطور.

#### س: هل يمكنني استخدام هذا البرنامج التعليمي لتحديد المسافة بين الأسطر لأي نوع من النص؟

ج: نعم، يوفر هذا البرنامج التعليمي إرشادات حول كيفية تحديد مسافة السطور لأي محتوى نصي داخل مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام عينات التعليمات البرمجية المقدمة لضبط مسافة السطور في النص وفقًا لاحتياجاتك.

#### س: كيف يمكنني تحديد وضع تباعد الأسطر في البرنامج التعليمي؟

 أ: يوضح البرنامج التعليمي كيفية إنشاء`TextFormattingOptions` الكائن وضبطه`LineSpacing` الممتلكات ل`TextFormattingOptions.LineSpacingMode.FullSize`يحدد هذا الوضع المسافة الكاملة بين أسطر محتوى النص.

#### س: كيف يمكنني تحميل خط معين للنص؟

 ج: إذا كنت ترغب في استخدام خط معين لمحتوى النص، فإن البرنامج التعليمي يوفر إرشادات حول كيفية تحميل ملف خط TrueType في`FileStream` الكائن وتعيينه كخط لـ`TextFragment`يتيح لك هذا تخصيص خط النص مع تباعد السطور.

#### س: كيف أقوم بتخصيص موضع النص داخل مستند PDF؟

 أ: لتخصيص موضع النص، قم بإنشاء`TextFragment` الكائن وضبطه`Position`قم بتعديل الخاصية إلى الإحداثيات المطلوبة (X وY). يتيح لك هذا التحكم في مكان وضع النص داخل مستند PDF.

#### س: هل يمكنني تطبيق تعديلات تباعد الأسطر هذه على مستندات PDF الموجودة؟

 ج: نعم، يمكنك تعديل المسافة بين الأسطر للنص في مستندات PDF الموجودة. يوضح البرنامج التعليمي كيفية إنشاء`TextFragment` مع المسافة بين الأسطر والموضع المحددين، ثم قم بإضافته إلى الصفحة`Paragraphs` مجموعة.