---
title: تدوير النص باستخدام فقرة النص والمنشئ في ملف PDF
linktitle: تدوير النص باستخدام فقرة النص والمنشئ في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تدوير النص باستخدام فقرة نصية ومنشئ في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 410
url: /ar/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام فقرات النص وأدوات الإنشاء في ملف PDF. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

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
using Aspose.Pdf.Text.TextBuilder;
```

## الخطوة 3: إنشاء مستند PDF

 تهيئة`Document` كائن لإنشاء مستند PDF جديد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 تأكد من استبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: إضافة صفحة

 احصل على صفحة معينة من المستند باستخدام`Pages.Add()` طريقة:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## الخطوة 5: إنشاء فقرات النص وتدويرها

 إنشاء`for` حلقة لإنشاء فقرات نصية متعددة بتناوبات مختلفة:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

اضبط قيم الموضع والدوران وفقًا لمتطلباتك.

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

اضبط النص والخصائص الأخرى حسب الرغبة.

## الخطوة 7: إلحاق أجزاء النص بالفقرة

 قم بإلحاق أجزاء النص التي تم إنشاؤها بالفقرة باستخدام`AppendLine` طريقة:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## الخطوة 8: إنشاء TextBuilder وإلحاق الفقرة

 إنشاء`TextBuilder` كائن باستخدام`pdfPage` وإلحاق الفقرة النصية بصفحة PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## الخطوة 9: احفظ مستند PDF

 احفظ مستند PDF المعدل في ملف باستخدام الملف`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 تأكد من استبدال`"TextFragmentTests_Rotated4_out.pdf"` مع اسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لتدوير النص باستخدام Text Paragraph And Builder باستخدام Aspose.PDF لـ .NET 
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
	// تحديد التدوير
	paragraph.Rotation = i * 90 + 45;
	// إنشاء جزء من النص
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// إنشاء جزء من النص
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// إنشاء جزء من النص
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// تعيين خصائص النص
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// إنشاء جزء من النص
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
	// إلحاق جزء النص بصفحة PDF
	textBuilder.AppendParagraph(paragraph);
}
// حفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تدوير النص باستخدام فقرات النص وأدوات الإنشاء في مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من إنشاء المستند وحتى حفظ النسخة المعدلة. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لمعالجة تدوير النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تدوير النص باستخدام فقرة النص ومنشئه"؟

ج: يوفر البرنامج التعليمي "تدوير النص باستخدام فقرة النص والمنشئ" دليلاً شاملاً حول كيفية استخدام مكتبة Aspose.PDF لـ .NET لتدوير النص باستخدام فقرات النص وأدوات الإنشاء داخل مستند PDF. يوضح البرنامج التعليمي إرشادات خطوة بخطوة ويتضمن نموذج تعليمات برمجية C# لتحقيق تدوير النص مع الفقرات والتنسيق المخصص.

#### س: كيف يختلف هذا البرنامج التعليمي عن البرامج التعليمية السابقة لتدوير النص؟

ج: على عكس البرامج التعليمية السابقة، يجمع هذا البرنامج التعليمي بين استخدام فقرات النص والمنشئات وزوايا التدوير لتحقيق تأثير تدوير النص أكثر تقدمًا. ويوضح كيفية إنشاء فقرات نصية متعددة بزوايا دوران مختلفة وتطبيق التنسيق المخصص على أجزاء النص الفردية.

#### س: ما أهمية استخدام فقرات النص والمنشئات لتدوير النص؟

ج: يتيح استخدام فقرات النص وأدوات إنشاء النص تحسين التحكم في تدوير النص وتنسيقه. توفر فقرات النص طريقة منظمة لتنظيم أجزاء النص، بينما يقوم المنشئون بتسهيل إنشاء محتوى النص ومعالجته داخل مستند PDF.

#### س: هل يمكنني تطبيق زوايا دوران مختلفة على كل فقرة نصية؟

 ج: نعم، يمكنك تطبيق زوايا دوران مختلفة على كل فقرة نصية عن طريق ضبط الإعداد`Rotation` ملكية`TextParagraph` هدف. يتيح لك ذلك إنشاء تأثيرات تدوير نص متنوعة وديناميكية داخل مستند PDF.

#### س: كيف يمكنني تخصيص تنسيق أجزاء النص داخل فقرات النص؟

 ج: يمكنك تخصيص تنسيق أجزاء النص عن طريق تعيين خصائص مختلفة للملف`TextState` داخل كل`TextFragment` هدف. يمكن تعديل خصائص مثل حجم الخط ونوع الخط وألوان المقدمة والخلفية والتسطير لتحقيق التأثير المرئي المطلوب.

#### س: هل يمكنني إنشاء تأثيرات أكثر تعقيدًا لتدوير النص باستخدام هذه الطريقة؟

ج: بالتأكيد. من خلال إنشاء فقرات نصية متعددة بشكل متكرر بزوايا تدوير وخيارات تنسيق مختلفة، يمكنك تحقيق تأثيرات تدوير نص معقدة وجذابة بصريًا يمكنها تحسين سهولة القراءة وجماليات مستندات PDF الخاصة بك.

#### س: هل من الممكن الجمع بين تدوير النص وتقنيات معالجة النص الأخرى؟

ج: نعم، يمكنك الجمع بين تدوير النص وتقنيات معالجة النص الأخرى التي توفرها مكتبة Aspose.PDF. يتضمن ذلك إضافة الجداول والصور والارتباطات التشعبية والمزيد لإنشاء مستندات PDF غنية وغنية بالمعلومات.

#### س: هل أحتاج إلى ترخيص خاص لاستخدام مكتبة Aspose.PDF في مشروعي؟

ج: نعم، أنت بحاجة إلى ترخيص Aspose صالح لاستخدام مكتبة Aspose.PDF في مشروعك. يمكنك الحصول على ترخيص من موقع Aspose، والذي سيزودك ببيانات الاعتماد اللازمة لدمج المكتبة واستخدامها بشكل فعال.