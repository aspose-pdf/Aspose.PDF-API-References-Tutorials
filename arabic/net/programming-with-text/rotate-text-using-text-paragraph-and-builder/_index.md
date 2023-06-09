---
title: قم بتدوير النص باستخدام فقرة النص ومنشئ النص
linktitle: قم بتدوير النص باستخدام فقرة النص ومنشئ النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تدوير النص باستخدام فقرة نصية ومنشئ في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 410
url: /ar/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام فقرات النص والبناة. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

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
using Aspose.Pdf.Text.TextBuilder;
```

## الخطوة 3: قم بإنشاء مستند PDF

 قم بتهيئة ملف`Document` كائن لإنشاء مستند PDF جديد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 تأكد من استبداله`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: أضف صفحة

 احصل على صفحة معينة من المستند باستخدام امتداد`Pages.Add()` طريقة:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## الخطوة 5: إنشاء فقرات نصية وتدويرها

 إنشاء`for` تكرار لإنشاء فقرات نصية متعددة بدورات مختلفة:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

اضبط الموضع وقيم الدوران حسب متطلباتك.

## الخطوة 6: إنشاء وتكوين أجزاء النص

 إنشاء ملفات متعددة`TextFragment`الكائنات ، قم بتعيين نصوصها وخصائصها:

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

## الخطوة 7: إلحاق أجزاء نصية بالفقرة

 قم بإلحاق أجزاء النص التي تم إنشاؤها بالفقرة باستخدام ملحق`AppendLine` طريقة:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## الخطوة 8: أنشئ TextBuilder وألحق الفقرة

 إنشاء`TextBuilder` كائن باستخدام`pdfPage` وإلحاق فقرة النص بصفحة PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## الخطوة 9: احفظ مستند PDF

 احفظ مستند PDF المعدل في ملف باستخدام امتداد`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 تأكد من استبداله`"TextFragmentTests_Rotated4_out.pdf"` باسم ملف الإخراج المطلوب.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تدوير النص باستخدام فقرات نصية وأدوات إنشاء في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً تفصيليًا ، بدءًا من إنشاء المستند وحتى حفظ النسخة المعدلة. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لمعالجة تدوير النص في ملفات PDF.

### نموذج التعليمات البرمجية المصدر لـ Rotate Text Using Text Paragraph And Builder باستخدام Aspose.PDF لـ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
// احصل على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// حدد التناوب
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
	// قم بإلحاق جزء النص بصفحة PDF
	textBuilder.AppendParagraph(paragraph);
}
// احفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```