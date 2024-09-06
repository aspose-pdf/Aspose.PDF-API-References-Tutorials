---
title: تدوير النص باستخدام فقرة النص والمنشئ في ملف PDF
linktitle: تدوير النص باستخدام فقرة النص والمنشئ في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تدوير النص باستخدام فقرة النص ومنشئها في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 410
url: /ar/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام فقرات النص والمنشئين في ملف PDF. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

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
using Aspose.Pdf.Text.TextBuilder;
```

## الخطوة 3: إنشاء مستند PDF

 تهيئة`Document` كائن لإنشاء مستند PDF جديد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 تأكد من الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: إضافة صفحة

 احصل على صفحة معينة من المستند باستخدام`Pages.Add()` طريقة:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## الخطوة 5: إنشاء فقرات النص وتدويرها

 إنشاء`for` حلقة لإنشاء فقرات نصية متعددة مع دورانات مختلفة:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

قم بضبط قيم الموضع والدوران وفقًا لمتطلباتك.

## الخطوة 6: إنشاء وتكوين أجزاء النص

 إنشاء متعددة`TextFragment` الكائنات، قم بتعيين نصها وخصائصها:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
```

قم بضبط النص والخصائص الأخرى حسب رغبتك.

## الخطوة 7: إضافة أجزاء نصية إلى الفقرة

 قم بإضافة أجزاء النص التي تم إنشاؤها إلى الفقرة باستخدام`AppendLine` طريقة:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## الخطوة 8: إنشاء TextBuilder وإضافة الفقرة

 إنشاء`TextBuilder` كائن باستخدام`pdfPage` وأضف فقرة النص إلى صفحة PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## الخطوة 9: احفظ مستند PDF

 احفظ مستند PDF المعدّل في ملف باستخدام`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 تأكد من الاستبدال`"TextFragmentTests_Rotated4_out.pdf"` مع اسم ملف الإخراج المطلوب.

### عينة من كود المصدر لتدوير النص باستخدام فقرة نصية وبناء باستخدام Aspose.PDF لـ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// تحديد الدوران
	paragraph.Rotation = i * 90 + 45;
	// إنشاء جزء نصي
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// إنشاء جزء نصي
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// إنشاء جزء نصي
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// تعيين خصائص النص
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// إنشاء جزء نصي
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// تعيين خصائص النص
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// إنشاء كائن TextBuilder
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// إضافة جزء من النص إلى صفحة PDF
	textBuilder.AppendParagraph(paragraph);
}
// حفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## خاتمة

مبروك! لقد تعلمت بنجاح كيفية تدوير النص باستخدام فقرات النص وأدوات البناء في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من إنشاء المستند إلى حفظ الإصدار المعدل. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك للتلاعب بتدوير النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تدوير النص باستخدام فقرة النص والمنشئ"؟

ج: يوفر البرنامج التعليمي "تدوير النص باستخدام فقرات النص والمنشئ" دليلاً شاملاً حول كيفية استخدام مكتبة Aspose.PDF لـ .NET لتدوير النص باستخدام فقرات النص والمنشئين داخل مستند PDF. يوضح البرنامج التعليمي تعليمات خطوة بخطوة ويتضمن عينة من كود C# لتحقيق تدوير النص باستخدام الفقرات والتنسيق المخصص.

#### س: كيف يختلف هذا البرنامج التعليمي عن دروس تدوير النص السابقة؟

ج: على عكس الدروس التعليمية السابقة، يجمع هذا البرنامج التعليمي بين استخدام فقرات النص وأدوات البناء وزوايا التدوير لتحقيق تأثير تدوير نص أكثر تقدمًا. ويوضح كيفية إنشاء فقرات نصية متعددة بزوايا تدوير مختلفة وتطبيق تنسيق مخصص على أجزاء نصية فردية.

#### س: ما أهمية استخدام فقرات النص والمنشئين لتدوير النص؟

أ: يتيح استخدام فقرات النص وأدوات البناء تحكمًا أفضل في تدوير النص وتنسيقه. توفر فقرات النص طريقة منظمة لتنظيم أجزاء النص، بينما تسهل أدوات البناء إنشاء المحتوى النصي ومعالجته داخل مستند PDF.

#### س: هل يمكنني تطبيق زوايا دوران مختلفة لكل فقرة نصية؟

 ج: نعم، يمكنك تطبيق زوايا دوران مختلفة لكل فقرة نصية عن طريق ضبط`Rotation` ممتلكات`TextParagraph` يتيح لك هذا إنشاء تأثيرات تدوير نص متنوعة وديناميكية داخل مستند PDF.

#### س: كيف أقوم بتخصيص تنسيق أجزاء النص داخل فقرات النص؟

 أ: يمكنك تخصيص تنسيق أجزاء النص من خلال ضبط خصائص مختلفة لـ`TextState` داخل كل منها`TextFragment` يمكن تعديل خصائص مثل حجم الخط ونوع الخط ولون المقدمة والخلفية والتسطير لتحقيق التأثير المرئي المطلوب.

#### س: هل يمكنني إنشاء تأثيرات تدوير النص أكثر تعقيدًا باستخدام هذه الطريقة؟

ج: بالتأكيد. من خلال إنشاء فقرات نصية متعددة بشكل متكرر بزوايا تدوير وخيارات تنسيق مختلفة، يمكنك تحقيق تأثيرات تدوير نص معقدة وجذابة بصريًا يمكنها تعزيز قابلية القراءة والجماليات في مستندات PDF الخاصة بك.

#### س: هل من الممكن الجمع بين تدوير النص وتقنيات معالجة النص الأخرى؟

ج: نعم، يمكنك الجمع بين تدوير النص وتقنيات معالجة النص الأخرى التي توفرها مكتبة Aspose.PDF. ويتضمن ذلك إضافة الجداول والصور والارتباطات التشعبية والمزيد لإنشاء مستندات PDF غنية ومفيدة.

#### س: هل أحتاج إلى ترخيص خاص لاستخدام مكتبة Aspose.PDF في مشروعي؟

ج: نعم، تحتاج إلى ترخيص Aspose صالح لاستخدام مكتبة Aspose.PDF في مشروعك. يمكنك الحصول على ترخيص من موقع Aspose الإلكتروني، والذي سيزودك بالبيانات اللازمة لدمج المكتبة واستخدامها بشكل فعال.