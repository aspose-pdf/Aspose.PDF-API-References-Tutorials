---
title: أضف جدول المحتويات
linktitle: أضف جدول المحتويات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة جدول محتويات إلى مستندات PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة مع مثال التعليمات البرمجية المصدر. تعزيز التنقل في المستند!
type: docs
weight: 40
url: /ar/net/programming-with-document/addtoc/
---

في هذا البرنامج التعليمي ، سوف نستكشف كيفية استخدام ميزة Add TOC (جدول المحتويات) في Aspose.PDF لـ .NET لإضافة جدول محتويات إلى مستندات PDF. سنقدم دليلاً خطوة بخطوة ونوضح كود المصدر C # المطلوب لتحقيق ذلك. بنهاية هذا البرنامج التعليمي ، ستتمكن من إنشاء مستند PDF مع جدول محتويات باستخدام Aspose.PDF for .NET.


## الخطوة 1: قم بتحميل ملف PDF الحالي

للبدء ، نحتاج إلى تحميل ملف PDF موجود. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لملف PDF الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## الخطوة 2: قم بإنشاء صفحة جديدة لجدول المحتويات

سننشئ صفحة جديدة تحتوي على جدول المحتويات. يقوم الكود التالي بإدراج صفحة جديدة في الفهرس 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## الخطوة 3: تحديد معلومات جدول المحتويات

بعد ذلك ، نحتاج إلى تحديد معلومات جدول المحتويات. سنقوم بتعيين العنوان والخصائص الأخرى لجدول المحتويات. أضف الكود التالي:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## الخطوة 4: إنشاء عناصر جدول المحتويات

الآن ، سننشئ عناصر جدول المحتويات. في هذا البرنامج التعليمي ، سننشئ أربعة عناصر جدول المحتويات المقابلة لصفحات مختلفة. قم بتعديل الكود التالي وفقًا لمتطلباتك:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## الخطوة 5: احفظ المستند المحدث

 أخيرًا ، نحتاج إلى حفظ المستند المعدل مع جدول المحتويات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود أدناه بمسار ملف الإخراج المطلوب:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### مثال على الكود المصدري لإضافة جدول المحتويات إلى مستندات PDF باستخدام Aspose.PDF for .NET

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملفات PDF موجودة
Document doc = new Document(dataDir + "AddTOC.pdf");

// احصل على الوصول إلى الصفحة الأولى من ملف PDF
Page tocPage = doc.Pages.Insert(1);

// إنشاء كائن لتمثيل معلومات جدول المحتويات
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// قم بتعيين عنوان جدول المحتويات
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

// إنشاء كائنات سلسلة التي سيتم استخدامها كعناصر جدول المحتويات
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// إنشاء كائن العنوان
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// حدد صفحة الوجهة لكائن العنوان
	heading2.DestinationPage = doc.Pages[i + 2];

	// صفحة الوجهة
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// تنسيق الوجهة
	segment2.Text = titles[i];

	// أضف عنوانًا إلى الصفحة التي تحتوي على جدول المحتويات
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
//احفظ المستند المحدث
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);

```
