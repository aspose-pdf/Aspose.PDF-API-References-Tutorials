---
title: استبدل التواجد الأول
linktitle: استبدل التواجد الأول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال التواجد الأول للنص في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 330
url: /ar/net/programming-with-text/replace-first-occurrence/
---

في هذا البرنامج التعليمي ، سنشرح كيفية استبدال التواجد الأول لنص معين في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتابع العملية خطوة بخطوة لفتح مستند PDF ، والعثور على أول ظهور لعبارة البحث ، واستبدال النص ، وتحديث الخصائص ، وحفظ ملف PDF المعدل باستخدام كود المصدر C # المقدم.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى ضبط المسار إلى الدليل حيث لديك ملف PDF للإدخال. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 بعد ذلك ، نفتح مستند PDF باستخدام ملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## الخطوة 3: ابحث عن أول ظهور لعبارة البحث

 نقوم بإنشاء ملف`TextFragmentAbsorber`كائن وقبوله لجميع صفحات مستند PDF للعثور على جميع مثيلات عبارة البحث.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 4: استبدل النص

إذا تم العثور على عبارة البحث في مستند PDF ، فإننا نسترجع التواجد الأول لجزء النص ونقوم بتحديث خصائصه بالنص والتنسيق الجديدين.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## الخطوة 5: احفظ ملف PDF المعدل

أخيرًا ، نقوم بحفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لاستبدال التواجد الأول باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// قم بإنشاء كائن TextAbsorber للعثور على جميع مثيلات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// تقبل الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// احصل على أول ظهور للنص واستبدله
	TextFragment textFragment = textFragmentCollection[1];
	// تحديث النص وخصائص أخرى
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية استبدال التواجد الأول لنص معين في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك فتح مستند PDF والعثور على أول ظهور لعبارة البحث واستبدال النص وتحديث الخصائص وحفظ ملف PDF المعدل.