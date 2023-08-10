---
title: استبدال النص في التعبير العادي
linktitle: استبدل Texton Regular Expression
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال النص بناءً على تعبير عادي في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 360
url: /ar/net/programming-with-text/replace-text-on-regular-expression/
---

في هذا البرنامج التعليمي ، سنشرح كيفية استبدال النص بناءً على تعبير عادي في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنقدم دليلاً مفصلاً خطوة بخطوة جنبًا إلى جنب مع الكود المصدري C # الضروري.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- الفهم الأساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 عيّن المسار إلى الدليل حيث يوجد لديك ملف PDF للإدخال. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir`متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 قم بتحميل مستند PDF باستخدام ملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## الخطوة 3: البحث عن النص واستبداله باستخدام التعبير العادي

 إنشاء`TextFragmentAbsorber` الكائن وحدد نمط التعبير العادي للعثور على جميع العبارات المطابقة للنمط. قم بتعيين خيار البحث عن النص لتمكين استخدام التعبير العادي.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## الخطوة 4: استبدال النص

قم بالتكرار خلال أجزاء النص المستخرجة واستبدل النص كما هو مطلوب. قم بتحديث النص والخصائص الأخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## الخطوة 5: احفظ ملف PDF المعدل

احفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لاستبدال Texton Regular Expression باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// قم بإنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
// تعيين خيار البحث عن النص لتحديد استخدام التعبير العادي
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// تقبل الممتص لصفحة واحدة
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الأجزاء
foreach (TextFragment textFragment in textFragmentCollection)
{
	// تحديث النص وخصائص أخرى
	textFragment.Text = "New Phrase";
	// قم بتعيين مثيل لكائن.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية استبدال النص بناءً على تعبير عادي في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تحميل مستند PDF والبحث عن نص باستخدام تعبير عادي واستبداله وحفظ ملف PDF المعدل.