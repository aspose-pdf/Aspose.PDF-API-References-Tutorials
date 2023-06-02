---
title: تخصيص أرقام الصفحات أثناء إضافة جدول المحتويات
linktitle: تخصيص أرقام الصفحات أثناء إضافة جدول المحتويات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تخصيص أرقام الصفحات أثناء إضافة جدول محتويات (TOC) باستخدام Aspose.PDF for .NET باستخدام هذا الدليل التفصيلي ومثال التعليمات البرمجية هذا.
type: docs
weight: 100
url: /ar/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---

في هذا البرنامج التعليمي ، سوف نستكشف كيفية تخصيص أرقام الصفحات أثناء إضافة جدول محتويات (TOC) باستخدام Aspose.PDF لـ .NET. سنقدم إرشادات خطوة بخطوة ، جنبًا إلى جنب مع مثال رمز ، لمساعدتك في تحقيق ذلك.

## الخطوة 1: تحميل ملف PDF موجود

أولاً ، نحتاج إلى تحميل ملف PDF موجود. في هذا البرنامج التعليمي ، سنستخدم الملف "42824.pdf" الموجود في دليل "دليل المستندات". استبدل مسار الدليل هذا بالمسار الفعلي إلى دليل المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## الخطوة 2: إضافة صفحة جدول المحتويات

 بعد ذلك ، نحتاج إلى إضافة صفحة جديدة في بداية المستند لتكون بمثابة صفحة جدول المحتويات. يمكننا تحقيق ذلك باستخدام`Insert()` طريقة`Pages` جمع`Document` هدف.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## الخطوة 3: إنشاء كائن جدول المحتويات

 لإنشاء كائن TOC ، نحتاج أولاً إلى إنشاء ملف`TocInfo`الكائن وتعيين خصائصه. في هذا البرنامج التعليمي ، سنقوم بتعيين عنوان جدول المحتويات على "جدول المحتويات" وبادئة رقم الصفحة على "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## الخطوة 4: إنشاء إدخالات جدول المحتويات

لإنشاء إدخالات جدول المحتويات ، نحتاج إلى المرور عبر جميع صفحات المستند ، باستثناء صفحة جدول المحتويات ، وإنشاء كائن عنوان لكل صفحة. يمكننا بعد ذلك إضافة كائن العنوان إلى صفحة جدول المحتويات وتحديد صفحة الوجهة الخاصة بها.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // إنشاء كائن العنوان
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // حدد صفحة الوجهة لكائن العنوان
    heading2.DestinationPage = doc.Pages[i + 1];
    // صفحة الوجهة
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // تنسيق الوجهة
    segment2.Text = "Page " + i.ToString();
    // أضف عنوانًا إلى الصفحة التي تحتوي على جدول المحتويات
    tocPage.Paragraphs.Add(heading2);
}
```

## الخطوة 5: حفظ المستند المحدث

 أخيرًا ، نحتاج إلى حفظ المستند المحدث في ملف جديد. يمكننا تحقيق ذلك باستخدام`Save()` طريقة`Document` هدف.

```csharp
doc.Save(outFile);
```

### مثال على شفرة المصدر لتخصيص الصفحات المخدرة أثناء إضافة جدول المحتويات باستخدام Aspose.PDF لـ .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
//قم بتحميل ملفات PDF موجودة
Document doc = new Document(inFile);
// احصل على الوصول إلى الصفحة الأولى من ملف PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// إنشاء كائن لتمثيل معلومات جدول المحتويات
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// قم بتعيين عنوان جدول المحتويات
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// إنشاء كائن العنوان
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// حدد صفحة الوجهة لكائن العنوان
	heading2.DestinationPage = doc.Pages[i + 1];
	// صفحة الوجهة
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// تنسيق الوجهة
	segment2.Text = "Page " + i.ToString();
	// أضف عنوانًا إلى الصفحة التي تحتوي على جدول المحتويات
	tocPage.Paragraphs.Add(heading2);
}

// احفظ المستند المحدث
doc.Save(outFile);
```

## خاتمة

في هذا البرنامج التعليمي ، قدمنا إرشادات خطوة بخطوة حول كيفية تخصيص أرقام الصفحات أثناء إضافة جدول المحتويات باستخدام Aspose.PDF لـ .NET. لقد قدمنا أيضًا مثالًا للرمز يمكنك استخدامه كمرجع عند تنفيذ هذه الميزة في ملف

