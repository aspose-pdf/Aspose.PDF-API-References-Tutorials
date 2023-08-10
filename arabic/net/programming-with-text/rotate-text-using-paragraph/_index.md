---
title: تدوير النص باستخدام الفقرة
linktitle: تدوير النص باستخدام الفقرة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تدوير النص باستخدام فقرات في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 380
url: /ar/net/programming-with-text/rotate-text-using-paragraph/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام الفقرات. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

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

## الخطوة 5: قم بإنشاء فقرة نصية

 إنشاء`TextParagraph` الكائن وتعيين موضعه على الصفحة:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

اضبط قيم المركز وفقًا لمتطلباتك.

## الخطوة 6: إنشاء وتكوين أجزاء النص

 إنشاء ملفات متعددة`TextFragment`الكائنات وتعيين نصوصها وخصائصها:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
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
```

## الخطوة 9: احفظ مستند PDF

 احفظ مستند PDF المعدل في ملف باستخدام امتداد`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 تأكد من استبداله`"TextFragmentTests_Rotated2_out.pdf"` باسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لـ Rotate Text Using Paragraph باستخدام Aspose.PDF for .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
// احصل على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// إنشاء جزء من النص
TextFragment textFragment1 = new TextFragment("rotated text");
// تعيين خصائص النص
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// تعيين التناوب
textFragment1.TextState.Rotation = 45;
// إنشاء جزء من النص
TextFragment textFragment2 = new TextFragment("main text");
// تعيين خصائص النص
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// إنشاء جزء من النص
TextFragment textFragment3 = new TextFragment("another rotated text");
// تعيين خصائص النص
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// تعيين التناوب
textFragment3.TextState.Rotation = -45;
// إلحاق أجزاء النص بالفقرة
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// إنشاء كائن TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// قم بإلحاق فقرة النص بصفحة PDF
textBuilder.AppendParagraph(paragraph);
// احفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تدوير النص باستخدام فقرات في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً تفصيليًا ، بدءًا من إنشاء المستند وحتى حفظ النسخة المعدلة. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لمعالجة تدوير النص في ملفات PDF.