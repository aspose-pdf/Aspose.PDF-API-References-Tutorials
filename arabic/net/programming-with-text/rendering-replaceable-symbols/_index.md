---
title: تقديم الرموز القابلة للاستبدال
linktitle: تقديم الرموز القابلة للاستبدال
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تقديم الرموز القابلة للاستبدال في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 310
url: /ar/net/programming-with-text/rendering-replaceable-symbols/
---

في هذا البرنامج التعليمي ، سنشرح كيفية عرض الرموز القابلة للاستبدال في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتابع العملية خطوة بخطوة لإنشاء ملف PDF ، وإضافة جزء نصي بعلامات سطر جديد ، وتعيين خصائص النص ، وتحديد موضع النص ، وحفظ ملف PDF باستخدام كود المصدر C # المقدم.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى الدليل حيث تريد حفظ ملف PDF الذي تم إنشاؤه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بإنشاء مستند وصفحة PDF

بعد ذلك ، نقوم بإنشاء مستند PDF جديد وإضافة صفحة إليه باستخدام ملف`Document` فئة و`Page` فئة من مكتبة Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## الخطوة 3: إضافة جزء نصي باستخدام محددات سطر جديد

 نقوم بإنشاء ملف`TextFragment` الكائن وتعيين نصه ليشمل علامات السطر الجديد (`Environment.NewLine`) لتمثيل أسطر متعددة من النص.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## الخطوة 4: تعيين خصائص جزء النص

يمكننا تعيين خصائص مختلفة لجزء النص إذا رغبت في ذلك ، مثل حجم الخط والخط ولون الخلفية ولون المقدمة.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## الخطوة 5: إنشاء نص فقرة وموضع

 نقوم بإنشاء ملف`TextParagraph` الكائن ، إلحاق جزء النص بالفقرة ، وتعيين موضع الفقرة على الصفحة.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## الخطوة 6: أضف فقرة نصية إلى الصفحة

 نقوم بإنشاء ملف`TextBuilder` الكائن بالصفحة وإلحاق فقرة النص بمنشئ النص.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## الخطوة 7: احفظ مستند PDF

أخيرًا ، نحفظ مستند PDF في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لتقديم الرموز القابلة للاستبدال باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// قم بتهيئة جزء النص الجديد بنص يحتوي على علامات السطر الجديد المطلوبة
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// قم بتعيين خصائص جزء النص إذا لزم الأمر
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// إنشاء كائن TextParagraph
TextParagraph par = new TextParagraph();
// إضافة TextFragment جديدة إلى الفقرة
par.AppendLine(textFragment);
// تعيين موضع الفقرة
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// إنشاء كائن TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// أضف TextParagraph باستخدام TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية عرض الرموز القابلة للاستبدال في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك إنشاء ملف PDF وإضافة نص بعلامات سطر جديد وتعيين خصائص النص ووضع النص على الصفحة وحفظ ملف PDF.