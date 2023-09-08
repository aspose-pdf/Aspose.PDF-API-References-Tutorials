---
title: إضافة TOC إلى ملف PDF
linktitle: إضافة TOC إلى ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة جدول محتويات إلى ملف PDF باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة مع مثال التعليمات البرمجية المصدر. تعزيز التنقل في المستندات!
type: docs
weight: 40
url: /ar/net/programming-with-document/addtoc/
---
في هذا البرنامج التعليمي، سنستكشف كيفية استخدام ميزة Add TOC (جدول المحتويات) إلى ملف PDF في Aspose.PDF لـ .NET لإضافة جدول محتويات إلى مستندات PDF. سنقدم دليلًا خطوة بخطوة ونشرح كود مصدر C# المطلوب لتحقيق ذلك. بنهاية هذا البرنامج التعليمي، ستكون قادرًا على إنشاء مستند PDF بجدول محتويات باستخدام Aspose.PDF for .NET.


## الخطوة 1: قم بتحميل ملف PDF الموجود

 للبدء، نحتاج إلى تحميل ملف PDF موجود. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي مع المسار الفعلي لملف PDF الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## الخطوة 2: إنشاء صفحة جديدة لجدول المحتويات

سنقوم بإنشاء صفحة جديدة لجدول المحتويات. يقوم التعليمة البرمجية التالية بإدراج صفحة جديدة في الفهرس 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## الخطوة 3: تحديد معلومات جدول المحتويات

بعد ذلك، نحتاج إلى تحديد معلومات جدول المحتويات. سنقوم بتعيين العنوان والخصائص الأخرى لجدول المحتويات. أضف الكود التالي:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## الخطوة 4: إنشاء عناصر جدول المحتويات

الآن، سوف نقوم بإنشاء عناصر جدول المحتويات. في هذا البرنامج التعليمي، سنقوم بإنشاء أربعة عناصر جدول محتويات تتوافق مع صفحات مختلفة. قم بتعديل الكود التالي حسب متطلباتك:

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

 وأخيرا، نحن بحاجة إلى حفظ الوثيقة المعدلة مع جدول المحتويات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود أدناه مع مسار ملف الإخراج المطلوب:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### مثال على الكود المصدري لإضافة جدول محتويات إلى مستندات PDF باستخدام Aspose.PDF لـ .NET

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملفات PDF الموجودة
Document doc = new Document(dataDir + "AddTOC.pdf");

// الوصول إلى الصفحة الأولى من ملف PDF
Page tocPage = doc.Pages.Insert(1);

// قم بإنشاء كائن لتمثيل معلومات جدول المحتويات
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// قم بتعيين عنوان جدول المحتويات
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//قم بإنشاء كائنات سلسلة سيتم استخدامها كعناصر جدول المحتويات
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

	// حدد الصفحة الوجهة لكائن العنوان
	heading2.DestinationPage = doc.Pages[i + 2];

	// صفحة الوجهة
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// تنسيق الوجهة
	segment2.Text = titles[i];

	// أضف عنوانًا إلى الصفحة التي تحتوي على جدول المحتويات
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// احفظ المستند المحدث
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية إضافة جدول محتويات (TOC) إلى مستندات PDF باستخدام Aspose.PDF لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود مصدر C# المتوفر، يمكنك بسهولة إنشاء مستند PDF مع جدول محتويات. يعمل جدول المحتويات على تحسين إمكانية استخدام المستند، مما يسمح للمستخدمين بالانتقال إلى أقسام أو صفحات معينة بشكل أكثر كفاءة. يوفر Aspose.PDF for .NET حلاً قويًا وسهل الاستخدام للعمل مع ملفات PDF في تطبيقات .NET، مما يتيح لك إنشاء مستندات PDF ديناميكية وتفاعلية بسهولة.

### الأسئلة الشائعة لإضافة جدول المحتويات إلى ملف PDF

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تتيح للمطورين العمل مع ملفات PDF في تطبيقات .NET بشكل فعال. فهو يوفر مجموعة واسعة من الميزات لإنشاء مستندات PDF ومعالجتها وإدارتها برمجيًا.

#### س: ما هو الغرض من إضافة جدول محتويات (TOC) إلى مستند PDF؟

ج: يوفر جدول المحتويات (TOC) وسيلة مساعدة للمستخدمين، مما يمكّنهم من الانتقال بسرعة إلى أقسام أو صفحات محددة داخل مستند PDF. يعمل على تحسين سهولة استخدام المستند وتجربة المستخدم.

#### س: كيف يمكنني إضافة جدول محتويات إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: لإضافة جدول محتويات إلى مستند PDF باستخدام Aspose.PDF لـ .NET، تحتاج إلى إنشاء صفحة جديدة للاحتفاظ بجدول المحتويات، وتحديد معلومات جدول المحتويات، ثم إنشاء عناصر جدول المحتويات التي تتوافق مع صفحات معينة أو الأقسام في الوثيقة.

#### س: هل يمكنني تخصيص مظهر جدول المحتويات؟

ج: نعم، يمكنك تخصيص مظهر جدول المحتويات عن طريق تعيين خصائص مختلفة لعناصر جدول المحتويات، مثل حجم الخط ونمط الخط والمحاذاة. يوفر Aspose.PDF for .NET المرونة في تصميم جدول المحتويات ليتوافق مع الشكل والمظهر المطلوبين.

#### س: هل Aspose.PDF for .NET مناسب لإضافة ميزات متقدمة إلى مستندات PDF؟

ج: بالتأكيد، Aspose.PDF for .NET هي مكتبة غنية بالميزات تسمح لك بإضافة وظائف متقدمة إلى مستندات PDF، بما في ذلك العناصر التفاعلية وحقول النماذج والتوقيعات الرقمية والمزيد.