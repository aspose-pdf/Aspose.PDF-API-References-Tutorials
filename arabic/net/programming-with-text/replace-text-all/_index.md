---
title: استبدال النص الكل
linktitle: استبدال النص الكل
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال كل النص في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 350
url: /ar/net/programming-with-text/replace-text-all/
---

في هذا البرنامج التعليمي ، سنشرح كيفية استبدال كل النص في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنقدم دليلاً مفصلاً خطوة بخطوة جنبًا إلى جنب مع الكود المصدري C # الضروري.

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
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## الخطوة 3: البحث عن النص واستبداله

 إنشاء`TextFragmentAbsorber` للعثور على جميع حالات إدخال عبارة البحث. اقبل الممتص لجميع صفحات مستند PDF لاستخراج أجزاء النص.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 4: استبدال النص

قم بالتكرار خلال أجزاء النص المستخرجة واستبدل النص كما هو مطلوب. قم بتحديث النص والخصائص الأخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## الخطوة 5: احفظ ملف PDF المعدل

احفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Replace Text All باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
//قم بإنشاء كائن TextAbsorber للعثور على جميع مثيلات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// تقبل الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الأجزاء
foreach (TextFragment textFragment in textFragmentCollection)
{
	// تحديث النص وخصائص أخرى
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// حفظ مستند PDF الناتج.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية استبدال كل النص في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تحميل مستند PDF والبحث عن النص المطلوب واستبداله وحفظ ملف PDF المعدل.